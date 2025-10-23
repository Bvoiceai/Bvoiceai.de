import React from "react";
import { motion } from "framer-motion";

export default function NewWebsiteStarter() {
  const scrollTo = (id: string) => {
    const el = document.getElementById(id);
    if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
  };

  return (
    <div className="min-h-screen bg-gradient-to-b from-white to-indigo-50 text-slate-800">
      {/* Nav */}
      <header className="sticky top-0 z-50 backdrop-blur bg-white/80 border-b border-indigo-200">
        <nav className="mx-auto max-w-6xl px-4 py-3 flex items-center justify-between">
          <a className="font-bold text-xl tracking-tight text-indigo-700" href="#" onClick={(e) => {e.preventDefault(); scrollTo("hero");}}>
            KI‑Telefonassistent
          </a>
          <div className="hidden md:flex items-center gap-6 text-sm">
            <button onClick={() => scrollTo("leistungen")} className="hover:text-indigo-800">Leistungen</button>
            <button onClick={() => scrollTo("how-it-works")} className="hover:text-indigo-800">So funktioniert's</button>
            <button onClick={() => scrollTo("ueber-uns")} className="hover:text-indigo-800">Über uns</button>
            <button onClick={() => scrollTo("kontakt")} className="hover:text-indigo-800">Kontakt</button>
            <a href="#kontakt" onClick={(e)=>{e.preventDefault(); scrollTo("kontakt");}} className="rounded-2xl px-4 py-2 bg-indigo-600 text-white shadow-sm hover:shadow-md transition">Beratung vereinbaren</a>
          </div>
        </nav>
      </header>

      {/* Hero */}
      <section id="hero" className="relative overflow-hidden">
        <div className="mx-auto max-w-6xl px-4 py-16 md:py-24 grid md:grid-cols-2 gap-10 items-center">
          <motion.div initial={{opacity:0, y:20}} animate={{opacity:1, y:0}} transition={{duration:0.6}}>
            <h1 className="text-4xl md:text-6xl font-extrabold leading-tight">
              Ihr smarter <span className="bg-gradient-to-r from-indigo-700 to-violet-500 bg-clip-text text-transparent">Telefonassistent</span>
            </h1>
            <p className="mt-5 text-lg text-slate-700">
              Unser KI‑gestützter Telefonservice nimmt Anrufe zuverlässig entgegen, sortiert sie und leitet sie gebündelt an Ihr Team weiter. So bleibt mehr Zeit für das Wesentliche: Ihre Kundinnen und Kunden.
            </p>
            <ul className="mt-6 space-y-2 text-slate-700">
              <li>• Natürliche, interaktive Gesprächsführung dank neuerer Technologie</li>
              <li>• Termine direkt am Telefon buchen inkl. SMS‑Bestätigung</li>
              <li>• Unterstützung von über 30 Sprachen</li>
            </ul>
            <div className="mt-8 flex flex-wrap gap-3">
              <a href="#leistungen" onClick={(e)=>{e.preventDefault(); scrollTo("leistungen");}} className="rounded-2xl px-5 py-3 bg-indigo-600 text-white shadow-sm hover:shadow-md transition">Zu den Leistungen</a>
              <a href="#kontakt" onClick={(e)=>{e.preventDefault(); scrollTo("kontakt");}} className="rounded-2xl px-5 py-3 border border-indigo-300 hover:border-indigo-400">Beratung vereinbaren</a>
            </div>
            <div className="mt-6 text-xs text-slate-500">🌍 30+ Sprachen · 📅 Terminbuchung · 🔒 DSGVO‑ready</div>
          </motion.div>

          <motion.div initial={{opacity:0, y:20}} animate={{opacity:1, y:0}} transition={{duration:0.6, delay:0.1}} className="relative">
            <div className="aspect-[4/3] rounded-2xl border border-indigo-200 bg-white shadow-sm overflow-hidden">
              {/* Ersetze src mit einer öffentlich erreichbaren URL (z.B. CDN) */}
              <img
                src="/assets/hero-robot.jpg"
                alt="KI‑Telefonassistent Demo mit Smartphone"
                className="h-full w-full object-cover"
              />
            </div>
          </motion.div>
        </div>
      </section>

      {/* Demo: So klingt der Assistent */}
      <section id="demo-audio" className="bg-white">
        <div className="mx-auto max-w-6xl px-4 py-16 md:py-20">
          <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">So klingt der bvoiceai.de one TelefonAssistent</h2>
          <p className="mt-3 text-slate-600 max-w-3xl">
            Wählen Sie aus, mit welcher Stimme unser KI‑Telefonassistent Ihre Patientinnen und Patienten begrüßt und durch das Gespräch führt –
            darunter auch weibliche Varianten. So lässt sich die Kommunikation individuell an den Stil Ihrer Praxis anpassen.
          </p>
          <div className="mt-6 grid md:grid-cols-3 gap-4">
            {(["Freundlich","Professionell","Natürlich (w)"] as const).map((label, i) => (
              <div key={i} className="rounded-2xl border border-indigo-200 p-4">
                <div className="font-medium text-indigo-700">{label}</div>
                <audio controls className="mt-3 w-full">
                  {/* Ersetze src durch eine echte, öffentlich erreichbare URL zu deiner M4A/MP3 */}
                  <source src="/assets/voice-demo.m4a" type="audio/mp4" />
                  <source src="/assets/voice-demo.mp3" type="audio/mpeg" />
                  Dein Browser unterstützt das Audio-Element nicht.
                </audio>
              </div>
            ))}
          </div>
          <p className="mt-6 text-slate-600">Schon heute spricht der Assistent über <strong>30 Sprachen</strong>. Sie entscheiden, welche Sprachen für Ihre Praxis freigeschaltet werden.</p>
        </div>
      </section>

      {/* So funktioniert es */}
      <section id="how-it-works" className="bg-indigo-50 border-y border-indigo-200">
        <div className="mx-auto max-w-6xl px-4 py-16 md:py-20">
          <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">So funktioniert es</h2>
          <p className="mt-3 text-slate-600 max-w-3xl">Vom Anruf zur Terminbestätigung – der Assistent führt durch das Gespräch und bucht direkt in Ihren Kalender.</p>
          <div className="mt-8 rounded-2xl border border-indigo-200 bg-white p-2 overflow-hidden">
            <img src="/assets/how-it-works.png" alt="Ablauf: Kunde ruft an, KI führt Dialog, Termin wird bestätigt" className="w-full h-auto" />
          </div>
        </div>
      </section>

      {/* Leistungen */}
      <section id="leistungen" className="mx-auto max-w-6xl px-4 py-16 md:py-20">
        <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">Leistungen</h2>
        <p className="mt-3 text-slate-600 max-w-2xl">Unsere KI‑Technologie unterstützt Sie und Ihr Team zuverlässig im täglichen Kundenkontakt.</p>
        <div className="mt-8 grid md:grid-cols-3 gap-6">
          {[{
            title: "Natürliche Gesprächsführung",
            desc: "Interaktive Telefonate dank modernster KI‑Technologie.",
          },{
            title: "Terminbuchung",
            desc: "Kunden buchen direkt im Kalender und erhalten Bestätigung per SMS.",
          },{
            title: "Mehrsprachigkeit",
            desc: "Unterstützung von über 30 Sprachen für internationale Kundschaft.",
          },{
            title: "Zuverlässige Anrufweiterleitung",
            desc: "Alle Anrufe werden sortiert und gebündelt an Ihr Team übermittelt.",
          },{
            title: "Datenschutzkonform",
            desc: "DSGVO‑ready und sicher für Ihr Unternehmen.",
          },{
            title: "Schnelle Integration",
            desc: "Einfache Einbindung in bestehende Abläufe und Systeme.",
          }].map((item, idx) => (
            <motion.div
              key={idx}
              className="rounded-2xl border border-indigo-200 bg-white p-6 shadow-sm"
              initial={{opacity:0, y:12}}
              whileInView={{opacity:1, y:0}}
              viewport={{ once: true, amount: 0.2 }}
              transition={{duration:0.4, delay: idx * 0.05}}
            >
              <div className="text-lg font-semibold text-indigo-700">{item.title}</div>
              <p className="mt-2 text-slate-600">{item.desc}</p>
            </motion.div>
          ))}
        </div>
      </section>

      {/* Über uns */}
      <section id="ueber-uns" className="bg-indigo-50 border-y border-indigo-200">
        <div className="mx-auto max-w-6xl px-4 py-16 md:py-20">
          <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">Über uns</h2>
          <div className="mt-6 grid md:grid-cols-2 gap-8 items-start">
            <div>
              <p className="text-slate-700 leading-relaxed">
                Wir kombinieren modernste KI‑Technologie mit einem klaren Fokus auf Kundenerlebnis. Unser Ziel ist es, Unternehmen Zeit zu schenken – damit Sie sich auf das Wesentliche konzentrieren können: Ihre Kundinnen und Kunden.
              </p>
              <ul className="mt-4 space-y-3 text-slate-700">
                <li>✅ Langjährige Erfahrung in KI‑gestützter Kommunikation</li>
                <li>✅ Fokus auf klare, natürliche Gesprächsführung</li>
                <li>✅ Datenschutz & Sicherheit an erster Stelle</li>
              </ul>
            </div>
            <div className="rounded-2xl overflow-hidden border border-indigo-200 bg-white">
              <img src="/assets/thumbs-up.jpg" alt="Zufriedene Kundinnen und Kunden zeigen Daumen hoch" className="w-full h-full object-cover" />
            </div>
          </div>
        </div>
      </section>

      {/* Branchenbeispiel */}
      <section id="branchen" className="mx-auto max-w-6xl px-4 py-16 md:py-20">
        <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">Einsatz in Ihrer Praxis</h2>
        <div className="mt-6 grid md:grid-cols-2 gap-8 items-center">
          <div className="rounded-2xl overflow-hidden border border-indigo-200 bg-white">
            <img src="/assets/consultation.jpg" alt="Praxisbeispiel: Beratung mit zufriedener Patientin" className="w-full h-full object-cover" />
          </div>
          <div>
            <h3 className="text-xl font-semibold text-indigo-700">Terminvergabe ohne Warteschleife</h3>
            <p className="mt-2 text-slate-600">Der Assistent begrüßt Ihre Patientinnen und Patienten, klärt Anliegen und bucht passende Termine direkt in Ihren Kalender.</p>
          </div>
        </div>
      </section>

      {/* KI‑Zusammenfassung */}
      <section id="zusammenfassung" className="bg-white">
        <div className="mx-auto max-w-6xl px-4 py-16 md:py-20">
          <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">KI‑gestützte Zusammenfassung</h2>
          <p className="mt-3 text-slate-600 max-w-3xl">Detailansicht der Zusammenfassung, die der Assistent aus dem Telefongespräch erstellt – inklusive Anliegen, Dringlichkeit, Patientendaten (falls genannt) und vereinbartem Termin.</p>
          <div className="mt-6 rounded-2xl border border-indigo-200 bg-white p-6 shadow-sm">
            <div className="text-sm uppercase tracking-wide text-slate-500">Beispiel</div>
            <div className="mt-3 grid md:grid-cols-3 gap-4 text-sm">
              <div><div className="font-semibold">Anrufer</div><div>Frau M., Bestandspatientin</div></div>
              <div><div className="font-semibold">Anliegen</div><div>Termin zur Kontrollbehandlung</div></div>
              <div><div className="font-semibold">Vorschlag</div><div>Mo, 14:00 Uhr – bestätigt per SMS</div></div>
            </div>
            <div className="mt-4 text-slate-600">Zusammenfassung: Möchte kurzfristig Termin in KW 42, bevorzugt nachmittags; Rückruf nur bei Rückfrage nötig.</div>
          </div>
        </div>
      </section>

      {/* Kontakt */}
      <section id="kontakt" className="bg-indigo-600 text-white">
        <div className="mx-auto max-w-6xl px-4 py-16 md:py-20">
          <h2 className="text-3xl md:text-4xl font-bold">Kontakt aufnehmen</h2>
          <p className="mt-3 text-indigo-100">Schreiben Sie uns, und wir vereinbaren eine persönliche Beratung.</p>
          <form className="mt-8 grid md:grid-cols-2 gap-4">
            <input className="w-full rounded-xl border border-white/20 bg-white/10 px-4 py-3 placeholder:text-white/70 focus:outline-none focus:ring-2 focus:ring-white/40" placeholder="Ihr Name" />
            <input className="w-full rounded-xl border border-white/20 bg-white/10 px-4 py-3 placeholder:text-white/70 focus:outline-none focus:ring-2 focus:ring-white/40" placeholder="E-Mail" />
            <textarea rows={4} className="md:col-span-2 w-full rounded-xl border border-white/20 bg-white/10 px-4 py-3 placeholder:text-white/70 focus:outline-none focus:ring-2 focus:ring-white/40" placeholder="Worum geht es?"></textarea>
            <button type="button" className="md:col-span-2 rounded-2xl px-5 py-3 bg-white text-indigo-700 font-medium shadow hover:shadow-md transition">Nachricht senden</button>
          </form>
          <div className="mt-6 text-sm text-indigo-100">Oder direkt: <a href="mailto:hallo@deinedomain.de" className="underline">hallo@deinedomain.de</a></div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-white border-t border-indigo-200">
        <div className="mx-auto max-w-6xl px-4 py-6 text-sm text-slate-600 flex flex-col md:flex-row items-center justify-between gap-2">
          <div>© {new Date().getFullYear()} KI‑Telefonassistent</div>
          <div className="flex items-center gap-4">
            <a href="#impressum" onClick={(e)=>{e.preventDefault(); scrollTo("impressum");}} className="hover:text-indigo-700">Impressum</a>
            <a href="#datenschutz" onClick={(e)=>{e.preventDefault(); scrollTo("datenschutz");}} className="hover:text-indigo-700">Datenschutz</a>
            <a href="#kontakt" onClick={(e)=>{e.preventDefault(); scrollTo("kontakt");}} className="hover:text-indigo-700">Kontakt</a>
            <a href="#ueber-uns" onClick={(e)=>{e.preventDefault(); scrollTo("ueber-uns");}} className="hover:text-indigo-700">Über uns</a>
          </div>
        </div>
      </footer>

      {/* Impressum */}
      <section id="impressum" className="mx-auto max-w-6xl px-4 py-16 md:py-20">
        <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">Impressum</h2>
        <p className="mt-3 text-slate-600">Angaben gemäß § 5 TMG:</p>
        <p className="mt-3 text-slate-600">Firmenname GmbH<br/>Musterstraße 123<br/>12345 Musterstadt<br/></p>
        <p className="mt-3 text-slate-600">Vertreten durch: Max Mustermann<br/>Handelsregister: Amtsgericht Musterstadt, HRB 12345<br/>Umsatzsteuer-ID: DE123456789</p>
        <p className="mt-3 text-slate-600">Kontakt:<br/>Telefon: +49 (0)123 456789<br/>E-Mail: info@firma.de</p>
      </section>

      {/* Datenschutz */}
      <section id="datenschutz" className="bg-indigo-50 border-t border-indigo-200">
        <div className="mx-auto max-w-6xl px-4 py-16 md:py-20">
          <h2 className="text-3xl md:text-4xl font-bold text-indigo-700">Datenschutzerklärung</h2>
          <p className="mt-3 text-slate-600">Wir nehmen den Schutz Ihrer persönlichen Daten sehr ernst. Personenbezogene Daten werden auf dieser Website nur im technisch notwendigen Umfang erhoben. In keinem Fall werden die erhobenen Daten verkauft oder aus anderen Gründen an Dritte weitergegeben.</p>
          <p className="mt-3 text-slate-600">Verantwortlich im Sinne der DSGVO:<br/>Firmenname GmbH<br/>Musterstraße 123<br/>12345 Musterstadt<br/>E-Mail: datenschutz@firma.de</p>
          <p className="mt-3 text-slate-600">Ihre Rechte:<br/>Sie haben jederzeit das Recht auf Auskunft über die bezüglich Ihrer Person gespeicherten Daten, deren Herkunft und Empfänger sowie den Zweck der Speicherung. Ebenso haben Sie das Recht auf Berichtigung, Sperrung oder Löschung dieser Daten.</p>
          <p className="mt-3 text-slate-600">Weitere Informationen zum Thema Datenschutz finden Sie in unserer ausführlichen Datenschutzerklärung, die wir Ihnen auf Anfrage gerne zusenden.</p>
        </div>
      </section>
    </div>
  );
}
