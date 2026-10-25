# carlocavallopt.com — sito personale di Carlo Cavallo PT

Sito statico (un solo `index.html` + cartella `img/`), niente build. Pubblicato su Vercel
(progetto `carlocavallopt-sito`, team `scontrino-app`, piano Hobby): ogni push su `main`
va online da solo in pochi secondi.

## Dominio
- carlocavallopt.com reindirizza a www.carlocavallopt.com (configurato su Vercel).
- Il dominio è registrato su WordPress.com (rinnovo automatico). DNS gestiti su WordPress.com:
  A @ → 216.198.79.1, CNAME www → 2e6d4b7c43f4ffd6.vercel-dns-017.com. MX e NS non vanno toccati.

## Come lavora Carlo
- Non usa terminale o ambienti locali: prova tutto dal browser o dal telefono.
- Le modifiche al codice, i commit e la pubblicazione li fa Claude. Spiegare in italiano, semplice.
- REGOLA: pubblicare subito ogni modifica, senza aspettare che Carlo scriva "pubblica". Dopo il push sul ramo
  di lavoro, portarla anche su `main` (va online da sola). Se c'è da correggere, si corregge dopo.

## Contenuti
- Design: sfondo scuro #0E0F0C, accento verde lime #C6F432 (variabili CSS in `:root`),
  font Archivo (titoli) + Manrope (testo). Responsive, menu a scomparsa sotto 1100px.
- Sezioni: hero, numeri, "Si sono allenati con me" (foto VIP), servizi, "I miei centri", Coaching Online,
  risultati, chi sono (certificazioni e master), modulo contatti, footer.
- WhatsApp: numero 393775247736 (variabile `WHATSAPP` nello script in fondo). Il modulo apre
  WhatsApp con nome, telefono, email, obiettivo, dove (in sede o Google Meet) e servizio già scritti.
- Foto VIP (`img/vip-1..5.webp`) prese dal repo `sito-fitpointactive`:
  1 Francesca Tocca, 2 Martina Colombari, 3 Billy Costacurta, 4 Andrea Iannone, 5 Gianni Sperti.
- Foto VIP mostrate come su fitpointactive.com (griglia, nome grande in maiuscolo). vip-4 è ritagliata in basso
  per togliere il nome scritto nella foto originale: ha la didascalia come le altre.
- "I miei centri": titolo "Tre centri a Sava, un solo obiettivo: tu.", testo "non sto dietro a un PC a mandare
  schede copia e incolla, ci metto la faccia" e 3 ruoli (Imprenditore dal 2007, Coach, Personal trainer). Poi le schede:
  FitPoint Active, C Club, Girl Power con link alle pagine di www.fitpointactive.com.
  Loghi e foto (`logo-*.webp`, `fp-sala-pesi`, `cclub-lat-machine`, `gp-sala-blu`) copiati dal repo
  `sito-fitpointactive`, che non va modificato da qui.
- Hero solo testo (niente foto: Carlo non la vuole lì perché la sua foto è già in "Chi sono").
  Quella foto (Carlo con i loghi) resta solo in `img/og-carlo.jpg` per l'anteprima social.
- "Risultati": 13 coppie prima/dopo (`img/risultati/N-prima|dopo.webp`, senza volto) prese dalla sezione C Club
  del repo `sito-fitpointactive`. Non visibili nella pagina: si aprono in una finestra (`<dialog>`) dal pulsante
  "Vedi i risultati" e si caricano solo all'apertura. `vercel.json` le esclude da Google (X-Robots-Tag).
  Non ci sono recensioni scritte: aggiungerle solo se Carlo le fornisce, mai inventarle.
- Servizi (3 schede): Personal Training in studio (C CLUB, include EMS e analisi BIA), Coaching Online,
  Video Coaching "Servizio Pro" (circa 1 ora in videochiamata, Carlo segue l'allenamento in diretta).
  I link "Scopri di più"/"Prenota" preselezionano il servizio nel modulo (`data-servizio`).
- Coaching Online (`#coaching`): "Ti seguo anche a distanza", per chi non può venire nei centri; 4 passi (check,
  programma, video in chat, aggiustamento settimanale) + rimando al Video Coaching.
- Biografia "Chi sono" scritta con Carlo: iniziato da ragazzo per passione, titoli 2011, poi ha smesso di gareggiare
  per seguire i clienti; allena donne (tonificare), dimagrimento, massa, postura/dolori. Ha visto persone su cui nessuno
  avrebbe scommesso cambiare fisico e vita. Motto: "Never say… I can't do it"
  (Non dire mai… non ce la faccio), anche nel footer.
- Foto "Chi sono": `img/carlo-chi-sono.webp` (verticale, sfondo bianco, mandata da Carlo), riquadro 4:5.
- Sezione contatti = "Prenota il tuo check gratuito": in sede (C CLUB, Via Leonardo Da Vinci 95, con analisi BIA)
  o in videochiamata su Google Meet, più cosa si fa nel check. Le CTA dicono "check gratuito", non "consulenza".
- Speed Training Store: blocco `#store` dentro "I miei centri" (3 negozi Sava/Manduria/Francavilla con orari,
  shop online speedtrainingstore.com, WhatsApp negozio 393208526928). Dati e foto dal repo `sito-fitpointactive`.
- Logo di Carlo (CC, "CARLO CAVALLO COACH"; originale oro, sul sito ricolorato verde lime #C6F432, COACH bianco): `img/logo-cc.webp` (solo simbolo, in alto a sinistra),
  `img/logo-carlo-cavallo.webp` (completo, nel footer), `img/favicon.png`, `img/apple-touch-icon.png`.
  Ricavati dall'immagine inviata da Carlo togliendo lo sfondo nero (trasparenti).
- Footer in 3 gruppi: Seguimi (Instagram @carlocavallo.coach, Facebook, WhatsApp), I miei centri (fitpointactive.com,
  Instagram FitPoint/C Club/Girl Power, Facebook FitPoint), Speed Training Store (shop, Instagram). Niente YouTube
  (Carlo non ha un canale); @carlo.cavallo.pt è il vecchio Instagram, non usarlo.
- Dati reali dal vecchio sito WordPress: 14 certificazioni, 8 master, Campione Italiano WABBA 2011
  (HP-3), Mr Universo IBFA 2011 (Juniores), docente formazioni ACSI.
- L'app Speed Training Program non esiste più: non citarla sul sito.

## Da fare
- Nulla in sospeso: le prossime modifiche le decide Carlo man mano.
