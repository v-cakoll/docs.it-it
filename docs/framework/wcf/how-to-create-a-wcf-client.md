---
title: 'Esercitazione: Creare un client Windows Communication FoundationTutorial: Create a Windows Communication Foundation client'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184105"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Esercitazione: Creare un client Windows Communication FoundationTutorial: Create a Windows Communication Foundation client

Questa esercitazione descrive la quarta di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base. Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).

L'attività successiva per la creazione di un'applicazione WCF consiste nel creare un client recuperando i metadati da un servizio WCF. Utilizzare Visual Studio per aggiungere un riferimento al servizio, che ottiene i metadati dall'endpoint MEX del servizio. Visual Studio genera quindi un file di codice sorgente gestito per un proxy client nel linguaggio scelto. Viene inoltre creato un file di configurazione client (*App.config*). Questo file consente all'applicazione client di connettersi al servizio in un endpoint.

> [!NOTE]
> Se si chiama un servizio WCF da un progetto di libreria di classi in Visual Studio, usare la funzionalità **Aggiungi riferimento** al servizio per generare automaticamente un proxy e un file di configurazione associato. Tuttavia, poiché i progetti di libreria di classi non utilizzano questo file di configurazione, è necessario aggiungere le impostazioni nel file di configurazione generato al file *App.config* per l'eseguibile che chiama la libreria di classi.

> [!NOTE]
> In alternativa, utilizzare [lo strumento ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) anziché Visual Studio per generare la classe proxy e il file di configurazione.

L'applicazione client utilizza la classe proxy generata per comunicare con il servizio. Questa procedura è descritta in [Esercitazione: Utilizzare un client](how-to-use-a-wcf-client.md).

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per il client WCF.
> - Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione.

## <a name="create-a-windows-communication-foundation-client"></a>Creare un client Windows Communication FoundationCreate a Windows Communication Foundation client

1. Creare un progetto di app console in Visual Studio:Create a console app project in Visual Studio:

    1. Scegliere **Apri** > **progetto/soluzione** dal menu **File** e individuare la soluzione **GettingStarted** creata in precedenza (*GettingStarted.sln*). Selezionare **Apri**.

    2. Scegliere **Esplora soluzioni**dal menu **Visualizza** .

    3. Nella finestra **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo superiore), quindi scegliere **Aggiungi** > **nuovo progetto** dal menu di scelta rapida.

    4. Nella finestra **Aggiungi nuovo progetto,** sul lato sinistro, selezionare la categoria **Desktop di Windows** in Visual **Cè** o **Visual Basic**.

    5. Selezionare il modello **App console (.NET Framework)** e immettere *GettingStartedClient* come **Nome**. Selezionare **OK**.

2. Aggiungere un riferimento nel progetto GettingStartedClient all'assembly:Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:

    1. Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedClient,** quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.

    2. Nella finestra **Aggiungi riferimento,** in **Assembly** sul lato sinistro della finestra, selezionare **Framework**.

    3. Individuare e selezionare **System.ServiceModel**, quindi scegliere **OK**.

    4. Salvare la soluzione selezionando Salva**tutto** **al file** > .

3. Aggiungere un riferimento al servizio di calcolo:Add a service reference to the calculator service:

   1. Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedClient,** quindi scegliere **Aggiungi riferimento al servizio** dal menu di scelta rapida.

   2. Nella finestra **Aggiungi riferimento** al servizio selezionare **Individua**.

      Il servizio CalculatorService viene avviato e Visual Studio lo visualizza nella casella **Servizi.**

   3. Selezionare **CalculatorService** per espanderlo e visualizzare i contratti di servizio implementati dal servizio. Lasciare il valore predefinito **Spazio dei nomi** e scegliere **OK**.

      Visual Studio aggiunge un nuovo elemento nella cartella **Servizi connessi** nel progetto **GettingStartedClient.**

### <a name="servicemodel-metadata-utility-tool"></a>Strumento Utilità metadati ServiceModelServiceModel Metadata Utility tool

Negli esempi seguenti viene illustrato come utilizzare facoltativamente [lo strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il file di classe proxy. Questo strumento genera il file della classe proxy e il file *App.config.* Negli esempi seguenti viene illustrato come generare il proxy rispettivamente in C .

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>File di configurazione del client

Dopo aver creato il client, Visual Studio crea il file di configurazione App.config nel progetto **GettingStartedClient,** che dovrebbe essere simile all'esempio seguente:After you've created the client, Visual Studio creates the **App.config** configuration file in the GettingStartedClient project, which should be similar to the following example:

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

Nella sezione [ \<>system.serviceModel](../configure-apps/file-schema/wcf/system-servicemodel.md) notare l'elemento [ \<endpoint>.](../configure-apps/file-schema/wcf/endpoint-element.md) L'elemento ** &lt;endpoint&gt; ** definisce l'endpoint utilizzato dal client per accedere al servizio nel modo seguente:The endpoint element defines the endpoint that the client uses to access the service as follows:

- Indirizzo: `http://localhost:8000/GettingStarted/CalculatorService`. L'indirizzo dell'endpoint.
- Contratto `ServiceReference1.ICalculator`di servizio: . Il contratto di servizio gestisce la comunicazione tra il client WCF e il servizio. Visual Studio ha generato questo contratto quando è stata utilizzata la funzione **Aggiungi riferimento al servizio.** Si tratta essenzialmente di una copia del contratto definito nel progetto GettingStartedLib.
- Rilegatura: <xref:System.ServiceModel.WSHttpBinding>. L'associazione specifica HTTP come trasporto, sicurezza interoperabile e altri dettagli di configurazione.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per il client WCF.
> - Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione per l'applicazione client.

Passare all'esercitazione successiva per informazioni su come usare il client generato.

> [!div class="nextstepaction"]
> [Esercitazione: Usare un client WCFTutorial: Use a WCF client](how-to-use-a-wcf-client.md)
