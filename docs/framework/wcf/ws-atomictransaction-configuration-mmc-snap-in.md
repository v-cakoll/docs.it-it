---
title: Snap-in MMC di configurazione di WS-AtomicTransaction
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: 0bcd08f9a3450c850ead941df6313526d076df2d
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921339"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a>Snap-in MMC configurazione WS-AtomicTransaction

Lo snap-in MMC configurazione WS-AtomicTransaction viene utilizzato per configurare una parte delle impostazioni di WS-AtomicTransaction nei computer locali e remoti.

## <a name="remarks"></a>Note

Se si esegue Windows XP o Windows Server 2003, è possibile trovare lo snap-in MMC passando a **Pannello di controllo/strumenti di amministrazione/Servizi componenti/** , facendo clic con il pulsante destro del mouse su **computer locale**e scegliendo **proprietà**. Si tratta dello stesso percorso nel quale è possibile configurare MSDTC. Le opzioni disponibili per la configurazione sono raggruppate nella scheda **WS-at** .

 Se si esegue Windows Vista o Windows Server 2008, è possibile trovare lo snap-in MMC facendo clic sul pulsante **Start** e digitando `dcomcnfg.exe` nella casella di **ricerca** . Quando si apre MMC, passare al nodo **Computer\Distributed Transaction COORDINATOR\LOCAL DTC** , fare clic con il pulsante destro del mouse e scegliere **Proprietà**. Le opzioni disponibili per la configurazione sono raggruppate nella scheda **WS-at** .

 I passaggi precedenti vengono utilizzati per avviare lo snap-in per la configurazione di un computer locale. Se si desidera configurare un computer remoto, è necessario individuare il nome del computer remoto nel **Pannello di controllo/strumenti di amministrazione/Servizi componenti/** ed eseguire operazioni simili se si esegue Windows XP o windows Server 2003. Se si esegue Windows Vista o Windows Server 2008, seguire i passaggi precedenti per vista e Windows Server 2008, ma usare il nodo **Distributed Transaction COORDINATOR\LOCAL DTC** nel nodo del computer remoto.

 Per usare l'interfaccia fornita dallo strumento è necessario registrare il file WsatUI.dll, disponibile nel percorso seguente:

 **%Programmi%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**

 La registrazione può essere effettuata con il comando seguente:

```console
regasm.exe /codebase WsatUI.dll
```

 È possibile utilizzare questo strumento per modificare le impostazioni di base WS-AtomicTransaction. Ad esempio, è possibile abilitare e disabilitare il supporto del protocollo WS-AtomicTransaction, configurare le porte HTTP per WS-AT, associare un Certificato SSL alla porta HTTP, configurare certificati specificando nomi dell’oggetto del certificato, selezionare la modalità Analisi e impostare i timeout massimi e predefiniti.

 Se è necessario configurare il supporto di WS-AtomicTransaction solo sul computer locale, è possibile usare la versione della riga di comando di questo strumento. Per ulteriori informazioni sullo strumento da riga di comando, vedere l'argomento relativo all' [utilità di configurazione WS-AtomicTransaction (wsatConfig. exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md) .

 È necessario tenere presente che Snap-in MMC e lo strumento della riga di comando, non supportano la configurazione di tutte le impostazioni WS-AT. Queste impostazioni possono essere modificate solo modificando direttamente il Registro di sistema. Per ulteriori informazioni su queste impostazioni del registro di sistema, vedere [configurazione del supporto per transazioni WS-Atomic](./feature-details/configuring-ws-atomic-transaction-support.md).

### <a name="user-interface-description"></a>Descrizione dell'interfaccia utente

**Abilita supporto di rete WS-Atomic Transaction**:

 L’attivazione di questa casella di comando abilita o disabilita tutti i componenti GUI di questo snap-in.

 Prima di selezionare questa casella, è necessario assicurarsi che l’accesso alla rete DTC sia abilitato con comunicazione in entrata e/o in uscita. Questo valore può essere verificato nella scheda **sicurezza** dello snap-in MSDTC.

#### <a name="network-group-box"></a>Casella di gruppo di rete

È possibile specificare la porta HTTPS e impostazioni di sicurezza aggiuntive, ad esempio crittografia SSL, nel gruppo della Rete. Questo gruppo è disabilitato (visualizzato in grigio) se le transazioni di rete DTC non sono state abilitate.

 **Porta HTTPS**

 Si tratta del valore della porta HTTPS utilizzata per WS-AT. Il valore deve essere un numero compreso nell'intervallo da 1 a 65535 (per rappresentare una porta valida). Cambiando la porta HTTP si modifica la configurazione del servizio http, di conseguenza l’indirizzo di servizio WS-AT precedentemente utilizzato viene  Servizio Indirizzo usato viene rilasciato e viene registrato un nuovo indirizzo di servizio WS-AT in base alla nuova porta. La porta appena selezionata è inoltre crittografata con il certificato attualmente selezionato per la Crittografia SSL.

> [!NOTE]
> Se prima di eseguire questo strumento è già stato abilitato il firewall, la porta viene automaticamente registrata nell'elenco delle eccezioni. Se il firewall è stato disabilitato prima di eseguire questo strumento, non verranno configurati elementi aggiuntivi riguardanti il firewall.

 Se si abilita il firewall dopo aver configurato WS-AT, sarà necessario eseguire di nuovo questo strumento e fornire il numero della porta che utilizza questo parametro. Se si disabilita il firewall dopo la configurazione, WS-AT rimarrà in funzione senza input aggiuntivo.

 **Certificato endpoint**

 Facendo clic sul pulsante **Seleziona** viene visualizzato un elenco con i certificati attualmente disponibili nel computer locale, consentendo all'utente di selezionare il certificato che può essere utilizzato per la crittografia SSL. I certificati devono disporre di una chiave privata. In caso contrario, viene generato un messaggio di errore.

> [!NOTE]
> Impostando un certificato SSL per una porta selezionata, il certificato SSL originale associato a quella porta, se presente, viene sovrascritto.

 **Account autorizzati**

 Facendo clic sul pulsante **Seleziona** viene richiamato l'editor dell'elenco di controllo di accesso di Windows, in cui è possibile specificare l'utente o il gruppo che può partecipare alle transazioni WS-Atomic selezionando la casella **Consenti** o **Nega** nel gruppo di autorizzazioni **partecipa** .

 **Certificati autorizzati**

 Facendo clic sul pulsante **Seleziona** viene visualizzato un elenco dei certificati attualmente disponibili nel LocalMachine. È quindi possibile selezionare quali identità del certificato possono partecipare nelle transazioni WS-Atomic.

#### <a name="timeout-group-box"></a>Casella di gruppo Timeout

La casella di gruppo **timeout** consente di specificare il timeout predefinito e massimo per una transazione WS-Atomic. Un valore valido per il timeout in uscita è compreso tra 1 e 3600. Un valore valido per il timeout in entrata è compreso tra 0 e 3600.

#### <a name="tracing-and-logging-group-box"></a>Casella di gruppo Traccia e registrazione

La casella di gruppo **traccia e registrazione** consente di configurare il livello di traccia e di registrazione desiderato.

 Facendo clic sul pulsante **Opzioni** viene richiamata una pagina in cui è possibile specificare impostazioni aggiuntive.

 La casella combinata **livello traccia** consente di scegliere tra qualsiasi valore valido dell'enumerazione <xref:System.Diagnostics.TraceLevel>. È inoltre possibile utilizzare le caselle di controllo per specificare se si desidera eseguire attività di traccia, propagazione di attività o raccogliere informazioni identificabili personali.

 È inoltre possibile specificare sessioni di registrazione nella casella di gruppo **sessione di registrazione** .

> [!NOTE]
> Quando il provider di traccia WS-AT è utilizzato da un altro consumer di traccia, non è possibile creare una nuova sessione di registrazione per gli eventi di traccia. Se si tenta di configurare la registrazione in questo momento verrà generato il messaggio di errore non “Errore durante l’abilitazione del provider”. Codice di errore: 1”.

 Per ulteriori informazioni sulla traccia e la registrazione, vedere [amministrazione e diagnostica](./diagnostics/index.md).

## <a name="see-also"></a>Vedere anche

- [Configurazione del supporto di transazioni WS-Atomic](./feature-details/configuring-ws-atomic-transaction-support.md)
- [Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [Amministrazione e diagnostica](./diagnostics/index.md)
