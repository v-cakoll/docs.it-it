---
title: 'Procedura: creare un client di Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
caps.latest.revision: "64"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd2740cfef2a618e4ab220f7db84fc78a10e0980
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Procedura: creare un client di Windows Communication Foundation
Questa è la quarta delle sei attività necessarie per creare un'applicazione [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Per una panoramica di tutte e sei le attività, vedere il [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md) argomento.  
  
 In questo argomento viene illustrato come recuperare metadati da un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e utilizzarli per creare un proxy [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in grado di accedere al servizio. Questa attività viene completata utilizzando la funzionalità Aggiungi riferimento al servizio fornita da Visual Studio. Con questo strumento si ottengono i metadati dall'endpoint MEX del servizio e si genera un file di codice sorgente gestito per un proxy client nel linguaggio scelto (per impostazione predefinita C#). Oltre a creare il proxy client, lo strumento crea o aggiorna anche il file di configurazione client che consente all'applicazione client di connettersi al servizio su uno dei relativi endpoint.  
  
> [!NOTE]
>  È inoltre possibile utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento per generare la classe proxy e configurazione invece di usare Aggiungi riferimento al servizio all'interno di Visual Studio.  
  
> [!WARNING]
>  Quando si esegue la chiamata a un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] da un progetto Libreria di classi in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], è possibile utilizzare la funzionalità Aggiungi riferimento al servizio per generare automaticamente un proxy e un file di configurazione associato.  Il file di configurazione non sarà utilizzato dal progetto Libreria di classi. Sarà necessario aggiungere le impostazioni del file di configurazione generato nel file app.config per il file eseguibile che chiamerà la libreria di classi.  
  
 L'applicazione client utilizza la classe proxy generata per comunicare con il servizio. Questa procedura è descritta [procedura: utilizzare un Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
### <a name="to-create-a-windows-communication-foundation-client"></a>Per creare un client Windows Communication Foundation  
  
1.  Creare un nuovo progetto applicazione console facendo clic su una soluzione di introduzione, se si seleziona, **Aggiungi**, **nuovo progetto**. Nel **Aggiungi nuovo progetto** sul lato sinistro della finestra di dialogo Seleziona **Windows** in **c#** o **VB**. Nella sezione centrale della finestra di dialogo selezionare **applicazione Console**. Denominare il progetto `GettingStartedClient`.  
  
2.  Impostare il framework di destinazione del progetto GettingStartedClient su .NET Framework 4.5 facendo clic su **GettingStartedClient** in Esplora soluzioni e selezionando **proprietà**. Nella casella a discesa **Framework di destinazione** selezionare **.NET Framework 4.5**. Il framework di destinazione per un progetto VB è leggermente diverso. nella finestra di dialogo Proprietà progetto GettingStartedClient fare clic su di **compilare** scheda sul lato sinistro della schermata e quindi scegliere il **avanzate Opzioni** pulsante nell'angolo inferiore sinistro della finestra di dialogo. Selezionare quindi **.NET Framework 4.5** nella casella a discesa **Framework di destinazione**.  
  
     Il framework di destinazione che impostare Visual Studio 2011 ricaricamento della soluzione, premere **OK** quando richiesto.  
  
3.  Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedClient facendo clic con il **riferimento** cartella nel progetto GettingStartedClient in Esplora soluzioni e selezionare **Aggiungi** Riferimento. Nel **Aggiungi riferimento** finestra di dialogo selezionare **Framework** sul lato sinistro della finestra di dialogo. Nella casella di testo di ricerca degli assembly digitare `System.ServiceModel`. Nella sezione centrale della finestra di dialogo selezionare **System. ServiceModel**, fare clic su di **Aggiungi** pulsante, quindi scegliere il **Chiudi** pulsante. Salvare la soluzione scegliendo il **Salva tutto** pulsante sotto il menu principale.  
  
4.  Successivamente, verrà aggiunto un riferimento al servizio calcolatrice. Prima di poter eseguire questa operazione, è necessario avviare l'applicazione console GettingStartedHost. Quando l'host è in esecuzione, è possibile fare clic con il pulsante destro cartella riferimenti nel progetto GettingStartedClient in Esplora soluzioni e selezionare Aggiungi riferimento al servizio; digitare l'URL seguente nella casella dell'indirizzo della finestra di dialogo Aggiungi riferimento al servizio: HYPERLINK "http:/ / localhost:8000/ServiceModelSamples/Service "http://localhost:8000/servicemodelsamples/Service/ServiceModelSamples/Service e fare clic su di **passare** pulsante. CalculatorService dovrebbe quindi essere visualizzato nella casella di riepilogo dei servizi. Fare doppio clic su CalculatorService in modo che venga espanso e vengano visualizzati i contratti di servizio implementati dal servizio. Spazio dei nomi predefinito e scegliere di lasciare il **OK** pulsante.  
  
     Quando si aggiunge un riferimento a un servizio utilizzando Visual Studio, nel progetto GettingStartedClient della cartella Riferimenti del servizio in Esplora soluzioni viene visualizzato un nuovo elemento.  Se si utilizza il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento verrà generati un file di codice sorgente e il file app. config.  
  
     È inoltre possibile utilizzare lo strumento da riga di comando [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con le opzioni appropriate per creare il codice client. Nell'esempio seguente viene illustrato un file di codice e un file di configurazione per il servizio. Nel primo esempio viene illustrato come generare il proxy in VB e nel secondo come effettuare la stessa operazione in C#:  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
 A questo punto è stato creato il proxy che sarà utilizzato dall'applicazione client per chiamare il servizio calcolatrice. Passare all'argomento successivo nella serie: [procedura: configurare un Client](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)  
 [Procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Procedura: usare Svcutil.exe per scaricare documenti di metadati](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
