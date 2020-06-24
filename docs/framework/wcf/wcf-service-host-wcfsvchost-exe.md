---
title: Host servizio WCF (WcfSvcHost.exe)
description: Utilizzare l'host del servizio WCF per ospitare e testare un servizio implementato. È possibile testare il servizio utilizzando il client di prova WCF o il client.
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: efc9512766d2a9cc814083ab632226d98917bf4e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245726"
---
# <a name="wcf-service-host-wcfsvchostexe"></a>Host servizio WCF (WcfSvcHost.exe)

L'host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare automaticamente un servizio implementato. È quindi possibile testare il servizio utilizzando il client di prova WCF (WcfTestClient.exe) o il client per individuare e correggere eventuali errori potenziali.

## <a name="wcf-service-host"></a>Host servizio WCF

L'host del servizio WCF enumera i servizi in un progetto di servizio WCF, carica la configurazione del progetto e crea un'istanza di un host per ogni servizio rilevato. Lo strumento è integrato in Visual Studio tramite il modello di servizio WCF e viene richiamato quando si avvia il debug del progetto.

Utilizzando l'host del servizio WCF, è possibile ospitare un servizio WCF (in un progetto di libreria di servizi WCF) senza scrivere codice aggiuntivo o eseguire il commit in un host specifico durante lo sviluppo.

> [!NOTE]
> L'host del servizio WCF non supporta l'attendibilità parziale. Se si desidera utilizzare un servizio WCF in attendibilità parziale, non utilizzare il modello di progetto libreria di servizi WCF in Visual Studio per compilare il servizio. È invece possibile creare un nuovo sito Web in Visual Studio scegliendo il modello di sito Web del servizio WCF, che può ospitare il servizio in un server Web in cui è supportato l'attendibilità parziale WCF.

## <a name="project-types-hosted-by-wcf-service-host"></a>Tipi di progetto ospitati da Host servizio WCF

L'host del servizio WCF può ospitare i seguenti tipi di progetto della libreria di servizi WCF: libreria del servizio WCF, libreria di servizi del flusso di lavoro sequenziale, libreria del servizio flusso di lavoro macchina a Stati L'host del servizio WCF può inoltre ospitare i servizi che possono essere aggiunti a un progetto di libreria di servizi utilizzando la funzionalità **Aggiungi elemento** . Sono inclusi il servizio WCF, il servizio macchina a stati WF, il servizio sequenziale WF, il servizio macchina a stati WF XAML e il servizio sequenziale WF XAML.

Tuttavia, è necessario notare che lo strumento non consentirà di configurare un host. Per questa attività, è necessario modificare manualmente il file App.config. Lo strumento non convalida nemmeno i file di configurazione definiti dall'utente.

> [!CAUTION]
> Non è consigliabile utilizzare l'host del servizio WCF per ospitare i servizi in un ambiente di produzione, in quanto non è stato progettato a questo scopo.  L'host del servizio WCF non supporta i requisiti di affidabilità, sicurezza e gestibilità di un ambiente di questo tipo. Utilizzare invece IIS in quanto fornisce migliori funzionalità di affidabilità e monitoraggio ed è la soluzione preferita per i servizi di hosting. Al termine dello sviluppo dei servizi, è necessario eseguire la migrazione dei servizi dall'host del servizio WCF a IIS.

## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>Scenari per l'utilizzo di Host servizio WCF in Visual Studio

La tabella seguente elenca tutti i parametri nella finestra di dialogo **argomenti della riga di comando** , che è possibile trovare facendo clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionando **proprietà**, quindi selezionando la scheda **debug** e facendo clic su **Avvia progetto**. Questi parametri sono utili per la configurazione dell'host del servizio WCF.

|Parametro|Significato|
|---------------|-------------|
|`/client`|Un parametro facoltativo che specifica il percorso di un file eseguibile da eseguire dopo l'hosting dei servizi. Verrà avviato il client di prova WCF in seguito all'hosting.|
|`/clientArg`|Consente di specificare una stringa come argomento che viene passato all'applicazione client personalizzata.|
|`/?`|Visualizza il testo della Guida.|

#### <a name="using-wcf-test-client"></a>Utilizzo di Client di test WCF

Dopo aver creato un nuovo progetto di servizio WCF e premuto F5 per avviare il debugger, l'host del servizio WCF inizia a ospitare tutti i servizi trovati nel progetto. Il client di prova WCF si apre automaticamente e visualizza un elenco di endpoint di servizio definiti nel file di configurazione. Dalla finestra principale, è possibile testare i parametri e richiamare il servizio.

Per assicurarsi che il client di prova WCF venga utilizzato, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **Proprietà**, quindi selezionare la scheda **debug** . fare clic su **Avvia progetto** e verificare che nella finestra di dialogo **argomenti della riga di comando** sia visualizzato quanto segue.

`/client:WcfTestClient.exe`

#### <a name="using-a-custom-client"></a>Utilizzo di un client personalizzato

