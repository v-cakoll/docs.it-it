---
title: 'Procedura: creare un client di Windows Communication Foundation'
ms.date: 09/14/2018
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 9572f3e2c0cddf75daf343f250b16e94bc2b0dbf
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181670"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Procedura: creare un client di Windows Communication Foundation

Questa è la quarta delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).

In questo argomento viene descritto come recuperare i metadati da un servizio WCF e usarlo per creare un proxy WCF che può accedere al servizio. Questa attività viene completata utilizzando la **Aggiungi riferimento al servizio** funzionalità fornite da Visual Studio. Con questo strumento si ottengono i metadati dall'endpoint MEX del servizio e si genera un file di codice sorgente gestito per un proxy client nel linguaggio scelto (per impostazione predefinita C#). Oltre a creare il proxy client, lo strumento crea o aggiorna anche il file di configurazione client che consente all'applicazione client di connettersi al servizio su uno dei relativi endpoint.

> [!NOTE]
> È anche possibile usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dello strumento per generare la classe proxy e la configurazione invece di usare **Aggiungi riferimento al servizio** in Visual Studio.

> [!NOTE]
> Quando si chiama un servizio WCF da un progetto libreria di classi in Visual Studio, è possibile usare la **Aggiungi riferimento al servizio** funzionalità per generare automaticamente un proxy e un file di configurazione associata. Il file di configurazione non sarà utilizzato dal progetto Libreria di classi. È necessario aggiungere le impostazioni nel file di configurazione generato nel file app. config per il file eseguibile che chiama la libreria di classi.

L'applicazione client utilizza la classe proxy generata per comunicare con il servizio. Questa procedura è descritta in [procedura: usare un Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="to-create-a-windows-communication-foundation-client"></a>Per creare un client Windows Communication Foundation

1. Creare un nuovo progetto applicazione console in Visual Studio. Pulsante destro del mouse sulla soluzione nella Guida introduttiva **Esplora soluzioni** e selezionare **Add** > **nuovo progetto**. Nel **Aggiungi nuovo progetto** finestra di dialogo sul lato sinistro, seleziona la **Desktop di Windows** categoria sotto **Visual c#** oppure **Visual Basic**. Selezionare il **App Console (.NET Framework)** modello e quindi denominare il progetto **GettingStartedClient**.

2. Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedClient. Fare clic sui **riferimenti** cartella nel progetto GettingStartedClient in **Esplora soluzioni**e quindi selezionare **Aggiungi riferimento**. Nel **Aggiungi riferimento** finestra di dialogo, seleziona **Framework** sul lato sinistro della finestra di dialogo sotto **assembly**. Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**. Salvare la soluzione selezionando **File** > **Salva tutto**.

3. Aggiungere un riferimento al servizio per il servizio di calcolatrice.

   1. Innanzitutto, avviare l'applicazione console GettingStartedHost.

   2. L'host è in esecuzione, fare doppio clic il **riferimenti** cartella nel progetto GettingStartedClient in **Esplora soluzioni** e selezionare **Add**  >   **Riferimento del servizio**.

   3. Immettere l'URL seguente nella casella dell'indirizzo del **Aggiungi riferimento al servizio** finestra di dialogo: [http://localhost:8000/GettingStarted/CalculatorService](http://localhost:8000/GettingStarted/CalculatorService)

   4. Scegli **Vai**.

   CalculatorService è visualizzato nei **Services** casella di riepilogo. Fare doppio clic su CalculatorService per espanderlo e visualizzare i contratti di servizio implementati dal servizio. Lasciare lo spazio dei nomi predefinito come- e sceglie **OK**.

    Quando si aggiunge un riferimento a un servizio utilizzando Visual Studio, un nuovo elemento viene visualizzato nella **Esplora soluzioni** sotto il **riferimenti al servizio** cartella nel progetto GettingStartedClient. Se si usa la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) vengono generati degli strumenti, un file di codice sorgente e file app. config.

    È anche possibile usare lo strumento da riga di comando [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con le opzioni appropriate per creare il codice client. Nell'esempio seguente viene illustrato un file di codice e un file di configurazione per il servizio. Il primo esempio illustra come generare il proxy in VB e il secondo mostra come generare il proxy in c#:

    ```shell
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
    ```

    ```shell
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
    ```

## <a name="next-steps"></a>Passaggi successivi

È stato creato il proxy che utilizzerà l'applicazione client per chiamare il servizio di calcolatrice. Passare all'argomento successivo della serie.

> [!div class="nextstepaction"]
> [Procedura: Configurare un client](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>Vedere anche

- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)
- [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Procedura: Usare Svcutil.exe per scaricare documenti di metadati](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
