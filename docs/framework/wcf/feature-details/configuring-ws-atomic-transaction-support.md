---
title: Configurazione del supporto transazioni WS-Atomic
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF], configuring WS-Atomic Transaction
ms.assetid: cb9f1c9c-1439-4172-b9bc-b01c3e09ac48
ms.openlocfilehash: d396ccdaca81eab74de5e20d7ba7a9a00acbf7a6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597475"
---
# <a name="configure-ws-atomic-transaction-support"></a>Configura supporto transazioni WS-Atomic

In questo argomento viene descritto come è possibile configurare il supporto WS-AtomicTransaction (WS-AT) usando l'utilità configurazione WS-AT.

## <a name="use-the-ws-at-configuration-utility"></a>Utilizzare l'utilità di configurazione WS-AT

L'utilità configurazione WS-AT (wsatConfig.exe) viene usata per configurare impostazioni WS-AT. Per abilitare il servizio del protocollo WS-AT è necessario usare l'utilità configurazione per configurare la porta HTTPS per WS-AT, associare un certificato X.509 alla porta HTTPS e configurare certificati partner autorizzati specificando nomi del soggetto o identificazioni personali dei certificati. L'utilità configurazione consente inoltre di selezionare la modalità di traccia e impostare i timeout predefiniti per le transazioni in ingresso e in uscita.

È possibile accedere alla funzionalità di questo strumento usando uno snap-in di pagina delle proprietà MMC (Microsoft Management Console) nella console di gestione Servizi componenti o da una finestra della riga di comando. Configurare il supporto WS-AT sul computer locale tramite la finestra della riga di comando; configurare le impostazioni sul computer locale e su quello remoto usando lo snap-in MMC.

La finestra della riga di comando può essere aperta nel percorso di installazione di Windows SDK "%WINDIR%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation".

Per ulteriori informazioni sullo strumento da riga di comando, vedere l' [utilità di configurazione WS-AtomicTransaction (wsatConfig. exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md).

Se si esegue Windows XP o Windows Server 2003, è possibile accedere allo snap-in MMC passando a **Pannello di controllo/strumenti di amministrazione/Servizi componenti**, facendo clic con il pulsante destro del mouse su **computer locale**e scegliendo **proprietà**. Si tratta dello stesso percorso in cui è possibile configurare Microsoft Distributed Transaction Coordinator (MSDTC). Le opzioni disponibili per la configurazione sono raggruppate nella scheda **WS-at** . Se si esegue Windows Vista o Windows Server 2008, è possibile trovare lo snap-in MMC facendo clic sul pulsante **Avvia** e immettendo `dcomcnfg.exe` nella casella di **ricerca** . Quando si apre MMC, passare al nodo **Computer\Distributed Transaction COORDINATOR\LOCAL DTC** , fare clic con il pulsante destro del mouse e scegliere **Proprietà**. Le opzioni disponibili per la configurazione sono raggruppate nella scheda **WS-at** .

Per ulteriori informazioni sullo snap-in, vedere lo [snap-in MMC configurazione WS-AtomicTransaction](../ws-atomictransaction-configuration-mmc-snap-in.md).

Per abilitare l'interfaccia utente dello strumento è prima necessario registrare il file WsatUI.dll, disponibile nel percorso seguente:

%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin

Per registrare il prodotto, eseguire il comando seguente da una finestra del prompt dei comandi:

`regasm.exe /codebase WsatUI.dll`

## <a name="enable-ws-at"></a>Abilita WS-AT

Per abilitare il servizio del protocollo WS-AT in MSDTC usando la porta 443 e un certificato X.509 con una chiave privata installata nell'archivio del computer locale, usare lo strumento wsatConfig.exe con il comando seguente.

`WsatConfig.exe –network:enable –port:8443 –endpointCert:<machine|"Issuer\SubjectName"> -accountsCerts:<thumbprint|"Issuer\SubjectName"> -restart`

Sostituire i rispettivi parametri con i valori pertinenti per l'ambiente.

Per disabilitare il servizio del protocollo WS-AT in MSDTC, usare lo strumento wsatConfig.exe con il comando seguente.

