import React, { useState } from 'react';
import { ExternalLink, Bug, Sparkles, MessageCircle, Send, ChevronRight, Clock, Star } from 'lucide-react';

// --- INITIAL DATA ---
const initialVersions = [
  {
    id: "v3.0.0",
    name: "Project Nova Release",
    date: "06. April 2026",
    status: "Stable",
    link: "https://example.com/v3",
    whatsNew: [
      "Komplett überarbeitetes UI mit Glassmorphism-Design",
      "Einführung des neuen KI-Assistenten",
      "Echtzeit-Synchronisation über alle Geräte hinweg",
      "Neues interaktives Dashboard"
    ],
    bugFixes: [
      "Speicherleck in der mobilen Ansicht behoben",
      "Verzögerung beim Laden von großen Bildern entfernt"
    ],
    comments: [
      { id: 1, user: "Elena", text: "Das neue Design ist absolut atemberaubend! 😍", time: "Vor 2 Stunden" },
      { id: 2, user: "Max_Dev", text: "Die Ladezeiten sind spürbar besser geworden. Gute Arbeit!", time: "Vor 5 Stunden" }
    ]
  },
  {
    id: "v2.5.4",
    name: "Performance Update",
    date: "15. März 2026",
    status: "Update",
    link: "https://example.com/v2.5.4",
    whatsNew: [
      "Optimierte Datenbankabfragen für 3x schnellere Suche",
      "Erweiterte Export-Funktionen (PDF, CSV)"
    ],
    bugFixes: [
      "Fehler beim Zurücksetzen des Passworts behoben",
      "Darstellungsfehler im Safari-Browser korrigiert",
      "Absturz bei zu vielen gleichzeitigen Benachrichtigungen gefixt"
    ],
    comments: [
      { id: 1, user: "Lisa99", text: "Endlich funktioniert der Export richtig.", time: "16. März 2026" }
    ]
  },
  {
    id: "v2.5.0",
    name: "Dark Mode Edition",
    date: "10. Januar 2026",
    status: "Stable",
    link: "https://example.com/v2.5",
    whatsNew: [
      "Vollständige Dark Mode Unterstützung",
      "Neue Einstellungsseite hinzugefügt",
      "Unterstützung für Tastatur-Shortcuts"
    ],
    bugFixes: [
      "Login-Session läuft nicht mehr vorzeitig ab",
      "Tippfehler in der französischen Übersetzung behoben"
    ],
    comments: []
  }
];

// --- COMPONENTS ---

