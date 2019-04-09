---
title: Interpretazione dei codici errore restituiti da wsatConfig.exe
ms.date: 03/30/2017
ms.assetid: ab65f22b-0d69-4c21-9aaf-74acef0ca102
ms.openlocfilehash: 47db39f2b350c2fa8c655a041ec0239e5d297644
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151632"
---
# <a name="interpreting-error-codes-returned-by-wsatconfigexe"></a>Interpretazione dei codici errore restituiti da wsatConfig.exe
Questo argomento elenca tutti i codici errore generati dall'utilità di configurazione WS-AtomicTransaction (wsatConfig.exe) e azioni consigliate da intraprendere.  
  
## <a name="list-of-error-codes"></a>Elenco dei codici di errore  
  
|Codice di errore|Descrizione|Azione consigliata da intraprendere|  
|----------------|-----------------|------------------------------------|  
|0|L'operazione è stata completata|nessuno|  
|1|Errore imprevisto|Contattare Microsoft|  
|2|Si è verificato un errore imprevisto durante il tentativo di contattare MSDTC per recuperare le impostazioni di sicurezza.|Assicurarsi che il servizio MSDTC non sia disabilitato e risolvere tutti i problemi elencati nell’Eccezione restituita.|  
|3|L'account nel quale è stato eseguito WsatConfig.exe non dispone delle autorizzazioni necessarie per leggere le impostazioni di sicurezza di rete.|Eseguire WsatConfig.exe in un account utente dell'Amministratore.|  
|4|Abilitare “Accesso rete DTC” per MSDTC prima di tentare di abilitare il supporto WS-AT.|Abilitare “Accesso rete DTC” per MSDTC ed eseguire nuovamente l'utilità.|  
|5|Porta di accesso esterna all'intervallo. Il valore deve essere compreso nell'intervallo 1-65535.|Correggere il `-port:<portNum>`<br /><br /> opzione della riga di comando come indicato nel messaggio di errore.|  
|6|Un certificato dell'endpoint non valido è stato specificato sulla riga di comando.  Non è stato possibile individuare un certificato o non ha superato la verifica.|Correggere l'opzione della riga di comando `-endpointCert`. Assicurarsi che il certificato abbia una chiave privata, sia destinato a ClientAuthentication e ServerAuthentication, sia installato nell'archivio certificati LocalMachine\MY e sia completamente attendibile.|  
|7|Un certificato account non valido è stato specificato sulla riga di comando.|Correggere l'opzione della riga di comando `-accountsCerts`. Il certificato specificato non è stato correttamente specificato o non è stato possibile trovarlo.|  
|8|Un timeout predefinito è stato specificato al di fuori dell'intervallo di 1 a 3600 secondi.|Immettere un valore di timeout predefinito corretto come indicato.|  
|10|Si è verificato un errore imprevisto nel tentativo di accesso al Registro di sistema.|Verificare messaggio di errore e codice errore ed eventuali elementi eseguibili|  
|11|Impossibile scrivere nel Registro di sistema.|Assicurarsi che la chiave elencata nel messaggio di errore sia capace di supportare l’accesso al Registro di sistema da parte dell’account WsatConfig.exe di esecuzione.|  
|12|Si è verificato un errore imprevisto nel tentativo di accesso all’archivio certificati.|Utilizzare il codice errore restituito per eseguire il mapping all'errore di sistema adatto.|  
|13|La configurazione di http.sys non è riuscita. Impossibile creare una nuova prenotazione della porta HTTPS per MSDTC.|Utilizzare il codice errore restituito per eseguire il mapping all'errore di sistema adatto.|  
|14|La configurazione di http.sys non è riuscita. Impossibile rimuovere la precedente prenotazione della porta HTTPS per MSDTC.|Utilizzare il codice errore restituito per eseguire il mapping all'errore di sistema adatto.|  
|15|La configurazione di http.sys non è riuscita. Esiste già una prenotazione della porta HTTPS precedente per la porta specificata.|Un'altra applicazione è già diventata proprietaria della porta specifica. Cambiare porta o disinstallare o riconfigurare l'applicazione corrente.|  
|16|La configurazione di http.sys non è riuscita. Impossibile effettuare l'associazione del certificato specifico alla porta.|Utilizzare il codice errore restituito nel messaggio di errore per eseguire il mapping all'errore di sistema adatto.|  
|17|La configurazione di http.sys non è riuscita. Impossibile separare il certificato SSL dalla porta precedente.|Utilizzare il codice errore restituito nel messaggio di errore per eseguire il mapping all'errore di sistema adatto. Se necessario, utilizzare httpcfg.exe o netsh.exe per rimuovere la prenotazione della porta errata.|  
|18|La configurazione di http.sys non è riuscita. Impossibile associare il certificato specificato alla porta in quanto esiste già un'associazione SSL precedente.|Un'altra applicazione è già diventata proprietaria della porta specifica. Cambiare porta o disinstallare o riconfigurare l'applicazione corrente.|  
|19|Il riavvio di MSDTC non è riuscito|Riavviare manualmente MSDTC se necessario. Se il problema persiste, contattare Microsoft.|  
|20|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] non è installato nel computer remoto oppure non è installato correttamente.|Installare [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] sul computer.|  
|21|La configurazione remota non è riuscita in quanto l'operazione è scaduta.|La chiamata per configurare WS-AT sul computer remoto richiede più di 90 secondi.|  
|22|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] non è installato nel computer remoto oppure non è installato correttamente.|Installare [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] sul computer.|  
|23|La configurazione remota non è riuscita a causa di un'eccezione sul computer remoto.|Verificare il messaggio di errore per gli elementi eseguibili|  
|26|È stato passato un argomento non valido a WsatConfig.exe.|Verificare eventuali errori nella riga di comando.|  
|27|Opzione della riga di comando `-accounts` non valida.|Correggere l'opzione della riga di comando -`accounts` per specificare correttamente un account utente.|  
|28|Opzione della riga di comando `-network` non valida.|Correggere l'opzione della riga di comando `-network` per specificare correttamente "abilita" o "disabilita".|  
|29|Opzione della riga di comando `-maxTimeout` non valida.|Correggere l'opzione della riga di comando `-maxTimeout`come indicato. |  
|30|Opzione della riga di comando `-timeout` non valida.|Correggere l'opzione della riga di comando `-timeout`come indicato. |  
|31|Opzione della riga di comando `-traceLevel` non valida.|Correggere l'opzione della riga di comando `-traceLevel` per specificare uno dei seguenti valori validi:<br /><br /> -   Off<br />-Errore<br />-   Critico<br />-Avviso<br />-Informazioni<br />-Verbose<br />-Tutte|  
|32|Opzione della riga di comando `-traceActivity` non valida.|Correggere l'opzione della riga di comando `-traceActivity` specificando "abilita" o "disabilita".|  
|33|Opzione della riga di comando `-traceProp` non valida.|Correggere l'opzione della riga di comando `-traceProp` specificando "abilita" o "disabilita".|  
|34|Opzione della riga di comando `-tracePII` non valida.|Correggere l'opzione della riga di comando `-tracePII` specificando "abilita" o "disabilita".|  
|37|WsatConfig.exe non è stato in grado di determinare il certificato del computer esatto. Questo potrebbe verificarsi quando esiste più di un candidato o quando non ne esiste nessuno.|Specificare un'identificazione digitale o una coppia Issuer\SubjectName per identificare correttamente il certificato esatto da configurare.|  
|38|Il processo o l'utente non dispone delle autorizzazioni sufficienti per modificare la configurazione del firewall.|Eseguire WsatConfig.exe in un account utente dell'Amministratore.|  
|39|Errore riscontrato da WsatConfig.exe durante l’aggiornamento della configurazione del firewall.|Verificare il messaggio di errore per gli elementi eseguibili.|  
|40|WsatConfig.exe non è in grado di dare accesso in lettura MSDTC al file di chiave privata del certificato|Eseguire WsatConfig.exe in un account utente dell'Amministratore.|  
|41|Non è stata individuata alcuna installazione di [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] o la versione trovata non corrisponde alla funzionalità di configurazione dello strumento.|Assicurarsi che [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] sia installato correttamente e utilizzare soltanto lo strumento WsatConfig.exe fornito con tale versione di [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] per configurare WS-AT.|  
|42|Lo stesso argomento è stato specificato più volte nella riga di comando.|Specificare un solo argomento per volta nell'esecuzione di WsatConfig.exe.|  
|43|WsatConfig.exe non può aggiornare impostazioni WS-AT se WS-AT non è abilitato.|Specificare `-network:enable` come argomento della riga di comando aggiuntivo.|  
|44|L’aggiornamento rapido necessario è mancante e WS-AT non può essere configurato finché non viene installato l’aggiornamento rapido.|Vedere le note sulla versione di [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] per istruzioni sull'installazione dell'hotfix necessario.|  
|45|Opzione della riga di comando `-virtualServer` non valida.|Correggere l'opzione della riga di comando `-virtualServer` specificando il nome di rete della risorsa cluster in cui eseguire la configurazione.|  
|46|Si è verificato un errore imprevisto nel tentativo di avvio della sessione di traccia ETW|Utilizzare il codice errore restituito per eseguire il mapping all'errore di sistema adatto.|  
|47|Il processo o l’utente non dispongono delle autorizzazioni necessarie per abilitare la sessione di traccia ETW.|Eseguire WsatConfig.exe in un account utente dell'Amministratore.|  
|48|Si è verificato un errore imprevisto nel tentativo di avvio della sessione di traccia ETW.|Contattare Microsoft.|  
|49|Impossibile creare un file di log nuovo a causa di spazio insufficiente su %systemdrive%|Assicurarsi che vi sia spazio sufficiente in %systemdrive% per il file di log.|  
|51|Si è verificato un errore imprevisto nel tentativo di avvio della sessione di traccia ETW.|Contattare Microsoft.|  
|52|Si è verificato un errore imprevisto nel tentativo di avvio della sessione di traccia ETW.|Contattare Microsoft.|  
|53|Backup del file di log della sessione ETW precedente non è riuscito.|Assicurarsi che vi sia spazio sufficiente in %systemdrive% per il file di log e per il backup del file di log precedente (se presente). Rimuovere manualmente il file di log precedente se necessario.|  
|55|Si è verificato un errore imprevisto nel tentativo di avvio della sessione di traccia ETW.|Contattare Microsoft.|  
|56|Si è verificato un errore imprevisto nel tentativo di avvio della sessione di traccia ETW.|Contattare Microsoft.|  
  
## <a name="see-also"></a>Vedere anche

- [Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
