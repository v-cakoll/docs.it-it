---
title: 'Esercitazione: Creare un client di Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: ddb5167c7f71a263377fb465ec44ee21057fbf4a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928898"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Esercitazione: Creare un client di Windows Communication Foundation

Questa esercitazione descrive il quarto di cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Inizia a usare Windows Communication Foundation applicazioni](getting-started-tutorial.md).

L'attività successiva per la creazione di un'applicazione WCF consiste nel creare un client recuperando i metadati da un servizio WCF. Si usa Visual Studio per aggiungere un riferimento al servizio, che ottiene i metadati dall'endpoint MEX del servizio. Visual Studio genera quindi un file di codice sorgente gestito per un proxy client nel linguaggio scelto. Viene inoltre creato un file di configurazione client (*app. config*). Questo file consente all'applicazione client di connettersi al servizio in un endpoint. 

> [!NOTE]
> Se si chiama un servizio WCF da un progetto libreria di classi in Visual Studio, utilizzare la funzionalità **Aggiungi riferimento al servizio** per generare automaticamente un proxy e un file di configurazione associato. Tuttavia, poiché i progetti della libreria di classi non utilizzano questo file di configurazione, è necessario aggiungere le impostazioni nel file di configurazione generato al file *app. config* per il file eseguibile che chiama la libreria di classi.

> [!NOTE]
> In alternativa, utilizzare lo [strumento ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) anziché Visual Studio per generare la classe proxy e il file di configurazione.

L'applicazione client utilizza la classe proxy generata per comunicare con il servizio. Questa procedura è descritta in [esercitazione: Usare un client](how-to-use-a-wcf-client.md).

In questa esercitazione si imparerà a:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per il client WCF.
> - Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione.

## <a name="create-a-windows-communication-foundation-client"></a>Creare un client di Windows Communication Foundation

1. Creare un progetto di app console in Visual Studio: 

    1. Dal menu **file** selezionare **Apri** > **progetto/soluzione** e passare alla soluzione **GettingStarted** creata in precedenza (*GettingStarted. sln*). Selezionare **Apri**.

    2. Scegliere **Esplora soluzioni**dal menu **Visualizza** .

    3. Nella finestra di **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo principale), quindi scegliere **Aggiungi** > **nuovo progetto** dal menu di scelta rapida. 
    
    4. Nella finestra **Aggiungi nuovo progetto** sul lato sinistro selezionare la categoria **desktop di Windows** in  **C# Visual** o **Visual Basic**. 

    5. Selezionare il modello **applicazione console (.NET Framework)** e immettere *GettingStartedClient* per **nome**. Selezionare **OK**.

2. Aggiungere un riferimento nel progetto **GettingStartedClient** all' <xref:System.ServiceModel> assembly: 

    1. Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedClient** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida. 

    2. Nella finestra **Aggiungi riferimento** , in **assembly** sul lato sinistro della finestra, selezionare **Framework**.
    
    3. Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**. 

    4. Salvare la soluzione selezionando **file** > **Salva tutto**.

3. Aggiungere un riferimento al servizio del calcolatore:

   1. Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedClient** e quindi selezionare **Aggiungi riferimento al servizio** dal menu di scelta rapida.

   2. Nella finestra di **Aggiungi riferimento al servizio** selezionare **individua**.

      Il servizio CalculatorService viene avviato e Visual Studio lo Visualizza nella casella **Servizi** .

   3. Selezionare **CalculatorService** per espanderlo e visualizzare i contratti di servizio implementati dal servizio. Lasciare lo **spazio dei nomi** predefinito e scegliere **OK**.

      Visual Studio aggiunge un nuovo elemento sotto la cartella **servizi connessi** nel progetto **GettingStartedClient** . 

### <a name="servicemodel-metadata-utility-tool"></a>ServiceModel Metadata Utility Tool

Negli esempi seguenti viene illustrato come utilizzare facoltativamente lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il file della classe proxy. Questo strumento genera il file di classe proxy e il file *app. config* . Negli esempi seguenti viene illustrato come generare il proxy in C# e Visual Basic, rispettivamente:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>File di configurazione client

Dopo aver creato il client, Visual Studio crea il file di configurazione **app. config** nel progetto **GettingStartedClient** , che dovrebbe essere simile all'esempio seguente:

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

Nella sezione [ >System.ServiceModel,osservarel'elemento>endpoint.\<](../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../configure-apps/file-schema/wcf/endpoint-element.md) **L'&lt;elementoendpoint&gt;** definisce l'endpoint utilizzato dal client per accedere al servizio come indicato di seguito:

- Indirizzo: `http://localhost:8000/GettingStarted/CalculatorService`. L'indirizzo dell'endpoint.
- Contratto di servizio `ServiceReference1.ICalculator`:. Il contratto di servizio gestisce la comunicazione tra il client WCF e il servizio. Questo contratto è stato generato da Visual Studio quando è stata usata la relativa funzione **Aggiungi riferimento al servizio** . Si tratta essenzialmente di una copia del contratto definito nel progetto GettingStartedLib. 
- Binding: <xref:System.ServiceModel.WSHttpBinding>. L'associazione specifica HTTP come trasporto, sicurezza interoperativa e altri dettagli di configurazione.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per il client WCF.
> - Aggiungere un riferimento al servizio WCF per generare la classe proxy e i file di configurazione per l'applicazione client.

Passare all'esercitazione successiva per apprendere come usare il client generato.

> [!div class="nextstepaction"]
> [Esercitazione: Usare un client WCF](how-to-use-a-wcf-client.md)