const VersionCard = ({ version, onAddComment }) => {
  const [activeTab, setActiveTab] = useState('details'); // 'details' | 'comments'
  const [newComment, setNewComment] = useState('');

  const handleCommentSubmit = (e) => {
    e.preventDefault();
    if (!newComment.trim()) return;
    onAddComment(version.id, newComment);
    setNewComment('');
  };

  return (
    <div className="relative group animate-fade-in-up">
      {/* Glow Effect behind card */}
      <div className="absolute -inset-0.5 bg-gradient-to-r from-cyan-500 to-blue-600 rounded-2xl blur opacity-20 group-hover:opacity-40 transition duration-500"></div>
      
      {/* Card Content */}
      <div className="relative bg-slate-900/80 backdrop-blur-xl border border-white/10 rounded-2xl p-6 md:p-8 flex flex-col gap-6 transition-all duration-300 hover:border-white/20 hover:shadow-2xl hover:shadow-cyan-500/10">
        
        {/* Header */}
        <div className="flex flex-col md:flex-row md:items-center justify-between gap-4">
          <div>
            <div className="flex items-center gap-3 mb-2">
              <h2 className="text-3xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-white to-slate-400">
                {version.id}
              </h2>
              <span className={`px-3 py-1 rounded-full text-xs font-semibold tracking-wider uppercase ${
                version.status === 'Stable' ? 'bg-emerald-500/10 text-emerald-400 border border-emerald-500/20' : 
                'bg-blue-500/10 text-blue-400 border border-blue-500/20'
              }`}>
                {version.status}
              </span>
            </div>
            <p className="text-slate-400 text-sm flex items-center gap-2 font-medium">
              <span className="text-slate-300">{version.name}</span>
              <span className="w-1 h-1 rounded-full bg-slate-600"></span>
              <Clock size={14} /> {version.date}
            </p>
          </div>

          {/* Action Button */}
          <a 
            href={version.link} 
            target="_blank" 
            rel="noreferrer"
            className="group/btn relative inline-flex items-center justify-center gap-2 px-6 py-3 bg-gradient-to-r from-cyan-500 to-blue-600 text-white font-semibold rounded-xl overflow-hidden transition-all duration-300 hover:scale-105 hover:shadow-[0_0_20px_rgba(6,182,212,0.4)] focus:outline-none focus:ring-2 focus:ring-cyan-400 focus:ring-offset-2 focus:ring-offset-slate-900"
          >
            <span className="relative z-10 flex items-center gap-2">
              Öffnen <ExternalLink size={18} className="transition-transform group-hover/btn:translate-x-1 group-hover/btn:-translate-y-1" />
            </span>
            <div className="absolute inset-0 bg-white/20 translate-y-full group-hover/btn:translate-y-0 transition-transform duration-300 ease-out"></div>
          </a>
        </div>

        <hr className="border-white/5" />

        {/* Tab Navigation */}
        <div className="flex gap-4">
          <button 
            onClick={() => setActiveTab('details')}
            className={`flex-1 py-2 text-sm font-medium rounded-lg transition-all duration-300 ${
              activeTab === 'details' 
                ? 'bg-white/10 text-white shadow-inner' 
                : 'text-slate-400 hover:text-white hover:bg-white/5'
            }`}
          >
            Changelog
          </button>
          <button 
            onClick={() => setActiveTab('comments')}
            className={`flex-1 py-2 text-sm font-medium rounded-lg transition-all duration-300 flex items-center justify-center gap-2 ${
              activeTab === 'comments' 
                ? 'bg-white/10 text-white shadow-inner' 
                : 'text-slate-400 hover:text-white hover:bg-white/5'
            }`}
          >
            Kommentare 
            <span className="bg-cyan-500/20 text-cyan-400 py-0.5 px-2 rounded-full text-xs">
              {version.comments.length}
            </span>
          </button>
        </div>

        {/* Tab Content */}
        <div className="relative min-h-[200px]">
          {/* DETAILS TAB */}
          {activeTab === 'details' && (
            <div className="space-y-6 animate-fade-in">
              {/* What's New */}
              <div className="space-y-3">
                <h3 className="flex items-center gap-2 text-lg font-semibold text-emerald-400">
                  <Sparkles size={20} className="text-emerald-400" /> Was ist neu?
                </h3>
                <ul className="space-y-2">
                  {version.whatsNew.map((item, index) => (
                    <li key={index} className="flex items-start gap-3 text-slate-300">
                      <ChevronRight size={18} className="mt-0.5 text-emerald-500/50 shrink-0" />
                      <span className="leading-relaxed">{item}</span>
                    </li>
                  ))}
                </ul>
              </div>

              {/* Bug Fixes */}
              {version.bugFixes.length > 0 && (
                <div className="space-y-3">
                  <h3 className="flex items-center gap-2 text-lg font-semibold text-orange-400">
                    <Bug size={20} className="text-orange-400" /> Fehlerbehebungen
                  </h3>
                  <ul className="space-y-2">
                    {version.bugFixes.map((item, index) => (
                      <li key={index} className="flex items-start gap-3 text-slate-300">
                        <ChevronRight size={18} className="mt-0.5 text-orange-500/50 shrink-0" />
                        <span className="leading-relaxed">{item}</span>
                      </li>
                    ))}
                  </ul>
                </div>
              )}
            </div>
          )}

          {/* COMMENTS TAB */}
          {activeTab === 'comments' && (
            <div className="space-y-4 animate-fade-in flex flex-col h-full">
              <div className="space-y-4 max-h-[300px] overflow-y-auto pr-2 custom-scrollbar">
                {version.comments.length === 0 ? (
                  <div className="text-center py-8 text-slate-500 italic">
                    <MessageCircle size={32} className="mx-auto mb-3 opacity-20" />
                    Noch keine Kommentare vorhanden. Sei der Erste!
                  </div>
                ) : (
                  version.comments.map((comment) => (
                    <div key={comment.id} className="bg-white/5 rounded-xl p-4 border border-white/5 backdrop-blur-sm">
                      <div className="flex justify-between items-center mb-2">
                        <span className="font-semibold text-cyan-400 text-sm">{comment.user}</span>
                        <span className="text-xs text-slate-500">{comment.time}</span>
                      </div>
                      <p className="text-slate-300 text-sm leading-relaxed">{comment.text}</p>
                    </div>
                  ))
                )}
              </div>

              {/* Add Comment Input */}
              <form onSubmit={handleCommentSubmit} className="mt-auto pt-4 relative">
                <input
                  type="text"
                  value={newComment}
                  onChange={(e) => setNewComment(e.target.value)}
                  placeholder="Schreibe einen Kommentar..."
                  className="w-full bg-slate-950/50 border border-slate-700 rounded-xl py-3 pl-4 pr-12 text-slate-200 placeholder-slate-500 focus:outline-none focus:border-cyan-500 focus:ring-1 focus:ring-cyan-500 transition-all"
                />
                <button 
                  type="submit"
                  disabled={!newComment.trim()}
                  className="absolute right-2 top-1/2 -translate-y-1/2 p-2 mt-2 text-slate-400 hover:text-cyan-400 disabled:opacity-50 disabled:hover:text-slate-400 transition-colors"
                >
                  <Send size={18} />
                </button>
              </form>
            </div>
          )}
        </div>
      </div>
    </div>
  );
};

