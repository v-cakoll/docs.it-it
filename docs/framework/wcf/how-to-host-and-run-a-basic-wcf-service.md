---
title: 'Esercitazione: Ospitare ed eseguire un servizio Windows Communication Foundation di baseTutorial: Host and run a basic Windows Communication Foundation service'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184075"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Esercitazione: Ospitare ed eseguire un servizio Windows Communication Foundation di baseTutorial: Host and run a basic Windows Communication Foundation service

Questa esercitazione descrive la terza delle cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base. Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).

L'attività successiva per la creazione di un'applicazione WCF consiste nell'ospitare un servizio WCF in un'applicazione console. Un servizio WCF espone uno o più *endpoint,* ognuno dei quali espone una o più operazioni del servizio. Un endpoint del servizio specifica le informazioni seguenti:A service endpoint specifies the following information:

- Indirizzo in cui è possibile trovare il servizio.
- Associazione che contiene le informazioni che descrivono come un client deve comunicare con il servizio.
- Contratto che definisce la funzionalità fornita dal servizio ai client.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per l'hosting di un servizio WCF.
> - Aggiungere codice per ospitare il servizio WCF.
> - Aggiornare il file di configurazione.
> - Avviare il servizio WCF e verificare che sia in esecuzione.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Creare e configurare un progetto di app console per l'hosting del servizioCreate and configure a console app project for hosting the service

1. Creare un progetto di app console in Visual Studio:Create a console app project in Visual Studio:

    1. Scegliere **Apri** > **progetto/soluzione** dal menu **File** e individuare la soluzione **GettingStarted** creata in precedenza (*GettingStarted.sln*). Selezionare **Apri**.

    2. Scegliere **Esplora soluzioni**dal menu **Visualizza** .

    3. Nella finestra **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo superiore), quindi scegliere **Aggiungi** > **nuovo progetto** dal menu di scelta rapida.

    4. Nella finestra **Aggiungi nuovo progetto,** sul lato sinistro, selezionare la categoria **Desktop di Windows** in Visual **Cè** o **Visual Basic**.

    5. Selezionare il modello **App console (.NET Framework)** e immettere *GettingStartedHost* come **Nome**. Selezionare **OK**.

2. Aggiungere un riferimento nel progetto GettingStartedHost al progetto **GettingStartedLib:Add** a reference in the **GettingStartedHost** project to the GettingStartedLib project:

    1. Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedHost,** quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.

    2. Nella finestra di dialogo **Aggiungi riferimento,** in **Progetti** sul lato sinistro della finestra, selezionare **Soluzione**.

    3. Selezionare **GettingStartedLib** nella sezione centrale della finestra, quindi scegliere **OK**.

       Questa azione rende disponibili i tipi definiti nel progetto **GettingStartedLib** per il progetto **GettingStartedHost.**

3. Aggiungere un riferimento nel progetto GettingStartedHost all'assembly:Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:

    1. Nella finestra **Esplora soluzioni** selezionare la cartella **Riferimenti** nel progetto **GettingStartedHost,** quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.

    2. Nella finestra **Aggiungi riferimento,** in **Assembly** sul lato sinistro della finestra, selezionare **Framework**.

    3. Selezionare **System.ServiceModel**, quindi **scegliere OK**.

    4. Salvare la soluzione selezionando Salva**tutto** **al file** > .

## <a name="add-code-to-host-the-service"></a>Aggiungere codice per ospitare il servizioAdd code to host the service

Per ospitare il servizio, aggiungere il codice per eseguire la procedura seguente:To host the service, you add code to do the following steps:

1. Creare un URI per l'indirizzo di base.
2. Creare un'istanza della classe per l'hosting del servizio.
3. Creare un endpoint del servizio.
4. Consentire lo scambio di metadati.
5. Aprire l'host del servizio per l'ascolto dei messaggi in arrivo.
  
Apportare le modifiche seguenti al codice:

1. Aprire il **file Program.cs** o **Module1.vb** nel progetto **GettingStartedHost** e sostituirne il codice con il codice seguente:

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    Per informazioni sul funzionamento di questo codice, vedere Passaggi del [programma di hosting](#service-hosting-program-steps)dei servizi.

2. Aggiornare le proprietà del progetto:

   1. Nella finestra **Esplora soluzioni** selezionare la cartella **GettingStartedHost** e quindi **scegliere Proprietà** dal menu di scelta rapida.

   2. Nella pagina delle proprietà GettingStartedHost selezionare la scheda **Applicazione:On** the **GettingStartedHost** properties page, select the Application tab:

      - Per i progetti in C, selezionare **GettingStartedHost.Program** dall'elenco **Oggetto di avvio.**

      - Per i progetti Visual Basic, selezionare **Service.Program** dall'elenco **Oggetto di avvio.**

   3. Scegliere **Salva tutto**dal menu **File** .

## <a name="verify-the-service-is-working"></a>Verificare che il servizio funzioni

1. Compilare la soluzione e quindi eseguire l'applicazione console **GettingStartedHost** dall'interno di Visual Studio.

    Il servizio deve essere eseguito con privilegi di amministratore. Poiché Visual Studio è stato aperto con privilegi di amministratore, quando si esegue **GettingStartedHost** in Visual Studio, l'applicazione viene eseguita anche con privilegi di amministratore. In alternativa, è possibile aprire un nuovo prompt dei comandi come amministratore (selezionare **Altro** > **esecuzione come amministratore** dal menu di scelta rapida) ed eseguire **GettingStartedHost.exe** al suo interno.

2. Aprire un Web browser e passare alla `http://localhost:8000/GettingStarted/CalculatorService`pagina del servizio all'indirizzo .

   > [!NOTE]
   > Servizi come questo richiedono l'autorizzazione appropriata per registrare gli indirizzi HTTP sulla macchina per l'ascolto. Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP. Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).