`WsatConfig.exe –network:disable -restart`

## <a name="configure-trust-between-two-machines"></a>Configurare il trust tra due computer

Il servizio del protocollo WS-AT richiede che l'amministratore autorizzi in modo esplicito singoli account a partecipare alle transazioni distribuite. Gli amministratori di due computer possono configurare entrambi i computer, per stabilire una reciproca relazione di trust, scambiando il corretto set di certificati tra i computer, installando i certificati negli archivi certificati appropriati e usando lo strumento wsatConfig.exe per aggiungere ogni certificato di un computer all'elenco di certificati dei partecipanti autorizzati dell'altro. Questo passaggio è necessario per eseguire transazioni distribuite tra due computer usando WS-AT.

Nell'esempio seguente vengono illustrati i passaggi necessari per stabilire il trust tra due computer, A e B.

### <a name="create-and-export-certificates"></a>Creazione ed esportazione di certificati

Questa procedura richiede lo snap-in MMC Certificati. Per accedere allo snap-in è possibile fare clic sul pulsante Start, scegliere Esegui, digitare "mmc" nella casella di input e fare clic su OK. Quindi, nella finestra **Console1** passare allo snap-in **file/Aggiungi-Rimuovi** , fare clic su Aggiungi e scegliere **certificati** dall'elenco **snap-in autonomo disponibili** . Infine, selezionare **account computer** da gestire e fare clic su **OK**. Il nodo **certificati** verrà visualizzato nella console snap-in.