export default function App() {
  const [versions, setVersions] = useState(initialVersions);

  const handleAddComment = (versionId, text) => {
    setVersions(prev => prev.map(v => {
      if (v.id === versionId) {
        const newCommentObj = {
          id: Date.now(),
          user: "Gast User",
          text: text,
          time: "Gerade eben"
        };
        return { ...v, comments: [...v.comments, newCommentObj] };
      }
      return v;
    }));
  };

  return (
    <div className="min-h-screen bg-slate-950 text-slate-200 font-sans selection:bg-cyan-500/30 selection:text-cyan-100 relative overflow-hidden">
      
      {/* Background Ambient Effects */}
      <div className="fixed top-[-10%] left-[-10%] w-[40%] h-[40%] rounded-full bg-cyan-600/20 blur-[120px] pointer-events-none mix-blend-screen"></div>
      <div className="fixed bottom-[-10%] right-[-10%] w-[40%] h-[40%] rounded-full bg-blue-600/20 blur-[120px] pointer-events-none mix-blend-screen"></div>
      
      <div className="relative z-10 max-w-4xl mx-auto px-4 py-16 sm:px-6 lg:px-8 flex flex-col gap-12">
        
        {/* Header Section */}
        <header className="text-center space-y-4 animate-fade-in-down">
          <div className="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/5 border border-white/10 text-cyan-400 text-sm font-medium mb-4">
            <Star size={14} /> Offizielles Portal
          </div>
          <h1 className="text-5xl md:text-7xl font-extrabold tracking-tight text-transparent bg-clip-text bg-gradient-to-r from-white via-cyan-100 to-slate-400">
            Versions Hub
          </h1>
          <p className="text-lg md:text-xl text-slate-400 max-w-2xl mx-auto font-light">
            Entdecke die neuesten Updates, verbessere Funktionen und diskutiere mit der Community über unsere Software-Versionen.
          </p>
        </header>

        {/* Timeline / Cards Container */}
        <div className="relative space-y-8 before:absolute before:inset-0 before:ml-5 before:-translate-x-px md:before:mx-auto md:before:translate-x-0 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-transparent before:via-white/10 before:to-transparent">
          
          {versions.map((version, index) => (
            <div key={version.id} className="relative z-10" style={{ animationDelay: `${index * 150}ms` }}>
              <VersionCard 
                version={version} 
                onAddComment={handleAddComment}
              />
            </div>
          ))}
          
        </div>

        {/* Footer */}
        <footer className="text-center pt-8 pb-4 text-slate-500 text-sm border-t border-white/5">
          <p>© {new Date().getFullYear()} Software Inc. Alle Versionen sind anklickbar.</p>
        </footer>

      </div>

      <style dangerouslySetInnerHTML={{__html: `
        @keyframes fadeInUp {
          from { opacity: 0; transform: translateY(20px); }
          to { opacity: 1; transform: translateY(0); }
        }
        @keyframes fadeInDown {
          from { opacity: 0; transform: translateY(-20px); }
          to { opacity: 1; transform: translateY(0); }
        }
        @keyframes fadeIn {
          from { opacity: 0; }
          to { opacity: 1; }
        }
        .animate-fade-in-up {
          animation: fadeInUp 0.6s ease-out forwards;
        }
        .animate-fade-in-down {
          animation: fadeInDown 0.6s ease-out forwards;
        }
        .animate-fade-in {
          animation: fadeIn 0.4s ease-out forwards;
        }
        
        /* Custom Scrollbar for Comments */
        .custom-scrollbar::-webkit-scrollbar {
          width: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
          background: rgba(255, 255, 255, 0.02);
          border-radius: 8px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
          background: rgba(255, 255, 255, 0.1);
          border-radius: 8px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
          background: rgba(255, 255, 255, 0.2);
        }
      `}} />
    </div>
  );
}
