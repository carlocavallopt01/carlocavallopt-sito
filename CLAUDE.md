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
- Sezioni: hero, "Si sono allenati con me" (foto VIP), servizi, "I miei centri", Coaching Online,
  risultati, chi sono (certificazioni e master), modulo contatti, footer.
- WhatsApp: numero 393775247736 (variabile `WHATSAPP` nello script in fondo). È il numero privato di Carlo: va bene sul sito
  per WhatsApp (confermato), ma Vittoria non lo dà mai e non promette che richiama lui. Il modulo apre
  WhatsApp con nome, telefono, email, obiettivo, dove (in sede o Google Meet) e servizio già scritti.
- Foto VIP (`img/vip-1..5.webp`) prese dal repo `sito-fitpointactive`:
  1 Francesca Tocca, 2 Martina Colombari, 3 Billy Costacurta, 4 Andrea Iannone, 5 Gianni Sperti.
- Foto VIP mostrate come su fitpointactive.com (griglia, nome grande in maiuscolo). vip-4 (Iannone) è la foto
  mandata da Carlo il 25/10 (lui e Iannone alla leg extension), ritagliata 4:5.
- Sotto le foto VIP "In allenamento con me": `img/video-sperti.mp4`, `img/video-colombari.mp4` e `img/video-iannone.mp4` (da TikTok/Instagram di Carlo, ritagliati
  in basso per togliere i nomi Instagram), muti, in loop, partono solo quando sono sullo schermo.
- "I miei centri": titolo "Tre centri a Sava, un solo obiettivo: tu.", testo "non sto dietro a un PC a mandare
  schede copia e incolla, ci metto la faccia" e 3 ruoli (Imprenditore dal 2007, Coach, Personal trainer). Poi le schede:
  FitPoint Active, C Club, Girl Power con link alle pagine di www.fitpointactive.com.
  Loghi e foto (`logo-*.webp`, `fp-sala-pesi`, `cclub-lat-machine`, `gp-sala-blu`) copiati dal repo
  `sito-fitpointactive`, che non va modificato da qui.
- Hero: niente foto di Carlo (è già in "Chi sono"); sfondo = video C CLUB `img/video-hero.mp4` (11 s, muto, in loop,
  dal TikTok di Carlo; immagine ferma `video-hero.webp` se movimento ridotto o risparmio dati), dietro al testo da telefono (altezza del contenuto, non tutto schermo:
  Carlo trovava troppo spazio vuoto); da computer occupa
  la metà destra, sfumato verso il testo (verticale: a tutta larghezza diventerebbe sgranato).
  Tolta la fascia dei numeri (14 certificazioni ecc.): sono già più in basso. Da telefono VIP e negozi scorrono di lato.
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
- Foto "Chi sono": `img/carlo-tondo.webp` in un cerchio con bordo verde accanto al titolo, come nel Team del sito FitPoint
  (ritagliata dalla foto verticale mandata da Carlo).
- Sezione contatti = "Prenota il tuo check gratuito": in sede (C CLUB, Via Leonardo Da Vinci 95, con analisi BIA)
  o in videochiamata su Google Meet, più cosa si fa nel check. Le CTA dicono "check gratuito", non "consulenza".
- Modulo in 2 passi: passo 1 dati obbligatori (nome, telefono, email) e scelte; poi passo 2 facoltativo "Aiutami a
  conoscerti" (dati fisici, salute, allenamento, stile di vita, motivazione). Un solo messaggio WhatsApp con le sole
  risposte date (campi con `data-q`, raggruppati per `fieldset`). "Salta e invia solo i dati" manda solo il passo 1.
- App Lead: al passaggio dal passo 1 al passo 2 il contatto va in Lead (Supabase `lead_dal_sito`, chiave anon pubblica, come
  il sito FitPoint): sede `fitpoint`, campagna "Sito · Carlo Cavallo Coach · Check gratuito · <servizio>", una volta per visita.
  Le risposte del questionario (salute ecc.) NON vanno in Lead: solo nel messaggio WhatsApp. Casella consenso obbligatoria,
  campo trappola anti-spam `sito_web`. Repo app: `carlocavallopt01/lead`. Vittoria può chiamare questi contatti (deciso da
  Carlo): il consenso dice "anche al telefono tramite un'assistente virtuale" e la privacy ha la sezione Vittoria. Le istruzioni
  di Vittoria per questi contatti (check con Carlo) sono in `api/richiama.js` del repo `sito-fitpointactive` (`daSitoCarlo`).
- Privacy: `privacy.html` (servita come /privacy grazie a `cleanUrls` in `vercel.json`). Titolare indicato: FIT POINT ACTIVE
  SSD a r.l. (P.IVA 03417200734), anche nel footer: confermato da Carlo, tutto è sotto la società.
- Domande frequenti (`#faq`, prima dei contatti, + dati FAQPage per Google): palestra non serve per il Coaching Online,
  check di circa 30 minuti, si può iniziare da zero (risposte di Carlo); check gratuito e differenza Coaching/Video Coaching.
- Speed Training Store: blocco `#store` dentro "I miei centri" (3 negozi Sava/Manduria/Francavilla con orari,
  shop online speedtrainingstore.com, WhatsApp negozio 393208526928). Dati e foto dal repo `sito-fitpointactive`.
- Logo di Carlo (CC, "CARLO CAVALLO COACH"; originale oro, sul sito ricolorato verde lime #C6F432, COACH bianco): `img/logo-cc.webp` (solo simbolo, in alto a sinistra),
  `img/logo-carlo-cavallo.webp` (completo, nel footer), `img/favicon.png`, `img/apple-touch-icon.png`.
  Ricavati dall'immagine inviata da Carlo togliendo lo sfondo nero (trasparenti).
- Footer in 3 gruppi: Seguimi (Instagram @carlocavallocoach, Facebook, WhatsApp), I miei centri (fitpointactive.com,
  Instagram FitPoint/C Club/Girl Power, Facebook FitPoint), Speed Training Store (shop, Instagram). Niente YouTube
  (Carlo non ha un canale); @carlo.cavallo.pt e @carlocavallo.coach NON sono il suo Instagram: è @carlocavallocoach.
- Effetti sui pulsanti (blocco "effetti sui pulsanti" in fondo al CSS): verdi si alzano, alone verde e striscia di luce,
  pressione che schiaccia, frecce che scivolano, bordati che si accendono, alone che pulsa sul WhatsApp fisso. Tutto spento con
  prefers-reduced-motion.
- Dati reali dal vecchio sito WordPress: 14 certificazioni, 8 master, Campione Italiano WABBA 2011
  (HP-3), Mr Universo IBFA 2011 (Juniores), docente formazioni ACSI.
- L'app Speed Training Program non esiste più: non citarla sul sito.

## Da fare
- Nulla in sospeso: le prossime modifiche le decide Carlo man mano.
