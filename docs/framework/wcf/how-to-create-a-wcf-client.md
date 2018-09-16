---
title: 'Procedura: creare un client di Windows Communication Foundation'
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: e5655a6fdc06e69d801cb38b7ee7412450f0d34c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45674143"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Procedura: creare un client di Windows Communication Foundation

Questa è la quarta delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).

In questo argomento viene descritto come recuperare i metadati da un servizio WCF e usarlo per creare un proxy WCF che può accedere al servizio. Questa attività viene completata utilizzando la funzionalità Aggiungi riferimento al servizio fornita da Visual Studio. Con questo strumento si ottengono i metadati dall'endpoint MEX del servizio e si genera un file di codice sorgente gestito per un proxy client nel linguaggio scelto (per impostazione predefinita C#). Oltre a creare il proxy client, lo strumento crea o aggiorna anche il file di configurazione client che consente all'applicazione client di connettersi al servizio su uno dei relativi endpoint.

> [!NOTE]
> È anche possibile usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento per generare la classe proxy e la configurazione anziché utilizzare Aggiungi riferimento al servizio all'interno di Visual Studio.

> [!WARNING]
> Quando si chiama un servizio WCF da un progetto libreria di classi in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] è possibile usare la funzionalità Aggiungi riferimento al servizio per generare automaticamente un proxy e un file di configurazione associata.  Il file di configurazione non sarà utilizzato dal progetto Libreria di classi. Sarà necessario aggiungere le impostazioni del file di configurazione generato nel file app.config per il file eseguibile che chiamerà la libreria di classi.

 L'applicazione client utilizza la classe proxy generata per comunicare con il servizio. Questa procedura è descritta in [procedura: usare un Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="to-create-a-windows-communication-foundation-client"></a>Per creare un client Windows Communication Foundation

1.  Creare un nuovo progetto applicazione console facendo clic sulla soluzione Introduzione a, scegliendo **Add**, **nuovo progetto**. Sul lato sinistro della finestra di dialogo **Aggiungi nuovo progetto** selezionare **Windows** sotto **C#** o **VB**. Nella sezione centrale della finestra di dialogo selezionare **Applicazione console**. Denominare il progetto `GettingStartedClient`.

2.  Impostare il framework di destinazione del progetto GettingStartedClient su .NET Framework 4.5 con il pulsante destro facendo clic su **GettingStartedClient** in Esplora soluzioni e selezionando **proprietà**. Nella casella a discesa **Framework di destinazione** selezionare **.NET Framework 4.5**. Il framework di destinazione per un progetto VB è leggermente diverso. nella finestra di dialogo Proprietà progetto GettingStartedClient fare clic sui **Compile** scheda sul lato sinistro della schermata e quindi fare clic su di **avanzate Opzioni di compilazione** pulsante nell'angolo inferiore sinistro della finestra di dialogo. Selezionare quindi **.NET Framework 4.5** nella casella a discesa **Framework di destinazione**.

     Se si imposta il framework di destinazione verrà Visual Studio 2011, ricaricare la soluzione, premere **OK** quando richiesto.

3.  Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedClient facendo clic con il **riferimento** cartella nel progetto GettingStartedClient in Esplora soluzioni e scegliere **Add** Riferimento. Nella finestra di dialogo **Aggiungi riferimento** selezionare **Framework** sul lato sinistro. Nella casella di testo di ricerca degli assembly digitare `System.ServiceModel`. Nella sezione centrale della finestra di dialogo selezionare **System.ServiceModel**, fare clic sul pulsante **Aggiungi**, quindi sul pulsante **Chiudi**. Salvare la soluzione scegliendo il **Salva tutto** pulsante sotto il menu principale.

4.  Si aggiungerà quindi un riferimento al servizio per il servizio di calcolatrice. Prima di poter eseguire questa operazione, è necessario avviare l'applicazione console GettingStartedHost. L'host è in esecuzione, fare doppio clic il **riferimenti** cartella nel progetto GettingStartedClient in **Esplora soluzioni** e selezionare **Add**  >   **Riferimento del servizio**. Digitare l'URL seguente nella casella dell'indirizzo del **Aggiungi riferimento al servizio** finestra di dialogo: [ http://localhost:8000/GettingStartedClient/Service ](http://localhost:8000/GettingStartedClient/Service) e fare clic sui **passare** pulsante. CalculatorService dovrebbe quindi essere visualizzato nella casella di riepilogo di servizi. Fare doppio clic su CalculatorService che espandere e visualizzare i contratti di servizio implementati dal servizio. Lasciare lo spazio dei nomi predefinito e scegliere il **OK** pulsante.

     Quando si aggiunge un riferimento a un servizio utilizzando Visual Studio, nel progetto GettingStartedClient della cartella Riferimenti del servizio in Esplora soluzioni viene visualizzato un nuovo elemento.  Se si usa la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento verrà generati un file di codice sorgente e file app. config.

     È anche possibile usare lo strumento da riga di comando [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con le opzioni appropriate per creare il codice client. Nell'esempio seguente viene illustrato un file di codice e un file di configurazione per il servizio. Nel primo esempio viene illustrato come generare il proxy in VB e nel secondo come effettuare la stessa operazione in C#:

    ```
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

    ```csharp
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

 A questo punto è stato creato il proxy che sarà utilizzato dall'applicazione client per chiamare il servizio calcolatrice. Passare all'argomento successivo della serie: [procedura: configurare un Client](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>Vedere anche

- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)
- [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Procedura: Usare Svcutil.exe per scaricare documenti di metadati](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
