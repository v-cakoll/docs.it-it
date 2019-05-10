---
title: Pubblicazione servizio WCF
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: f10aabd2a2258f98915f1bbcc8b30fc1b7f677ac
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654574"
---
# <a name="wcf-service-publishing"></a>Pubblicazione servizio WCF

Pubblicazione servizio Windows Communication Foundation (WCF) assiste l'utente nel passaggio dall'ambiente di sviluppo iniziale fornito da Host servizio WCF e Client di prova WCF distribuisce l'applicazione in un ambiente di produzione a scopo di test. Prima di procedere effettivamente a un piano di distribuzione finale, è possibile usare pubblicazione servizio Windows Communication Foundation (WCF) per verificare che il servizio WCF eseguito correttamente e sia pronto per la pubblicazione. È anche possibile scegliere distribuire le librerie del servizio WCF in diverse posizioni di destinazione per il test.

## <a name="supported-services-and-target-locations"></a>Servizi supportati e posizioni di destinazione

Pubblicazione servizio WCF supporta la pubblicazione di servizi WCF creati dal set di modelli di libreria di servizi WCF e i modelli di elementi corrispondenti, che includono i seguenti:

- Modello WCF Service Library con modello di elemento.

- Libreria di servizi di diffusione.

È possibile trovare questi modelli di servizi scegliendo **File** > **nuovo progetto** > [**Visual Basic** oppure **Visual C#** ] > **WCF**. Per altri modelli WCF in questo percorso (incluso l'applicazione di servizio del flusso di lavoro WCF e applicazione di servizio WCF), è possibile pubblicare utilizzando [con un clic per le applicazioni web di pubblicazione](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110)).

È possibile pubblicare il servizio nelle posizioni di destinazione seguenti.

- IIS locale.

- File system.

- Sito FTP.

## <a name="using-wcf-service-publishing"></a>Uso di Pubblicazione servizio WCF

Per distribuire un'implementazione del servizio, eseguire la procedura seguente:

1. Aprire Visual Studio con privilegi elevati (fare clic sul file eseguibile e scegliere **Esegui come amministratore** per aprirlo).  Se si utilizza IIS 7.0 o versione successiva, assicurarsi che è stato installato il componente "Compatibilità Metabase di IIS e IIS 6 Configuration" con "Windows attiva o Disattiva funzionalità di" nel Pannello di controllo.

2. Aprire un progetto di servizio, selezionare **compilare** > **pubblica \<nome progetto >** dal menu principale oppure fare clic sul progetto in **Esplora**e fare clic su **Publish**.

3. Il **pubblica** verrà visualizzata la finestra. Fare clic su di **...** . per specificare la posizione di destinazione in cui distribuire il servizio. È possibile scegliere di distribuire l'applicazione in IIS locale, File System o sito FTP. Se si distribuisce l'applicazione per IIS locale, è possibile selezionare il sito Web e creare l'applicazione web, facendo i **Crea nuova applicazione Web** in alto a destra.

4. Dopo aver fatto clic **pubblica** nella finestra principale di Visual Studio distribuisce l'applicazione nel percorso di destinazione specificata e copia i file Web. config, con estensione svc e all'assembly nella directory di destinazione. . Il nome del file con estensione svc sarà "ProjectName". Dopo che il servizio viene pubblicato correttamente, è possibile trovare un collegamenti consigliati nella finestra Output di Visual Studio, che presenta un aspetto simile a "connessione a `http://localhost/WebApplicationFolderName...`". Premere CTRL e fare clic sul collegamento per aprire una pagina del browser in Visual Studio per visualizzare la struttura di directory del servizio.

     Se non è possibile collegarsi al sito, è possibile che il browser di directory non sia abilitato in IIS. Seguire i suggerimenti nella sezione "Possibili operazioni" per abilitarlo. In alternativa, è possibile digitare direttamente `http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc` per visualizzare la pagina del servizio.

È possibile usare **pubblica** per specificare se si desidera copiare l'assembly, configurazione e il file con estensione svc per tutti i servizi definiti nel progetto nel percorso di destinazione e sovrascrivere i file esistenti nella destinazione.

Se si sceglie di distribuire l'applicazione nel sito Web IIS locale, è possibile rilevare errori correlati all'installazione di IIS. Verificare che IIS sia installato in modo corretto. È possibile immettere `http://localhost` nella barra degli indirizzi del browser e verificare se la pagina IIS predefinita viene visualizzato. In alcuni casi, i problemi possono anche dipendere da una registrazione errata di ASP.NET o WCF in IIS. È possibile aprire il prompt dei comandi per gli sviluppatori per Visual Studio ed eseguire il comando `aspnet_regiis.exe -ir` risolvere i problemi di registrazione ASP.NET o eseguire comandi `ServiceModelReg.exe –ia` per risolvere i problemi di registrazione WCF.

## <a name="files-generated-for-publishing"></a>File generati per la pubblicazione
 Prima di una libreria di servizi WCF può essere ospitati su Web, i file seguenti sono generati dallo strumento: file di assembly, file Web. config e file con estensione svc. Tutti i file vengono copiati nella posizione di destinazione specificata. Il servizio viene quindi pubblicato.

### <a name="assembly-files"></a>File di assembly
 Quando si pubblica un servizio WCF usando questo strumento, il servizio viene innanzitutto compilato automaticamente e vengono generati i file di assembly nel progetto di servizio dopo la compilazione.

### <a name="svc-file"></a>File SVC
 L'operazione di pubblicazione genera un file con estensione svc per ogni servizio WCF, se il file esista o meno, per garantire la validità di versione. Esistono due tipi diversi di file svc: uno per WCF Service Library e libreria di servizi di diffusione e un altro per sequenziale e State Machine Workflow Service Library. Generato \*file con estensione svc viene copiato nella cartella radice nel percorso di destinazione.

### <a name="webconfig-file"></a>File Web.config
 Ogni volta che un progetto di servizio viene pubblicato in una posizione di destinazione specifica, viene creato un file Web.config.

 Il file Web. config generato include sezioni Web utili per l'hosting Web e il contenuto dell'App per la libreria di servizi WCF con le modifiche seguenti:

- L'indirizzo di base è escluso.

- Le impostazioni nell'elemento `<diagnostics>` vengono escluse per mantenere le impostazioni di traccia della piattaforma di destinazione.

## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Pubblicazione di servizi WCF con associazioni non HTTP a IIS
 Se si usa IIS7.0 o versione successiva, è possibile pubblicare servizi WCF con associazioni non HTTP a IIS. È necessario tuttavia eseguire alcune configurazioni preliminari. Per altre informazioni, vedere l'argomento [Hosting nel servizio Attivazione processo Windows](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).

## <a name="security"></a>Sicurezza
 Per la pubblicazione su un sito Web IIS locale sono necessari i privilegi di amministratore, poiché IIS deve essere eseguito con un account di questo tipo. Se un utente senza privilegi di amministratore apre pubblicazione servizio WCF, IIS non è disponibile come un percorso di destinazione. La pubblicazione nel File System o al sito FTP funziona senza privilegio di amministratore.

## <a name="see-also"></a>Vedere anche

- [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)
- [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)