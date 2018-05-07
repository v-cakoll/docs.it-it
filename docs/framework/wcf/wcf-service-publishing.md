---
title: Pubblicazione servizio WCF
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 9f76ab11e9697fc5af5c507d4dc9d944c433c918
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-service-publishing"></a>Pubblicazione servizio WCF
Pubblicazione servizio Windows Communication Foundation (WCF) fornisce assistenza per dall'ambiente di sviluppo iniziale fornito da [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host del servizio e [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di prova all'effettiva distribuzione all'applicazione di un ambiente di produzione ambiente a scopo di test. Prima eseguire il commit a un piano di distribuzione finale, è possibile usare pubblicazione servizio Windows Communication Foundation (WCF) per verificare che il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizio eseguito correttamente e sia pronto per la pubblicazione. È inoltre possibile scegliere di distribuire le librerie dei servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in diverse posizioni di destinazione per il test.  
  
## <a name="supported-services-and-target-locations"></a>Servizi supportati e posizioni di destinazione  
 Pubblicazione servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] supporta la pubblicazione di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] creati dal set di modelli delle librerie dei servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e dei modelli di elementi corrispondenti, tra cui:  
  
-   Modello della libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con modello di elemento.  
  
-   Libreria di servizi di diffusione.  
  
 È possibile trovare questi modelli di servizio scegliendo **File** -> **nuovo progetto** -> **Visual Basic** o **Visual c#**  ->  **WCF**. Per altri modelli WCF in questa posizione, inclusi applicazione del servizio del flusso di lavoro WCF e applicazione di servizio WCF, è possibile pubblicare utilizzando [pubblicazione per le applicazioni web a un solo clic](https://msdn.microsoft.com/library/dd465337\(v=vs.110\).aspx).  
  
 È possibile pubblicare il servizio nelle posizioni di destinazione seguenti.  
  
-   IIS locale.  
  
-   File system.  
  
-   Sito FTP.  
  
## <a name="using-wcf-service-publishing"></a>Uso di Pubblicazione servizio WCF  
 Per distribuire un'implementazione del servizio, eseguire la procedura seguente:  
  
1.  Aprire Visual Studio con privilegi elevati (fare doppio clic sul file eseguibile e utilizzare "Esegui come amministratore" per avviare il programma).  Se si utilizza IIS 7.0 o versioni successive, verificare di aver installato il componente "Metabase IIS 6 Configuration compatibilità IIS e" che utilizza "' o disattivare le funzionalità di Windows" nel Pannello di controllo.  
  
2.  Aprire un progetto di servizio, selezionare **compilare**->**pubblica \<nome progetto >** dal menu principale, o il pulsante destro del mouse sul progetto in **Esplora**e fare clic su **pubblica**.  
  
3.  Il **pubblica** verrà visualizzata la finestra. Fare clic su di **...** . per specificare la posizione di destinazione in cui distribuire il servizio. È possibile scegliere di distribuire l'applicazione IIS locale, File System o sito FTP. Se distribuire l'applicazione IIS locale, è possibile selezionare il sito Web e creare l'applicazione web, fare clic il **Crea nuova applicazione Web** in alto nell'angolo destro.  
  
4.  Dopo aver fatto clic **pubblica** nella finestra principale di Visual Studio distribuisce l'applicazione nel percorso di destinazione specificato e copia i file Web. config, con estensione svc e assembly nella directory di destinazione. . Il nome dell'estensione svc sarà "ProjectName.ServiceName.svc". Al termine della pubblicazione il servizio, è possibile trovare un DBCS nella finestra Output di Visual Studio, che presenta un aspetto simile a "Connessione a un collegamento ipertestuale"http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName ...". Premere CTRL e fare clic sul collegamento per aprire una pagina del browser in Visual Studio per visualizzare la struttura di directory del servizio.  
  
     Se non è possibile collegarsi al sito, è possibile che il browser di directory non sia abilitato in IIS. Seguire i suggerimenti nella sezione "Possibili operazioni" per abilitare la funzionalità. In alternativa, è possibile digitare direttamente"HYPERLINK"http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc" per visualizzare la pagina del servizio.  
  
 È possibile utilizzare **pubblica** per specificare se si desidera copiare l'assembly, configurazione e il file con estensione svc per tutti i servizi definiti nel progetto nel percorso di destinazione e sovrascrivere i file esistenti nella destinazione.  
  
 Se si sceglie di distribuire l'applicazione nel sito Web IIS locale, è possibile rilevare errori correlati all'installazione di IIS. Verificare che IIS sia installato in modo corretto. È possibile digitare "HYPERLINK"http://localhost" http://localhost" nel browser e verificare se la pagina predefinita IIS verrà visualizzati.  In alcuni casi i problemi potrebbero essere causati dalla registrazione non corretta di ASP.NET o [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in IIS. È possibile aprire il prompt dei comandi di Visual Studio ed eseguire il comando "aspnet_regiis.exe - ir" per risolvere i problemi di registrazione ASP.NET o eseguire il comando "ServiceModelReg.exe-ia" per correggere problemi di registrazione di WCF.  
  
## <a name="files-generated-for-publishing"></a>File generati per la pubblicazione  
 Prima che una libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] possa essere ospitata sul Web, devono essere generati automaticamente i file di assembly, il file Web.config e il file con estensione svc. Tutti i file vengono copiati nella posizione di destinazione specificata. Il servizio viene quindi pubblicato.  
  
### <a name="assembly-files"></a>File di assembly  
 Quando si pubblica un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usando questo strumento, viene innanzitutto compilato automaticamente il servizio, mentre i file di assembly vengono generati nel progetto di servizio dopo la compilazione.  
  
### <a name="svc-file"></a>File SVC  
 L'operazione di pubblicazione determina la creazione di un file con estensione svc per ogni servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], indipendentemente dal fatto che il file esista o meno, per garantire la validità della versione. Esistono due tipi diversi di file svc: uno per la libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e la libreria di servizi di diffusione e un altro per la libreria di servizi del flusso di lavoro sequenziale e la libreria di servizi del flusso di lavoro di una macchina a stati. Generato \*file con estensione svc viene copiato nella cartella radice nella posizione di destinazione.  
  
### <a name="webconfig-file"></a>File Web.config  
 Ogni volta che un progetto di servizio viene pubblicato in una posizione di destinazione specifica, viene creato un file Web.config.  
  
 Il file Web.config generato include sezioni Web utili per l'hosting Web, nonché il contenuto del file App.config per la libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con le modifiche seguenti:  
  
-   L'indirizzo di base è escluso.  
  
-   Le impostazioni nell'elemento `<diagnostics>` vengono escluse per mantenere le impostazioni di traccia della piattaforma di destinazione.  
  
## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>Pubblicazione di servizi WCF con associazioni non HTTP a IIS  
 Se si usa IIS7.0 o versione successiva, è possibile pubblicare servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con associazioni a IIS non HTTP. È necessario tuttavia eseguire alcune configurazioni preliminari. Per ulteriori informazioni, vedere gli argomenti in [Hosting nel servizio Attivazione processo Windows](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
## <a name="security"></a>Sicurezza  
 Per la pubblicazione su un sito Web IIS locale sono necessari i privilegi di amministratore, poiché IIS deve essere eseguito con un account di questo tipo. Se Pubblicazione servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] viene aperto da un utente che non dispone dei privilegi di amministratore, IIS non sarà disponibile come posizione di destinazione. La pubblicazione in File System o sito FTP funziona senza privilegio di amministratore.  
  
## <a name="see-also"></a>Vedere anche  
 [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