È necessario già essere in possesso dei certificati necessari per stabilire il trust. Per informazioni su come creare e installare nuovi certificati prima dei passaggi seguenti, vedere [procedura: creare e installare certificati client temporanei in WCF durante lo sviluppo](https://docs.microsoft.com/previous-versions/msp-n-p/ff650751(v=pandp.10)).

1. Sul computer A, usando lo snap-in MMC Certificati, importare il certificato esistente (certA) negli archivi LocalMachine\MY (nodo personale) e LocalMachine\ROOT (nodo Autorità di certificazione radice attendibile). Per importare un certificato in un nodo specifico, fare clic con il pulsante destro del mouse sul nodo e scegliere **tutte le attività/Importa**.

2. Sul computer B, usando lo snap-in MMC Certificati, creare o ottenere un certificato certB con una chiave privata e importarlo negli archivi LocalMachine\MY (nodo personale) e LocalMachine\ROOT (nodo Autorità di certificazione radice attendibile).

3. Se non lo si è già fatto, esportare la chiave pubblica di certA in un file.

4. Se non lo si è già fatto, esportare la chiave pubblica di certB in un file.

### <a name="establish-mutual-trust-between-machines"></a>Stabilire una relazione di trust reciproca tra i computer

1. Sul computer A, importare la rappresentazione del file di certB negli archivi LocalMachine\MY e LocalMachine\ROOT. Si dichiara così che il computer A concede il trust a certB per consentire la comunicazione.

2. Sul computer B, importare il file di certA negli archivi LocalMachine\MY e LocalMachine\ROOT. Questo implica che il computer B concede il trust a certA per consentire la comunicazione.

Dopo avere completato questi passaggi, viene stabilito il trust tra i due computer, che possono quindi essere configurati per la comunicazione reciproca mediante WS-AT.

### <a name="configure-msdtc-to-use-certificates"></a>Configurare MSDTC per l'uso di certificati

Poiché il servizio del protocollo WS-AT funge da client e da server, deve sia ascoltare le connessioni in ingresso sia avviare connessioni in uscita. È quindi necessario configurare MSDTC in modo che sappia quali certificati usare per la comunicazione con parti esterne e quali certificati autorizzare quando si accettano comunicazioni in ingresso.

Per eseguire questa configurazione è possibile usare lo snap-in MMC WS-AT. Per ulteriori informazioni su questo strumento, vedere l'argomento relativo allo [snap-in MMC per la configurazione di WS-AtomicTransaction](../ws-atomictransaction-configuration-mmc-snap-in.md) . Nei passaggi seguenti viene descritto come stabilire un trust tra due computer che eseguono MSDTC.

1. Configurare le impostazioni del computer A. Per "certificato dell'endpoint" selezionare certa. Per "certificati autorizzati" selezionare il certB.

2. Configurare le impostazioni del computer B. Per "certificato dell'endpoint" selezionare certB. Per "certificati autorizzati" selezionare il certificato.

> [!NOTE]
> Quando un computer invia un messaggio all'altro computer, il mittente tenta di verificare che il nome del soggetto del certificato del destinatario e il nome del computer del destinatario corrispondano. Se non corrispondono, la verifica del certificato ha esito negativo e i due computer non possono comunicare.
>
> Per un computer associato a un dominio, il nome corrisponde al nome di dominio completo. Per impostazione predefinita, il nome di un computer in un gruppo di lavoro corrisponde al nome NetBIOS del computer. Tuttavia, il nome può includere un suffisso DNS (Domain Name System), se ne è presente uno per la connessione usata tra i due computer.
>
> Se il nome del computer cambia, come nel caso, ad esempio, di un computer di un gruppo di lavoro che viene associato a un dominio, è necessario rilasciare nuovamente i certificati o configurare manualmente suffissi DNS.

## <a name="security"></a>Sicurezza

Poiché alcune delle impostazioni relative a MSDTC e WS-AT vengono archiviate nel Registro di sistema, rispettivamente in HKLM\Software\Microsoft\MSDTC e HKLM\Software\Microsoft\WSAT, assicurarsi che queste chiavi del Registro di sistema siano protette, in modo che solo gli amministratori possano scrivere in esse. Nello strumento Editor del registro di sistema, fare clic con il pulsante destro del mouse sulla chiave che si desidera proteggere e selezionare l' **autorizzazione** per impostare il controllo di accesso appropriato. È essenziale per la sicurezza e l'integrità del sistema che le chiavi importanti siano di sola lettura per gli utenti con privilegi di basso livello.

Quando si distribuisce MSDTC, l'amministratore deve verificare che qualsiasi scambio di dati MSDTC sia protetto. In una distribuzione in un gruppo di lavoro, isolare l'infrastruttura transazionale dagli utenti malintenzionati; in una distribuzione in cluster, proteggere il Registro di sistema del cluster.

## <a name="tracing"></a>Traccia

Il servizio del protocollo WS-AT supporta la traccia integrata, specifica della transazione, che può essere abilitata e gestita mediante lo strumento di [snap-in MMC configurazione WS-AtomicTransaction](../ws-atomictransaction-configuration-mmc-snap-in.md) . Le tracce possono includere dati che indicano l'ora di creazione di un'integrazione per una specifica transazione, l'ora in cui una transazione raggiunge lo stato finale e il risultato ricevuto da ogni integrazione di transazione. Tutte le tracce possono essere visualizzate tramite lo strumento [Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) .

Il servizio del protocollo WS-AT supporta, inoltre, la traccia ServiceModel integrata tramite la sessione di traccia ETW. Questa funzione fornisce tracce specifiche della comunicazione più dettagliate, oltre alle tracce di transazioni esistenti.  Per attivare queste tracce aggiuntive, eseguire la procedura seguente:

1. Aprire il menu **Start/Esegui** , digitare "regedit" nella casella di input e fare clic su **OK**.

2. Nell' **Editor del registro di sistema**passare alla seguente cartella nel riquadro a sinistra, HKEY_LOCAL_MACHINE \software\microsoft\wsat\3.0\

3. Fare clic con il pulsante destro del mouse sul `ServiceModelDiagnosticTracing` valore nel riquadro di destra e scegliere **modifica**.

4. Nella casella input **dati valore** immettere uno dei valori validi seguenti per specificare il livello di traccia che si desidera abilitare.

- 0: disattivato

- 1: critico

- 3: errore. Si tratta del valore predefinito.

- 7: avviso

- 15: informazioni

- 31: dettagliato

## <a name="see-also"></a>Vedere anche

- [Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [Snap-in di MMC di configurazione WS-AtomicTransaction](../ws-atomictransaction-configuration-mmc-snap-in.md)
