---
title: Snap-in MMC di configurazione di WS-AtomicTransaction
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: b1d86fa57b31d1f9be12f76c28f9d042e7e28e24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052560"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a>Snap-in MMC di configurazione di WS-AtomicTransaction
Lo Snap-in MMC di Configurazione di WS-AtomicTransaction è utilizzato per configurare una parte delle impostazioni WS-AtomicTransaction su computer locali e remoti.  
  
## <a name="remarks"></a>Note  
 Se si esegue [!INCLUDE[wxp](../../../includes/wxp-md.md)] oppure [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], lo snap-in MMC è reperibile passando a **controllo pannello/Administrative Tools/Servizi componenti /**, facendo **risorse del Computer**, e selezionando **proprietà**. Si tratta dello stesso percorso nel quale è possibile configurare MSDTC. Le opzioni disponibili per la configurazione vengono raggruppate sotto la **WS-AT** scheda.  
  
 Se si sta eseguendo Windows Vista o [!INCLUDE[lserver](../../../includes/lserver-md.md)], snap-in MMC sono reperibili facendo il **avviare** e digitando nella `dcomcnfg.exe` nel **ricerca** casella. Quando viene aperta la console MMC, passare al **risorse del Computer\Distributed Transaction COORDINATOR\DTC locale** nodo, fare clic e selezionare **proprietà**. Le opzioni disponibili per la configurazione vengono raggruppate sotto la **WS-AT** scheda.  
  
 I passaggi precedenti vengono utilizzati per avviare lo snap-in per la configurazione di un computer locale. Se si desidera configurare un computer remoto, è necessario individuare il nome del computer remoto in **controllo pannello/Administrative Tools/Servizi componenti /** e seguire una procedura simile se si esegue [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Se si sta eseguendo Windows Vista o [!INCLUDE[lserver](../../../includes/lserver-md.md)], seguire i passaggi precedenti per Vista e [!INCLUDE[lserver](../../../includes/lserver-md.md)], ma utilizzare il **Distributed Transaction Coordinator/DTC** nodo sotto il nodo del computer remoto.  
  
 Per usare l'interfaccia fornita dallo strumento è necessario registrare il file WsatUI.dll, disponibile nel percorso seguente:  
  
 **%ProgramFiles%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**  
  
 La registrazione può essere effettuata con il comando seguente:  
  
```Output  
regasm.exe /codebase WsatUI.dll  
```  
  
 È possibile utilizzare questo strumento per modificare le impostazioni di base WS-AtomicTransaction. Ad esempio, è possibile abilitare e disabilitare il supporto del protocollo WS-AtomicTransaction, configurare le porte HTTP per WS-AT, associare un Certificato SSL alla porta HTTP, configurare certificati specificando nomi dell’oggetto del certificato, selezionare la modalità Analisi e impostare i timeout massimi e predefiniti.  
  
 Se è necessario configurare il supporto di WS-AtomicTransaction solo sul computer locale, è possibile utilizzare la versione da riga di comando di questo strumento. Per altre informazioni sullo strumento della riga di comando, vedere la [utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md) argomento.  
  
 È necessario tenere presente che Snap-in MMC e lo strumento della riga di comando, non supportano la configurazione di tutte le impostazioni WS-AT. Queste impostazioni possono essere modificate solo modificando direttamente il Registro di sistema. Per altre informazioni su queste impostazioni del Registro di sistema, vedere [configurazione del supporto transazioni WS-Atomic](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
### <a name="user-interface-description"></a>Descrizione dell'interfaccia utente  
 **Abilitare il supporto di rete WS-Atomic Transaction**:  
  
 L’attivazione di questa casella di comando abilita o disabilita tutti i componenti GUI di questo snap-in.  
  
 Prima di selezionare questa casella, è necessario assicurarsi che l’accesso alla rete DTC sia abilitato con comunicazione in entrata e/o in uscita. Questo valore può essere verificato nel **sicurezza** scheda dello snap-in MSDTC.  
  
#### <a name="network-group-box"></a>Casella di gruppo di rete  
 È possibile specificare la porta HTTPS e impostazioni di sicurezza aggiuntive, ad esempio crittografia SSL, nel gruppo della Rete. Questo gruppo è disabilitato (visualizzato in grigio) se le transazioni di rete DTC non sono state abilitate.  
  
 **Porta HTTPS**  
  
 Si tratta del valore della porta HTTPS utilizzata per WS-AT. Il valore deve essere un numero compreso nell'intervallo da 1 a 65535 (per rappresentare una porta valida). Cambiando la porta HTTP si modifica la configurazione del servizio http, di conseguenza l’indirizzo di servizio WS-AT precedentemente utilizzato viene  Servizio Indirizzo usato viene rilasciato e viene registrato un nuovo indirizzo di servizio WS-AT in base alla nuova porta. La porta appena selezionata è inoltre crittografata con il certificato attualmente selezionato per la Crittografia SSL.  
  
> [!NOTE]
>  Se prima di eseguire questo strumento è già stato abilitato il firewall, la porta viene automaticamente registrata nell'elenco delle eccezioni. Se il firewall è stato disabilitato prima di eseguire questo strumento, non verranno configurati elementi aggiuntivi riguardanti il firewall.  
  
 Se si abilita il firewall dopo aver configurato WS-AT, sarà necessario eseguire di nuovo questo strumento e fornire il numero della porta che utilizza questo parametro. Se si disabilita il firewall dopo la configurazione, WS-AT rimarrà in funzione senza input aggiuntivo.  
  
 **Certificato dell'endpoint**  
  
 Scegliere il **seleziona** pulsante viene visualizzato un elenco dei certificati attualmente disponibili nel computer locale, consentendo all'utente di selezionare il certificato che può essere utilizzato per la crittografia SSL. I certificati devono disporre di una chiave privata. In caso contrario, viene generato un messaggio di errore.  
  
> [!NOTE]
>  Impostando un certificato SSL per una porta selezionata, il certificato SSL originale associato a quella porta, se presente, viene sovrascritto.  
  
 **Account autorizzati**  
  
 Facendo clic sul **seleziona** pulsante richiama l'editor elenco di controllo di accesso di Windows, in cui è possibile specificare l'utente o gruppo che può partecipare nelle transazioni WS-Atomic selezionando il **Consenti** o**Deny** nella casella il **partecipa** gruppo di autorizzazioni.  
  
 **Certificati autorizzati**  
  
 Scegliere il **selezionare** pulsante viene visualizzato un elenco dei certificati attualmente disponibili su LocalMachine. È quindi possibile selezionare quali identità del certificato possono partecipare nelle transazioni WS-Atomic.  
  
#### <a name="timeout-group-box"></a>Casella di gruppo Timeout  
 Il **Timeout** casella di gruppo consente di specificare il timeout predefinito e massimo per una transazione WS-Atomic. Un valore valido per il timeout in uscita è compreso tra 1 e 3600. Un valore valido per il timeout in entrata è compreso tra 0 e 3600.  
  
#### <a name="tracing-and-logging-group-box"></a>Casella di gruppo Traccia e registrazione  
 Il **traccia e registrazione** casella di gruppo consente di configurare il livello di registrazione e traccia desiderata.  
  
 Facendo clic sui **opzioni** quest'ultimo richiama una pagina in cui è possibile specificare impostazioni aggiuntive.  
  
 Il **livello di traccia** combinazione consente di scegliere un valore valido del <xref:System.Diagnostics.TraceLevel> enumerazione. È inoltre possibile utilizzare le caselle di controllo per specificare se si desidera eseguire attività di traccia, propagazione di attività o raccogliere informazioni identificabili personali.  
  
 È inoltre possibile specificare sessioni di registrazione nella **sessione di registrazione** casella di gruppo.  
  
> [!NOTE]
>  Quando il provider di traccia WS-AT è utilizzato da un altro consumer di traccia, non è possibile creare una nuova sessione di registrazione per gli eventi di traccia. Se si tenta di configurare la registrazione in questo momento verrà generato il messaggio di errore non “Errore durante l’abilitazione del provider”. Codice di errore: 1".  
  
 Per altre informazioni sull'analisi e la registrazione, vedere [amministrazione e diagnostica](../../../docs/framework/wcf/diagnostics/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione del supporto di transazioni WS-Atomic](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
- [Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [Amministrazione e diagnostica](../../../docs/framework/wcf/diagnostics/index.md)
