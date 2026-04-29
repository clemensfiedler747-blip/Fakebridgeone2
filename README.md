import React, { useState } from 'react';
import { Eye, Globe, HelpCircle } from 'lucide-react';

const App = () => {
  const [showCookies, setShowCookies] = useState(true);
  const [login, setLogin] = useState('');
  const [password, setPassword] = useState('');

  const handleLogin = (e) => {
    e.preventDefault();
    console.log("Anmeldung mit:", { login, password });
  };

  return (
    <div className="min-h-screen flex flex-col font-sans" style={{ backgroundColor: '#4db6ac' }}>
      {/* Gelber Cookie-Banner */}
      {showCookies && (
        <div className="bg-[#f0e68c] py-2 px-4 flex justify-center items-center gap-3 text-sm text-[#263238] border-b border-yellow-200/50">
          <p>
            Diese Website verwendet Cookies. Für weitere Informationen besuchen Sie bitte den <span className="underline font-bold cursor-pointer">Datenschutzhinweis.</span>
          </p>
          <button 
            onClick={() => setShowCookies(false)}
            className="bg-[#fafafa] px-6 py-1 rounded-full font-bold shadow-sm border border-gray-300 hover:bg-white transition-colors"
          >
            Cookies akzeptieren
          </button>
        </div>
      )}

      {/* Türkiser Header */}
      <header className="bg-[#3caea3] text-[#263238] py-3 px-6 md:px-12 flex justify-between items-center shadow-sm">
        <div className="flex items-center gap-2">
          {/* Logo-Symbol-Platzhalter */}
          <div className="w-8 h-8 bg-[#6b2a2a] flex items-center justify-center rounded-sm">
             <div className="w-5 h-5 border-2 border-white/50"></div>
          </div>
          <span className="text-xl tracking-[0.15em] font-bold uppercase font-serif">Cambridge</span>
        </div>
        
        <div className="flex items-center gap-6">
          <button className="flex items-center gap-1 text-[15px] font-medium hover:opacity-70 transition-opacity">
            <HelpCircle size={20} /> Hilfe
          </button>
          <button className="flex items-center gap-1 text-[15px] font-medium hover:opacity-70 transition-opacity">
            <Globe size={20} /> English
          </button>
          <button className="bg-[#263238] text-white px-8 py-2 rounded-full text-sm font-bold hover:bg-black transition-all">
            Anmelden
          </button>
        </div>
      </header>

      {/* Hauptbereich */}
      <main className="flex-grow flex items-center justify-center p-6">
        <div className="bg-white w-full max-w-[480px] rounded-sm shadow-xl p-8 md:p-14 flex flex-col items-center">
          <h1 className="text-3xl font-semibold text-[#263238] mb-1">Anmelden</h1>
          <p className="text-gray-500 text-sm mb-10 italic">mit</p>

          {/* Social Logins - Karten-Stil wie im Bild */}
          <div className="w-full space-y-4 mb-2">
            <div className="flex gap-4">
              <button className="flex-1 flex items-center justify-center gap-3 py-3 rounded-md shadow-[0_2px_10px_rgba(0,0,0,0.1)] border border-gray-50 hover:bg-gray-50 transition-all">
                <svg className="w-5 h-5 fill-[#1877F2]" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
                <span className="text-sm font-semibold text-gray-600">Facebook</span>
              </button>
              <button className="flex-1 flex items-center justify-center gap-3 py-3 rounded-md shadow-[0_2px_10px_rgba(0,0,0,0.1)] border border-gray-50 hover:bg-gray-50 transition-all">
                <svg className="w-5 h-5" viewBox="0 0 24 24">
                  <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
                  <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
                  <path fill="#FBBC05" d="M5.84 14.1c-.22-.66-.35-1.36-.35-2.1s.13-1.44.35-2.1V7.06H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.94l3.66-2.84z"/>
                  <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.06l3.66 2.84c.87-2.6 3.3-4.52 6.16-4.52z"/>
                </svg>
                <span className="text-sm font-semibold text-gray-600">Google</span>
              </button>
            </div>
            <div className="flex justify-center">
              <button className="w-1/2 flex items-center justify-center gap-3 py-3 rounded-md shadow-[0_2px_10px_rgba(0,0,0,0.1)] border border-gray-50 hover:bg-gray-50 transition-all">
                <svg className="w-5 h-5 fill-black" viewBox="0 0 384 512"><path d="M318.7 268.7c-.2-36.7 16.4-64.4 50-84.8-18.8-26.9-47.2-41.7-84.7-44.6-35.5-2.8-74.3 20.7-88.5 20.7-15 0-49.4-19.7-76.4-19.7C63.3 141.2 4 184.8 4 273.5q0 39.3 14.4 81.2c12.8 36.7 59 126.7 107.2 125.2 25.2-.6 43-17.9 75.8-17.9 31.8 0 48.3 17.9 76.4 17.9 48.6-.7 90.4-82.5 102.6-119.3-65.2-30.7-61.7-90-61.7-91.9zm-56.6-164.2c27.3-32.4 24.8-61.9 24-72.5-24.1 1.4-52 16.4-67.9 34.9-17.5 19.8-27.8 44.3-25.6 71.9 26.1 2 49.9-11.4 69.5-34.3z"/></svg>
                <span className="text-sm font-semibold text-gray-600">Apple</span>
              </button>
            </div>
          </div>

          <div className="w-full relative flex py-8 items-center">
            <div className="flex-grow border-t border-gray-200"></div>
            <span className="flex-shrink mx-4 text-gray-400 text-xs">oder</span>
            <div className="flex-grow border-t border-gray-200"></div>
          </div>

          {/* Formular */}
          <form onSubmit={handleLogin} className="w-full space-y-6">
            <div className="space-y-1">
              <label className="block text-sm font-bold text-[#263238]">Anmelden</label>
              <input 
                type="text" 
                placeholder="Benutzernamen oder E-Mail-Adresse eingeben *" 
                className="w-full bg-[#f4f4f4] p-4 rounded-sm text-sm border-b-2 border-transparent focus:border-[#7c4dff] outline-none transition-colors"
                value={login}
                onChange={(e) => setLogin(e.target.value)}
              />
            </div>

            <div className="space-y-1 relative">
              <label className="block text-sm font-bold text-[#263238]">Passwort</label>
              <div className="relative">
                <input 
                  type="password" 
                  placeholder="Passwort eingeben *" 
                  className="w-full bg-[#f4f4f4] p-4 rounded-sm text-sm border-b-2 border-transparent focus:border-[#7c4dff] outline-none transition-colors"
                  value={password}
                  onChange={(e) => setPassword(e.target.value)}
                />
                <button type="button" className="absolute right-4 top-1/2 -translate-y-1/2 text-[#7c4dff]">
                  <Eye size={20} />
                </button>
              </div>
            </div>

            <div className="text-right">
              <button type="button" className="text-[#7c4dff] text-sm font-bold hover:underline">
                Passwort vergessen?
              </button>
            </div>

            <div className="pt-2">
              <button 
                type="submit" 
                className="w-full bg-[#7c4dff] text-white font-bold py-4 rounded-full text-lg shadow-lg hover:bg-[#6a3de8] transition-all transform active:scale-95"
              >
                Anmelden
              </button>
            </div>
          </form>

          <div className="mt-10 text-center">
            <button className="text-[#7c4dff] font-bold underline text-md hover:opacity-80 transition-opacity">
              Noch kein Konto?
            </button>
          </div>
        </div>
      </main>
    </div>
  );
};

export default App;
