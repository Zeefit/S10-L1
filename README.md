### Passaggi Principali

1. **Installazione e Configurazione Iniziale**
   - Installare **Splunk Forwarder** su **Windows 10**.  
   - Installare **Splunk Enterprise** su **Windows Server 2022**.  
   - Configurare una porta di ascolto per consentire la ricezione dei log dal Forwarder.

2. **Impostazione del Forwarder**
   - Accedere alle impostazioni di Splunk Enterprise:  
     - Navigare in **Impostazioni > Inoltro e Ricezione > Configura Ricezione**.  
   - Abilitare la porta configurata per la ricezione.

3. **Aggiunta di Dati e Configurazione della Modalità Monitora**
   - Tornare alla homepage di Splunk e selezionare **Aggiungi Dati**.  
   - Scegliere la modalità **Monitora**.  
   - Selezionare l'evento di interesse, ad esempio **Security**, per raccogliere i log di sicurezza di Windows.

4. **Modifica delle Impostazioni degli Input**
   - Nella schermata di configurazione, sostituire l'host predefinito con un comando che includa più host, ad esempio:  
     ```plaintext
     source="WinEventLog:*" host="DESKTOP-9K104BT" OR host="WIN-4J600U41GIE"
     ```
   - Questo permette di includere dati da entrambi gli host configurati.

5. **Avvio della Ricerca**
   - Eseguire la ricerca e verificare che i log siano stati raccolti correttamente.  
   - I log saranno categorizzati come **Security** e organizzati per host, fornendo una visione dettagliata degli eventi monitorati.

6. **Conferma della Connessione**
   - Osservare che l'hostname (es. **Windows 10 Pro**) corrisponda alla macchina configurata con il Forwarder, confermando che la connessione tra i due sistemi sia attiva.

---

### Extra: Personalizzazione delle Query
- Scrivere query manuali per filtri specifici o combinazioni di host.
- Sfruttare l'interfaccia GUI di Splunk per selezionare campi di interesse e generare query automaticamente.