Per usare un client personalizzato, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **Proprietà**, quindi selezionare la scheda **debug** . fare clic su **Avvia progetto** e modificare il `/client` parametro nella finestra di dialogo **argomenti della riga di comando** per puntare al client personalizzato, come indicato nell'esempio seguente.

`/client:"path/CustomClient.exe"`

Quando si preme F5 per avviare nuovamente il servizio, l'host del servizio WCF avvia automaticamente il client personalizzato quando si avvia il debugger.

È anche possibile utilizzare il parametro `/clientArg:` per specificare una stringa come argomento passato all'applicazione client personalizzata, come indicato nell'esempio seguente.

`/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`

Ad esempio, se si utilizza il modello Libreria di servizi di diffusione, sarà possibile utilizzare gli argomenti della riga di comando seguenti:

`/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`

#### <a name="specifying-no-client"></a>Specifica nessuno client

Per specificare che nessun client verrà utilizzato dopo l'hosting del servizio WCF, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **Proprietà**, quindi selezionare la scheda **debug** . fare clic su **Avvia progetto** e lasciare vuota la finestra di dialogo **argomenti della riga di comando** .

#### <a name="using-a-custom-host"></a>Utilizzo di un host personalizzato

Per usare un host personalizzato, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **Proprietà**, quindi selezionare la scheda **debug** . fare clic su **Avvia programma esterno** e immettere il percorso completo dell'host personalizzato. È inoltre possibile utilizzare la finestra di dialogo **argomenti della riga di comando** per specificare gli argomenti da passare all'host.

## <a name="wcf-service-host-user-interface"></a>Interfaccia utente dell'Host servizio WCF

Quando si richiama inizialmente l'host del servizio WCF (premendo F5 in Visual Studio), viene automaticamente visualizzata la finestra **host servizio WCF** . Quando l'host del servizio WCF è in esecuzione, l'icona del programma viene visualizzata nell'area di notifica. Fare doppio clic sull'icona per aprire la finestra **host del servizio WCF**

Quando si verificano errori durante l'hosting del servizio, viene visualizzata la finestra di dialogo host servizio WCF per visualizzare le informazioni rilevanti.

La finestra principale **host servizio WCF** contiene due menu:

- **File**: contiene i comandi **Close** e **Exit** . Quando si fa clic su **Chiudi**, la finestra di dialogo **host servizio WCF** si chiude, ma i servizi continuano a essere ospitati. Quando si fa clic su **Esci**, viene arrestato anche l'host del servizio WCF. Questo arresta anche tutti i servizi in hosting.

- **Help**: contiene il comando **About** che contiene le informazioni sulla versione. Contiene inoltre il comando della **Guida** che consente di aprire un file della guida.

La finestra principale dell' **host del servizio WCF** contiene due aree:

- La prima area è **Service**. Contiene un elenco che visualizza informazioni di base su tutti i servizi. Le informazioni includono:

  - **Servizio**: elenca tutti i servizi.

  - **Stato**: elenca lo stato del servizio. I valori validi sono "Started", "Stopped" ed "Error".

  - **Indirizzo metadati**: Visualizza l'indirizzo dei metadati dei servizi.

- La seconda area è **informazioni aggiuntive**. Viene visualizzata una spiegazione dettagliata dello stato del servizio quando la riga di servizio specifica è selezionata nell'area **servizio** . Se lo stato è Errore, è possibile visualizzare il messaggio di errore completo sullo schermo.

## <a name="stopping-wcf-service-host"></a>Interruzione dell'Host servizio WCF

È possibile arrestare l'host del servizio WCF nei quattro modi seguenti:

- Arrestare la sessione di debug in Visual Studio.

- Selezionare **Esci** dal menu **file** nella finestra **host servizio WCF** .

- Selezionare **Esci** dal menu di scelta rapida dell'icona della barra degli host del servizio WCF nell'area di notifica del sistema.

- Uscire da client di prova WCF se viene usato.

## <a name="using-service-host-without-administrator-privilege"></a>Utilizzo di Host servizio senza privilegio di amministratore

Per consentire agli utenti senza privilegi di amministratore di sviluppare servizi WCF, viene creato un ACL (elenco di controllo di accesso) per lo spazio dei nomi " http://+:8731/Design_Time_Addresses " durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o rimuovere utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL consente agli utenti di utilizzare l'host automatico del servizio WCF (wcfSvcHost.exe) senza concedere loro privilegi di amministratore.

È possibile modificare l'accesso utilizzando lo strumento netsh.exe in Windows Vista con l'account amministratore con privilegi elevati. Di seguito è riportato un esempio dell'utilizzo di netsh.exe.

```console
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>
```

Per ulteriori informazioni su netsh.exe, vedere "[come utilizzare lo strumento Netsh.exe e le opzioni della riga di comando](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))".

## <a name="see-also"></a>Vedi anche

- [Client di prova WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
