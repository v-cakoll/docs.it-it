---
title: 'Esercitazione: Creare un client Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 0f7f622221e6612ecdb0ea04084d81e923218a5c
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634063"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Esercitazione: Creare un client Windows Communication Foundation

Questa esercitazione illustra il quarto di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Iniziare con le applicazioni di Windows Communication Foundation](getting-started-tutorial.md).

L'attività successiva per la creazione di un'applicazione WCF consiste nel creare un client tramite il recupero dei metadati da un servizio WCF. Si usa Visual Studio per aggiungere un riferimento al servizio, che ottiene i metadati dall'endpoint MEX del servizio. Visual Studio genera quindi un file di codice sorgente gestito per un proxy client nel linguaggio scelto. Viene anche creato un file di configurazione client (*app. config*). Questo file consente all'applicazione client di connettersi al servizio in un endpoint. 

> [!NOTE]
> Se si chiama un servizio WCF da un progetto libreria di classi in Visual Studio, usare il **Aggiungi riferimento al servizio** funzionalità per generare automaticamente un proxy e un file di configurazione associata. Tuttavia, poiché i progetti libreria di classi non utilizzano questo file di configurazione, è necessario aggiungere le impostazioni nel file di configurazione generato per il *app. config* file per il file eseguibile che chiama la libreria di classi.

> [!NOTE]
> In alternativa, usare il [strumento ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) invece di Visual Studio per generare il file di classe e la configurazione proxy.

L'applicazione client utilizza la classe proxy generata per comunicare con il servizio. Questa procedura è descritta nella [esercitazione: Usare un client](how-to-use-a-wcf-client.md).

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> - Creare e configurare un progetto app console per il client WCF.
> - Aggiungere un riferimento al servizio per il servizio WCF per generare i file di classe e la configurazione proxy.


## <a name="create-a-windows-communication-foundation-client"></a>Creare un client Windows Communication Foundation

1. Creare un progetto app console in Visual Studio: 

    1. Dal **File** dal menu **Open** > **progetto/soluzione** e passare alla **GettingStarted** soluzione si creato in precedenza (*GettingStarted.sln*). Selezionare **Apri**.

    2. Dal **View** dal menu **Esplora soluzioni**.

    3. Nel **Esplora soluzioni** finestra, seleziona la **GettingStarted** soluzione (nodo in alto) e quindi selezionare **Add** > **nuovo progetto** dal menu di scelta rapida. 
    
    4. Nel **Aggiungi nuovo progetto** finestra a sinistra, seleziona il **Desktop di Windows** categoria sotto **Visual C#**  oppure **Visual Basic**. 

    5. Selezionare il **App Console (.NET Framework)** modello, quindi immettere *GettingStartedClient* per il **nome**. Scegliere **OK**.

2. Aggiungere un riferimento nel **GettingStartedClient** del progetto per il <xref:System.ServiceModel> assembly: 

    1.  Nel **Esplora soluzioni** finestra, seleziona la **riferimenti** cartella sotto la **GettingStartedClient** del progetto e quindi selezionare **Aggiungi riferimento** dal menu di scelta rapida. 

    2. Nel **Aggiungi riferimento** finestra, sotto **assembly** sul lato sinistro della finestra, selezionare **Framework**.
    
    3. Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**. 

    4. Salvare la soluzione selezionando **File** > **Salva tutto**.

3. Aggiungere un riferimento al servizio di calcolatrice:

   1. Nel **Esplora soluzioni** finestra, seleziona la **riferimenti** cartella sotto la **GettingStartedClient** del progetto e quindi selezionare **Aggiungi riferimento al servizio**  dal menu di scelta rapida.

   2. Nel **Aggiungi riferimento al servizio** finestra, seleziona **Discover**.

      L'avvio del servizio CalculatorService e Visual Studio li visualizza nel **Services** casella.

   3. Selezionare **CalculatorService** per espanderlo e visualizzare i contratti di servizio implementati dal servizio. Lasciare l'impostazione predefinita **Namespace** e scegliere **OK**.

      Visual Studio aggiunge un nuovo elemento con il **servizi connessi** cartella nel **GettingStartedClient** progetto. 


### <a name="servicemodel-metadata-utility-tool"></a>Strumento ServiceModel Metadata Utility tool

Gli esempi seguenti illustrano come usare facoltativamente la [strumento ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il file di classe proxy. Questo strumento genera il file di classe proxy e il *app. config* file. Gli esempi seguenti illustrano come generare il proxy in C# e Visual Basic, rispettivamente:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>File di configurazione client

Dopo aver creato il client, Visual Studio crea il **app. config** file di configurazione le **GettingStartedClient** progetto, che dovrebbe essere simile all'esempio seguente:

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

Sotto il [ \<System. ServiceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) sezione, si noti il [ \<endpoint >](../configure-apps/file-schema/wcf/endpoint-element.md) elemento. Il **&lt;endpoint&gt;** elemento definisce l'endpoint utilizzato dal client per accedere al servizio come indicato di seguito:
- Indirizzo: `http://localhost:8000/GettingStarted/CalculatorService`. L'indirizzo dell'endpoint.
- Contratto di servizio: `ServiceReference1.ICalculator`. Il contratto di servizio gestisce la comunicazione tra il client WCF e il servizio. Visual Studio generato questo contratto quando è stato usato il **Aggiungi riferimento al servizio** (funzione). È essenzialmente una copia del contratto definito nel progetto GettingStartedLib. 
- Associazione: <xref:System.ServiceModel.WSHttpBinding>. L'associazione specifica HTTP come trasporto, sicurezza interoperativa e altri dettagli di configurazione.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> - Creare e configurare un progetto app console per il client WCF.
> - Aggiungere un riferimento al servizio per il servizio WCF per generare i file di classe e la configurazione proxy per l'applicazione client.

Passare all'esercitazione successiva per informazioni su come usare il client generato.

> [!div class="nextstepaction"]
> [Esercitazione: Usare un client WCF](how-to-use-a-wcf-client.md)