## <a name="service-hosting-program-steps"></a>Passaggi del programma di hosting dei serviziService hosting program steps

I passaggi nel codice aggiunto per ospitare il servizio sono descritti di seguito:The steps in the code you added to host the service are described as follows:

- **Passaggio 1**: Creare `Uri` un'istanza della classe per contenere l'indirizzo di base del servizio. Un URL che contiene un indirizzo di base ha un URI facoltativo che identifica un servizio. L'indirizzo di base viene `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`formattato come segue: . L'indirizzo di base per il servizio di calcolatrice utilizza il trasporto HTTP, localhost, la porta 8000 e il segmento URI GettingStarted.

- **Passaggio 2**: Creare <xref:System.ServiceModel.ServiceHost> un'istanza della classe, che si utilizza per ospitare il servizio. Il costruttore accetta due parametri: il tipo della classe che implementa il contratto di servizio e l'indirizzo di base del servizio.

- **Passaggio 3:** Creare un'istanza. <xref:System.ServiceModel.Description.ServiceEndpoint> Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio. Il <xref:System.ServiceModel.Description.ServiceEndpoint> costruttore è composto dal tipo di interfaccia del contratto di servizio, da un'associazione e da un indirizzo. Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio. L'associazione per <xref:System.ServiceModel.WSHttpBinding>questo esempio è , che è un'associazione incorporata e si connette agli endpoint conformi alle specifiche di WS-. Per altre informazioni sulle associazioni WCF, vedere [Cenni preliminari](bindings-overview.md)sulle associazioni WCF. Aggiungere l'indirizzo all'indirizzo di base per identificare l'endpoint. Il codice specifica l'indirizzo come CalculatorService e l'indirizzo completo per l'endpoint come `http://localhost:8000/GettingStarted/CalculatorService`.

    > [!IMPORTANT]
    > Per .NET Framework versione 4 e successive, l'aggiunta di un endpoint del servizio è facoltativa. Per queste versioni, se non si aggiunge il codice o la configurazione, WCF aggiunge un endpoint predefinito per ogni combinazione di indirizzo di base e contratto implementato dal servizio. Per ulteriori informazioni sugli endpoint predefiniti, vedere [Specifica di un indirizzo endpoint.](specifying-an-endpoint-address.md) Per altre informazioni sugli endpoint, le associazioni e i comportamenti predefiniti, vedere [Configurazione semplificata](simplified-configuration.md) e [Configurazione semplificata per i servizi WCF.](samples/simplified-configuration-for-wcf-services.md)

- **Passo 4**: Abilitare lo scambio di metadati. I client utilizzano lo scambio di metadati per generare proxy per chiamare le operazioni del servizio. Per abilitare lo <xref:System.ServiceModel.Description.ServiceMetadataBehavior> scambio dei <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> metadati, creare un'istanza, impostarne `true`la proprietà su e aggiungere l'oggetto `ServiceMetadataBehavior` all'insieme <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> dell'istanza. <xref:System.ServiceModel.ServiceHost>

- **Passo 5** <xref:System.ServiceModel.ServiceHost> : Aperto per ascoltare i messaggi in arrivo. L'applicazione attende che si preme **Invio**. Dopo l'istanza <xref:System.ServiceModel.ServiceHost>dell'applicazione , viene eseguito un blocco try/catch. Per ulteriori informazioni sull'intercettazione <xref:System.ServiceModel.ServiceHost>sicura delle eccezioni generate da , vedere Usare Close and Abort per rilasciare le [risorse client WCF.](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> Quando si aggiunge una libreria di servizi WCF, Visual Studio la ospita automaticamente se si esegue il debug avviando un host del servizio. Per evitare conflitti, è possibile impedire a Visual Studio di ospitare la libreria del servizio WCF.
>
> 1. Selezionare il progetto **GettingStartedLib** in **Esplora soluzioni** e scegliere **Proprietà** dal menu di scelta rapida.
> 2. Selezionare **Opzioni WCF** e deselezionare **Avvia host del servizio WCF durante il debug**di un altro progetto nella stessa soluzione .

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per l'hosting di un servizio WCF.
> - Aggiungere codice per ospitare il servizio WCF.
> - Aggiornare il file di configurazione.
> - Avviare il servizio WCF e verificare che sia in esecuzione.

Passare all'esercitazione successiva per informazioni su come creare un client WCF.

> [!div class="nextstepaction"]
> [Esercitazione: Creare un client WCFTutorial: Create a WCF client](how-to-create-a-wcf-client.md)
