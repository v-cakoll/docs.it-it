---
title: Pubblicazione servizio WCF
description: La pubblicazione del servizio WCF consente di distribuire l'applicazione in un ambiente di produzione a scopo di test.
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 99798b75e1dc01c8db361f4d8d1f162c7f7617b1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245674"
---
# <a name="wcf-service-publishing"></a>Pubblicazione servizio WCF

La pubblicazione del servizio Windows Communication Foundation (WCF) aiuta l'utente a progredire dall'ambiente di sviluppo iniziale fornito dall'host del servizio WCF e dal client di prova WCF per distribuire effettivamente l'applicazione in un ambiente di produzione a scopo di test. Prima di eseguire il commit in un piano di distribuzione finale, è possibile utilizzare la pubblicazione del servizio Windows Communication Foundation (WCF) per verificare che il servizio WCF venga eseguito correttamente e sia pronto per la pubblicazione. È inoltre possibile scegliere di distribuire le librerie del servizio WCF in diversi percorsi di destinazione per il test.

## <a name="supported-services-and-target-locations"></a>Servizi supportati e posizioni di destinazione

La pubblicazione del servizio WCF supporta la pubblicazione di servizi WCF creati dal set di modelli di libreria di servizi WCF e dei modelli di elementi corrispondenti, inclusi i seguenti:

- Modello di libreria di servizi WCF con modello di elemento.

- Libreria di servizi di diffusione.

È possibile trovare questi modelli di servizio scegliendo **file**  >  **nuovo progetto** > [**Visual Basic** o **Visual C#**] > **WCF**. Per altri modelli WCF in questa posizione (inclusa l'applicazione del servizio flusso di lavoro WCF e l'applicazione di servizio WCF), è possibile pubblicare utilizzando la [pubblicazione con un clic per le applicazioni Web](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110)).

È possibile pubblicare il servizio nelle posizioni di destinazione seguenti.

- IIS locale.

- File system.

- Sito FTP.

## <a name="using-wcf-service-publishing"></a>Uso di Pubblicazione servizio WCF

Per distribuire un'implementazione del servizio, eseguire la procedura seguente:

1. Aprire Visual Studio con privilegi elevati, fare clic con il pulsante destro del mouse sul file eseguibile e scegliere **Esegui come amministratore** per aprirlo.  Se si utilizza IIS 7,0 o versione successiva, verificare di aver installato il componente "compatibilità della metabase di IIS e della configurazione IIS6" utilizzando "attivazione o disattivazione delle funzionalità Windows" nel pannello di controllo.

2. Aprire un progetto di servizio, selezionare **Compila**  >  **pubblicazione \<Project Name> ** dal menu principale oppure fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e scegliere **pubblica**.

3. Verrà visualizzata la finestra **pubblica** . Fare clic su **...**. per specificare la posizione di destinazione in cui distribuire il servizio. È possibile scegliere di distribuire l'applicazione nel sito IIS, file System o FTP locale. Se si distribuisce l'applicazione in IIS locale, è possibile selezionare il sito Web e creare l'applicazione Web al suo interno facendo clic sull'icona **Crea nuova applicazione Web** nell'angolo superiore destro.

4. Dopo aver fatto clic su **pubblica** nella finestra principale, Visual Studio distribuisce l'applicazione nel percorso di destinazione specificato e copia i file di Web.config, SVC e assembly nella directory di destinazione. . Il nome del file con estensione svc sarà "NomeProgetto. ServiceName. svc". Dopo la pubblicazione del servizio, è possibile trovare un che nella finestra di output di Visual Studio, che ha un aspetto simile a "connessione a `http://localhost/WebApplicationFolderName...` ". Premere CTRL e fare clic sul collegamento per aprire una pagina del browser in Visual Studio per visualizzare la struttura di directory del servizio.

     Se non è possibile collegarsi al sito, è possibile che il browser di directory non sia abilitato in IIS. Per abilitarla, seguire i suggerimenti disponibili nella sezione "operazioni che è possibile provare". In alternativa, è possibile digitare direttamente `http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc` per visualizzare la pagina del servizio.

È possibile utilizzare **pubblica** per specificare se si desidera copiare il file di assembly, configurazione e SVC per tutti i servizi definiti nel progetto nel percorso di destinazione e sovrascrivere i file esistenti nella destinazione.

Se si sceglie di distribuire l'applicazione nel sito Web IIS locale, è possibile rilevare errori correlati all'installazione di IIS. Verificare che IIS sia installato in modo corretto. È possibile immettere `http://localhost` nella barra degli indirizzi del browser e controllare se viene visualizzata la pagina predefinita di IIS. In alcuni casi, è possibile che i problemi siano causati anche da una registrazione non corretta di ASP.NET o WCF in IIS. È possibile aprire il Prompt dei comandi per gli sviluppatori per Visual Studio ed eseguire il comando `aspnet_regiis.exe -ir` per correggere i problemi di registrazione di ASP.NET oppure eseguire il comando `ServiceModelReg.exe –ia` per correggere i problemi di registrazione di WCF.

## <a name="files-generated-for-publishing"></a>File generati per la pubblicazione
 Prima che una libreria di servizi WCF possa essere ospitata sul Web, i file seguenti vengono generati dallo strumento: file di assembly, file di Web.config e file con estensione svc. Tutti i file vengono copiati nella posizione di destinazione specificata. Il servizio viene quindi pubblicato.

### <a name="assembly-files"></a>File di assembly
 Quando si pubblica un servizio WCF utilizzando questo strumento, il servizio viene compilato automaticamente per primo e i file di assembly vengono generati nel progetto di servizio dopo la compilazione.

### <a name="svc-file"></a>File SVC
 L'operazione di pubblicazione genera un file *. svc per ogni servizio WCF, indipendentemente dal fatto che il file esista o meno, per garantire la validità della versione. Esistono due tipi diversi di file SVC: uno per la libreria del servizio WCF e la libreria del servizio di diffusione e un altro per la libreria di servizi del flusso di lavoro della macchina a Stati e sequenziali. Il \* file con estensione svc generato viene copiato nella cartella radice nel percorso di destinazione.

### <a name="webconfig-file"></a>File Web.config
 Ogni volta che un progetto di servizio viene pubblicato in una posizione di destinazione specifica, viene creato un file Web.config.

 Il file di Web.config generato include sezioni Web utili per l'hosting Web e il contenuto di App.config per la libreria di servizi WCF con le modifiche seguenti:

- L'indirizzo di base è escluso.

- Le impostazioni nell'elemento `<diagnostics>` vengono escluse per mantenere le impostazioni di traccia della piattaforma di destinazione.

## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Pubblicazione di servizi WCF con associazioni non HTTP a IIS
 Se si utilizza IIS 7.0 o versione successiva, è possibile pubblicare i servizi WCF con binding non HTTP a IIS. È necessario tuttavia eseguire alcune configurazioni preliminari. Per ulteriori informazioni, vedere gli argomenti relativi all' [hosting nel servizio di attivazione dei processi di Windows](./feature-details/hosting-in-windows-process-activation-service.md).

## <a name="security"></a>Sicurezza
 Per la pubblicazione su un sito Web IIS locale sono necessari i privilegi di amministratore, poiché IIS deve essere eseguito con un account di questo tipo. Se un utente senza privilegi di amministratore apre la pubblicazione del servizio WCF, IIS non è disponibile come percorso di destinazione. La pubblicazione nel file System o nel sito FTP funziona senza privilegi di amministratore.

## <a name="see-also"></a>Vedere anche

- [Modelli di Visual Studio WCF](wcf-vs-templates.md)
- [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Client di prova WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
