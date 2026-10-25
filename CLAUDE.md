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

## Contenuti
- Design: sfondo scuro #0E0F0C, accento verde lime #C6F432 (variabili CSS in `:root`),
  font Archivo (titoli) + Manrope (testo). Responsive, menu a scomparsa sotto 900px.
- Sezioni: hero, numeri, "Si sono allenati con me" (foto VIP), servizi, "I miei centri", Coaching Online,
  risultati, chi sono (certificazioni e master), modulo contatti, footer.
- WhatsApp: numero 393775247736 (variabile `WHATSAPP` nello script in fondo). Il modulo apre
  WhatsApp con nome, telefono, obiettivo e servizio già scritti.
- Foto VIP (`img/vip-1..5.webp`) prese dal repo `sito-fitpointactive`:
  1 Francesca Tocca, 2 Martina Colombari, 3 Billy Costacurta, 4 Andrea Iannone, 5 Gianni Sperti.
- Foto VIP mostrate come su fitpointactive.com (griglia, nome grande in maiuscolo). vip-4 non ha didascalia:
  il nome di Iannone è già scritto nella foto.
- "I miei centri": FitPoint Active, C Club, Girl Power con link alle pagine di www.fitpointactive.com.
  Loghi e foto (`logo-*.webp`, `fp-sala-pesi`, `cclub-lat-machine`, `gp-sala-blu`) copiati dal repo
  `sito-fitpointactive`, che non va modificato da qui.
- Foto hero: `img/carlo-hero.webp` (quadrata, Carlo con i loghi dei centri e dello Store), mostrata
  intera, senza riquadri sopra. `img/og-carlo.jpg` è la stessa foto per l'anteprima social.
- Dati reali dal vecchio sito WordPress: 14 certificazioni, 8 master, Campione Italiano WABBA 2011
  (HP-3), Mr Universo IBFA 2011 (Juniores), docente formazioni ACSI, app Speed Training Program.

## Da fare
- Sezione "Risultati": i testi tra [parentesi quadre] sono segnaposto. Servono 3 recensioni vere
  con foto prima/dopo. Non inventare recensioni o numeri.
