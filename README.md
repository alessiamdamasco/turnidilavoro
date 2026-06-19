# turnidilavoro
la mia turnistica
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestione Turni Ally - Registro Completo</title>
    <style>
        :root {
            --rose-gold: #b76e79;
            --light-rose: #f9f1f2;
            --dark-rose: #8a4f58;
            --gold-gradient: linear-gradient(135deg, #e0b0b6 0%, #b76e79 50%, #8a4f58 100%);
            --white: #ffffff;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #faf6f6;
            margin: 0;
            padding: 0;
            color: #333;
        }

        /* Schermata Login */
        .login-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: var(--gold-gradient);
        }

        .login-main-title {
            color: var(--white);
            font-size: 32px;
            font-weight: 300;
            letter-spacing: 2px;
            margin-bottom: 20px;
            text-shadow: 0 2px 5px rgba(0,0,0,0.15);
        }

        .login-card {
            background: var(--white);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        .login-card h2 {
            color: var(--rose-gold);
            margin-top: 0;
            margin-bottom: 30px;
            font-weight: 400;
            letter-spacing: 1px;
        }

        /* Dashboard */
        .dashboard {
            display: none;
            max-width: 1200px;
            margin: 30px auto;
            padding: 20px;
        }

        header {
            background: var(--gold-gradient);
            color: white;
            padding: 20px;
            border-radius: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 15px rgba(183, 110, 121, 0.3);
            margin-bottom: 30px;
        }

        header h1 { margin: 0; font-weight: 300; }

        .card {
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            border-top: 4px solid var(--rose-gold);
            margin-bottom: 25px;
        }

        .card h3 {
            margin-top: 0;
            color: var(--dark-rose);
            border-bottom: 1px solid var(--light-rose);
            padding-bottom: 10px;
        }

        .input-group {
            margin-bottom: 15px;
            text-align: left;
        }

        .input-group label {
            display: block;
            margin-bottom: 5px;
            color: var(--dark-rose);
            font-weight: 600;
            font-size: 14px;
        }

        input, select {
            width: 100%;
            padding: 12px;
            border: 1px solid #e0b0b6;
            border-radius: 8px;
            box-sizing: border-box;
            background-color: var(--light-rose);
            color: #333;
        }

        input:focus, select:focus {
            outline: none;
            border-color: var(--rose-gold);
        }

        .btn {
            background: var(--gold-gradient);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }

        .btn-secondary { background: #7f8c8d; }
        .btn-danger { background: #c94c4c; }

        /* Widget Stipendio */
        .salary-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            margin-top: 15px;
        }

        .salary-widget {
            background: var(--light-rose);
            border: 1px dashed var(--rose-gold);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
        }

        .salary-amount {
            font-size: 24px;
            font-weight: bold;
            color: var(--dark-rose);
            margin-top: 5px;
        }

        .main-layout {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 30px;
        }

        @media (max-width: 768px) {
            .main-layout { grid-template-columns: 1fr; }
        }

        /* Tabella */
        .table-container { overflow-x: auto; max-height: 500px; border-radius: 8px; }
        table { width: 100%; border-collapse: collapse; }
        th, td { padding: 12px; text-align: left; border-bottom: 1px solid #eededf; }
        th { background-color: var(--light-rose); color: var(--dark-rose); position: sticky; top: 0; }
        tr:hover { background-color: #fdfafb; }

        .badge { padding: 5px 10px; border-radius: 20px; font-size: 11px; font-weight: bold; }
        .badge-goldbet { background: #e3f2fd; color: #0d47a1; }
        .badge-planet { background: #fff3e0; color: #e65100; }

        /* Stile Ricerca Giorno */
        .search-box {
            display: flex;
            gap: 15px;
            align-items: flex-end;
            background: #fffcfc;
            padding: 15px;
            border-radius: 10px;
            border: 1px solid #eededf;
            margin-top: 10px;
        }
        .search-result-box {
            margin-top: 15px;
            padding: 15px;
            border-radius: 8px;
            background-color: #f1f9f5;
            border-left: 5px solid #2ecc71;
            display: none;
        }
    </style>
</head>
<body>

    <!-- SCHERMATA LOGIN -->
    <div id="loginPage" class="login-container">
        <!-- Titolo sopra la pagina di login richiesto -->
        <div class="login-main-title">Gestione turni Ally</div>
        
        <div class="login-card">
            <h2>Accesso Riservato</h2>
            <div class="input-group">
                <label>Username</label>
                <!-- Credenziali rimosse (Campi vuoti) -->
                <input type="text" id="username" placeholder="Inserisci il tuo username">
            </div>
            <div class="input-group">
                <label>Password</label>
                <!-- Credenziali rimosse (Campi vuoti) -->
                <input type="password" id="password" placeholder="Inserisci la tua password">
            </div>
            <button class="btn" style="width:100%; margin-top:10px;" onclick="checkLogin()">Accedi</button>
            <p id="loginError" style="color:red; font-size:14px; display:none; margin-top:15px;">Credenziali errate, Amo!</p>
        </div>
    </div>

    <!-- DASHBOARD PRINCIPALE -->
    <div id="dashboardPage" class="dashboard">
        <header>
            <h1>Registro Turni Personale ✨</h1>
            <button class="btn btn-danger" onclick="logout()">Esci</button>
        </header>

        <!-- STRUMENTO: CERCA UN GIORNO SPECIFICO -->
        <div class="card" style="border-top-color: #3498db;">
            <h3>🔍 Trova Turno per Data Rapida</h3>
            <p style="font-size: 14px; color: #666; margin-top: 0;">Vuoi sapere esattamente cosa hai fatto (o farai) in un giorno specifico? Inserisci la data qui sotto:</p>
            <div class="search-box">
                <div class="input-group" style="margin-bottom: 0; flex: 1;">
                    <label>Scegli il giorno:</label>
                    <input type="date" id="searchDateInput">
                </div>
                <button class="btn" style="background: #3498db;" onclick="cercaGiornoSpecifico()">Cerca Turno</button>
                <button class="btn btn-secondary" onclick="resetCercaGiorno()">Azzera</button>
            </div>
            <div id="searchResult" class="search-result-box">
                <!-- Risultato dinamico della ricerca -->
            </div>
        </div>

        <!-- UTILITY: Sincronizzazione e Caricamento File ICS -->
        <div class="card" style="border-top-color: #27ae60;">
            <h3>🔄 Importa Calendario (.ics)</h3>
            <p style="font-size: 14px; color: #666; margin-top: 0;">Carica un file di esportazione del calendario per unire automaticamente i turni di tutto l'anno.</p>
            <div style="display: flex; gap: 15px; align-items: center; flex-wrap: wrap;">
                <div style="flex: 1; min-width: 250px;">
                    <input type="file" id="icsFileInput" accept=".ics">
                </div>
                <button class="btn" style="background: #27ae60;" onclick="importaFileICS()">Carica ed Elabora</button>
            </div>
            <p id="importFeedback" style="font-weight: bold; color: #27ae60; display: none; margin-top: 10px; font-size: 14px;"></p>
        </div>

        <!-- Filtro Mese/Anno e Resoconto -->
        <div class="card">
            <h3>Filtra Periodo & Guadagni</h3>
            <div class="input-group" style="max-width: 400px;">
                <label>Seleziona il mese da esaminare:</label>
                <select id="periodFilter" onchange="aggiornaVisualizzazione()">
                    <!-- Popolato automaticamente fino a Dicembre 2026 -->
                </select>
            </div>

            <div class="salary-container">
                <div class="salary-widget">
                    <div>Stipendio Base Mensile</div>
                    <div class="salary-amount">850,00 €</div>
                </div>
                <div class="salary-widget">
                    <div>Turni Extra Realizzati (Planetwin365)</div>
                    <div class="salary-amount" id="extraCount">0 turni (+0,00 €)</div>
                </div>
                <div class="salary-widget" style="background: var(--gold-gradient); color: white;">
                    <div style="color: white;">Stipendio Totale del Mese</div>
                    <div class="salary-amount" id="totalSalary" style="color: white;">850,00 €</div>
                </div>
            </div>
        </div>

        <div class="main-layout">
            <!-- Pannello Inserimento / Modifica manuale -->
            <div class="card">
                <h3 id="formTitle">Gestisci Turno</h3>
                <input type="hidden" id="editIndex" value="">
                
                <div class="input-group">
                    <label>Data</label>
                    <input type="date" id="turnoData" required>
                </div>
                <div class="input-group">
                    <label>Sede Posto di Lavoro</label>
                    <select id="turnoSede">
                        <option value="Goldbet stazione">Goldbet stazione</option>
                        <option value="Planetwin365 via Marsala">Planetwin365 via Marsala (Extra +40€)</option>
                    </select>
                </div>
                <div class="input-group">
                    <label>Fascia</label>
                    <select id="turnoFascia">
                        <option value="Mattina">Mattina</option>
                        <option value="Pomeriggio">Pomeriggio</option>
                    </select>
                </div>
                <div class="input-group" style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
                    <div>
                        <label>Ora Inizio</label>
                        <input type="time" id="oraInizio" value="09:00">
                    </div>
                    <div>
                        <label>Ora Fine</label>
                        <input type="time" id="oraFine" value="15:00">
                    </div>
                </div>
                
                <div style="display: flex; gap: 10px; margin-top: 20px;">
                    <button class="btn" style="flex: 1;" onclick="salvaTurno()">Salva Turno</button>
                    <button class="btn btn-secondary" id="btnAnnulla" style="display:none;" onclick="resetForm()">Annulla</button>
                </div>
            </div>

            <!-- Tabella dei turni di quel mese -->
            <div class="card">
                <h3>Elenco Turni del Mese Selezionato</h3>
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Data</th>
                                <th>Sede</th>
                                <th>Fascia</th>
                                <th>Orario Effettivo</th>
                                <th>Azioni</th>
                            </tr>
                        </thead>
                        <tbody id="tabellaTurni">
                            <!-- Righe dinamiche -->
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Database locale persistente
        let turni = JSON.parse(localStorage.getItem('registro_completo_ally')) || [];

        const mesiNomi = ["Gennaio", "Febbraio", "Marzo", "Aprile", "Maggio", "Giugno", "Luglio", "Agosto", "Settembre", "Ottobre", "Novembre", "Dicembre"];

        function popolaSelettoreMesi() {
            const filter = document.getElementById('periodFilter');
            const periodiPresenti = new Set();
            
            turni.forEach(t => { if(t.data) periodiPresenti.add(t.data.substring(0, 7)); });

            // Riempimento automatico fino a Dicembre 2026
            for(let anno = 2024; anno <= 2026; anno++) {
                for(let mese = 1; mese <= 12; mese++) {
                    let mStr = mese < 10 ? '0' + mese : mese;
                    periodiPresenti.add(`${anno}-${mStr}`);
                }
            }

            const ordinati = Array.from(periodiPresenti).sort().reverse();
            filter.innerHTML = '';
            
            ordinati.forEach(p => {
                const [anno, mese] = p.split('-');
                const option = document.createElement('option');
                option.value = p;
                option.innerText = `${mesiNomi[parseInt(mese)-1]} ${anno}`;
                filter.appendChild(option);
            });
            
            const oggiStr = new Date().toISOString().substring(0, 7);
            if (ordinati.includes(oggiStr)) {
                filter.value = oggiStr;
            } else if(ordinati.length > 0) {
                filter.value = ordinati[0];
            }
        }

        function checkLogin() {
            const u = document.getElementById('username').value.trim().toLowerCase();
            const p = document.getElementById('password').value;
            
            // Credenziali da inserire manualmente a schermo vuoto
            if(u === 'ally' && p === 'Monopoli1@') {
                document.getElementById('loginPage').style.display = 'none';
                document.getElementById('dashboardPage').style.display = 'block';
                popolaSelettoreMesi();
                aggiornaVisualizzazione();
            } else {
                document.getElementById('loginError').style.display = 'block';
            }
        }

        function logout() {
            document.getElementById('loginPage').style.display = 'flex';
            document.getElementById('dashboardPage').style.display = 'none';
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
            document.getElementById('loginError').style.display = 'none';
        }

        // FUNZIONE DI RICERCA DI UN GIORNO TOT SPECIFICO
        function cercaGiornoSpecifico() {
            const dataCercata = document.getElementById('searchDateInput').value;
            const resultBox = document.getElementById('searchResult');
            
            if(!dataCercata) {
                alert("Seleziona una data per effettuare la ricerca, Amo!");
                return;
            }

            // Cerca la corrispondenza esatta della data
            const turnoTrovato = turni.find(t => t.data === dataCercata);

            resultBox.style.display = "block";
            
            if(turnoTrovato) {
                const opzioniData = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
                const dataLetta = new Date(dataCercata).toLocaleDateString('it-IT', opzioniData);
                
                resultBox.style.backgroundColor = "#e8f4fd";
                resultBox.style.borderLeft = "5px solid #3498db";
                resultBox.innerHTML = `
                    <p style="margin: 0 0 5px 0; font-weight: bold; color: #2c3e50;">📅 Risultato per ${dataLetta}:</p>
                    <span style="font-size: 15px;">Hai lavorato presso: <b>${turnoTrovato.sede}</b></span><br>
                    <span style="font-size: 15px;">Fascia oraria: <b>${turnoTrovato.fascia}</b> (${turnoTrovato.inizio} - ${turnoTrovato.fine})</span>
                `;
            } else {
                resultBox.style.backgroundColor = "#fdf2f2";
                resultBox.style.borderLeft = "5px solid #e74c3c";
                resultBox.innerHTML = `<p style="margin: 0; color: #c0392b;">Nessun turno registrato nel sistema per il giorno selezionato.</p>`;
            }
        }

        function resetCercaGiorno() {
            document.getElementById('searchDateInput').value = '';
            document.getElementById('searchResult').style.display = "none";
        }

        function aggiornaVisualizzazione() {
            const tbody = document.getElementById('tabellaTurni');
            tbody.innerHTML = '';
            
            const meseSelezionato = document.getElementById('periodFilter').value;
            let conteggioExtraMese = 0;

            let turniFiltrati = turni.filter(t => t.data && t.data.substring(0, 7) === meseSelezionato);
            turniFiltrati.sort((a, b) => new Date(a.data) - new Date(b.data));

            if(turniFiltrati.length === 0) {
                tbody.innerHTML = `<tr><td colspan="5" style="text-align:center; color:#999; padding:20px;">Nessun turno in questo mese. Inseriscilo a mano o usa l'importatore .ics!</td></tr>`;
            }

            turniFiltrati.forEach((turno) => {
                const realIndex = turni.findIndex(t => t === turno);
                if (turno.sede.toLowerCase().includes("planet")) {
                    conteggioExtraMese++;
                }

                let giornoSettimana = new Date(turno.data).toLocaleDateString('it-IT', { weekday: 'short', day: 'numeric' });
                const badgeClass = turno.sede.toLowerCase().includes('goldbet') ? 'badge-goldbet' : 'badge-planet';
                
                const tr = document.createElement('tr');
                tr.innerHTML = `
                    <td><span style="text-transform: capitalize;">${giornoSettimana}</span></td>
                    <td><span class="badge ${badgeClass}">${turno.sede}</span></td>
                    <td>${turno.fascia}</td>
                    <td>${turno.inizio} - ${turno.fine}</td>
                    <td>
                        <button class="btn" style="padding: 4px 8px; font-size:11px; background:#f39c12;" onclick="caricaModifica(${realIndex})">Modifica</button>
                    </td>
                `;
                tbody.appendChild(tr);
            });

            const totaleExtra = conteggioExtraMese * 40;
            document.getElementById('extraCount').innerText = `${conteggioExtraMese} turni extra (+${totaleExtra},00 €)`;
            document.getElementById('totalSalary').innerText = `${850 + totaleExtra},00 €`;
        }

        function importaFileICS() {
            const fileInput = document.getElementById('icsFileInput');
            const feedback = document.getElementById('importFeedback');
            
            if (!fileInput.files || fileInput.files.length === 0) {
                alert("Seleziona prima un file .ics!");
                return;
            }

            const file = fileInput.files[0];
            const reader = new FileReader();

            reader.onload = function(e) {
                const text = e.target.result;
                const veventRegex = /BEGIN:VEVENT([\s\S]*?)END:VEVENT/g;
                let match;
                let turniImportati = 0;

                while ((match = veventRegex.exec(text)) !== null) {
                    const block = match[1];
                    const summaryMatch = block.match(/SUMMARY:(.*)/);
                    const descMatch = block.match(/DESCRIPTION:(.*)/);
                    const dtstartMatch = block.match(/DTSTART(?:;VALUE=DATE)?:?([0-9]{8})/);
                    
                    if (!summaryMatch || !dtstartMatch) continue;

                    const summary = summaryMatch[1].trim();
                    const description = descMatch ? descMatch[1].trim() : "";
                    const dataGreza = dtstartMatch[1]; 
                    
                    if (summary.includes("Turno") || summary.toLowerCase().includes("goldbet") || summary.toLowerCase().includes("planet")) {
                        const anno = dataGreza.substring(0, 4);
                        const mese = dataGreza.substring(4, 6);
                        const giorno = dataGreza.substring(6, 8);
                        const dataFormattata = `${anno}-${mese}-${giorno}`;

                        const esisteGia = turni.some(t => t.data === dataFormattata);
                        if (esisteGia) continue;

                        let fascia = "Mattina";
                        let inizio = "09:00";
                        let fine = "15:00";
                        let sede = "Goldbet stazione";

                        if (summary.includes("Pomeriggio") || description.includes("Pomeriggio")) {
                            fascia = "Pomeriggio";
                            inizio = "15:00";
                            fine = "20:30";
                        }

                        if (summary.toLowerCase().includes("planet") || description.toLowerCase().includes("planet")) {
                            sede = "Planetwin365 via Marsala";
                        }

                        turni.push({ data: dataFormattata, sede, fascia, inizio, fine });
                        turniImportati++;
                    }
                }

                localStorage.setItem('registro_completo_ally', JSON.stringify(turni));
                popolaSelettoreMesi();
                aggiornaVisualizzazione();

                feedback.innerText = `✅ Successo! Aggiunti ${turniImportati} nuovi turni analizzando il file.`;
                feedback.style.display = "block";
            };

            reader.readAsText(file);
        }

        function salvaTurno() {
            const data = document.getElementById('turnoData').value;
            const sede = document.getElementById('turnoSede').value;
            const fascia = document.getElementById('turnoFascia').value;
            const inizio = document.getElementById('oraInizio').value;
            const fine = document.getElementById('oraFine').value;
            const editIndex = document.getElementById('editIndex').value;

            if(!data) return alert("Inserisci la data del turno!");

            const t = { data, sede, fascia, inizio, fine };

            if(editIndex === "") {
                turni.push(t);
            } else {
                turni[editIndex] = t;
            }

            localStorage.setItem('registro_completo_ally', JSON.stringify(turni));
            resetForm();
            popolaSelettoreMesi();
            document.getElementById('periodFilter').value = data.substring(0, 7);
            aggiornaVisualizzazione();
        }

        function caricaModifica(index) {
            const t = turni[index];
            document.getElementById('turnoData').value = t.data;
            document.getElementById('turnoSede').value = t.sede;
            document.getElementById('turnoFascia').value = t.fascia;
            document.getElementById('oraInizio').value = t.inizio;
            document.getElementById('oraFine').value = t.fine;
            
            document.getElementById('editIndex').value = index;
            document.getElementById('formTitle').innerText = "Modifica questo Turno";
            document.getElementById('btnAnnulla').style.display = "inline-block";
        }

        function resetForm() {
            document.getElementById('turnoData').value = '';
            document.getElementById('editIndex').value = '';
            document.getElementById('formTitle').innerText = "Gestisci Turno";
            document.getElementById('btnAnnulla').style.display = "none";
        }
    </script>
</body>
</html>
