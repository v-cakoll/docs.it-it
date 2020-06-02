---
title: 'Esercitazione: ospitare ed eseguire un servizio Windows Communication Foundation di base'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 872844487578843492e05dd2abb87b50e0bec91c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291396"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Esercitazione: ospitare ed eseguire un servizio Windows Communication Foundation di base

In questa esercitazione viene descritta la terza delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).

L'attività successiva per la creazione di un'applicazione WCF consiste nell'ospitare un servizio WCF in un'applicazione console. Un servizio WCF espone uno o più *endpoint*, ognuno dei quali espone una o più operazioni del servizio. Un endpoint di servizio specifica le informazioni seguenti:

- Un indirizzo in cui è possibile trovare il servizio.
- Associazione che contiene le informazioni che descrivono come un client deve comunicare con il servizio.
- Contratto che definisce la funzionalità fornita dal servizio ai propri client.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per l'hosting di un servizio WCF.
> - Aggiungere il codice per ospitare il servizio WCF.
> - Aggiornare il file di configurazione.
> - Avviare il servizio WCF e verificare che sia in esecuzione.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Creare e configurare un progetto di app console per ospitare il servizio

1. Creare un progetto di app console in Visual Studio:

    1. Dal menu **file** selezionare **Apri**  >  **progetto/soluzione** e passare alla soluzione **GettingStarted** creata in precedenza (*GettingStarted. sln*). Seleziona **Apri**.

    2. Scegliere **Esplora soluzioni**dal menu **Visualizza** .

    3. Nella finestra di **Esplora soluzioni** selezionare la soluzione **GettingStarted** (nodo principale), quindi scegliere **Aggiungi**  >  **nuovo progetto** dal menu di scelta rapida.

    4. Nella finestra **Aggiungi nuovo progetto** sul lato sinistro selezionare la categoria **desktop di Windows** in **Visual C#** o **Visual Basic**.

    5. Selezionare il modello **applicazione console (.NET Framework)** e immettere *GettingStartedHost* per **nome**. Selezionare **OK**.

2. Aggiungere un riferimento nel progetto **GettingStartedHost** al progetto **GettingStartedLib** :

    1. Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedHost** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.

    2. Nella finestra di dialogo **Aggiungi riferimento** fare clic su **soluzione**in **progetti** sul lato sinistro della finestra.

    3. Selezionare **GettingStartedLib** nella sezione centrale della finestra e quindi fare clic su **OK**.

       Questa azione rende disponibili i tipi definiti nel progetto **GettingStartedLib** per il progetto **GettingStartedHost** .

3. Aggiungere un riferimento nel progetto **GettingStartedHost** all' <xref:System.ServiceModel> assembly:

    1. Nella finestra di **Esplora soluzioni** selezionare la cartella **riferimenti** nel progetto **GettingStartedHost** e quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida.

    2. Nella finestra **Aggiungi riferimento** , in **assembly** sul lato sinistro della finestra, selezionare **Framework**.

    3. Selezionare **System. ServiceModel**, quindi fare clic su **OK**.

    4. Salvare la soluzione selezionando **file**  >  **Salva tutto**.

## <a name="add-code-to-host-the-service"></a>Aggiungere il codice per ospitare il servizio

Per ospitare il servizio, aggiungere il codice per eseguire i passaggi seguenti:

1. Creare un URI per l'indirizzo di base.
2. Creare un'istanza della classe per ospitare il servizio.
3. Creare un endpoint del servizio.
4. Consentire lo scambio di metadati.
5. Aprire l'host del servizio per restare in attesa dei messaggi in arrivo.
  
Apportare le modifiche seguenti al codice:

1. Aprire il file **Program.cs** o **Module1. vb** nel progetto **GettingStartedHost** e sostituirne il codice con il codice seguente:

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
                    selfHost.Description.Behaviors.Add(smb);

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

    Per informazioni sul funzionamento di questo codice, vedere la pagina relativa alla [procedura di hosting del programma](#service-hosting-program-steps).

2. Aggiornare le proprietà del progetto:

   1. Nella finestra di **Esplora soluzioni** selezionare la cartella **GettingStartedHost** e quindi selezionare **proprietà** dal menu di scelta rapida.

   2. Nella pagina delle proprietà di **GettingStartedHost** selezionare la scheda **applicazione** :

      - Per i progetti C#, selezionare **GettingStartedHost. Program** nell'elenco **oggetto di avvio** .

      - Per Visual Basic progetti, selezionare **Service. Program** dall'elenco **oggetto di avvio** .

   3. Scegliere **Salva tutto**dal menu **file** .

## <a name="verify-the-service-is-working"></a>Verificare il funzionamento del servizio

1. Compilare la soluzione, quindi eseguire l'applicazione console **GettingStartedHost** dall'interno di Visual Studio.

    Il servizio deve essere eseguito con privilegi di amministratore. Poiché è stato aperto Visual Studio con privilegi di amministratore, quando si esegue **GettingStartedHost** in Visual Studio, l'applicazione viene eseguita anche con privilegi di amministratore. In alternativa, è possibile aprire un nuovo prompt dei comandi come amministratore (selezionare **more**  >  **Esegui come amministratore** dal menu di scelta rapida) ed eseguire **GettingStartedHost. exe** al suo interno.

2. Aprire un Web browser e passare alla pagina del servizio all'indirizzo `http://localhost:8000/GettingStarted/CalculatorService` .

   > [!NOTE]
   > Per i servizi di questo tipo è necessaria l'autorizzazione appropriata per registrare gli indirizzi HTTP nel computer per l'ascolto. Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP. Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).

## <a name="service-hosting-program-steps"></a>Passaggi del programma di hosting del servizio

I passaggi nel codice aggiunto per ospitare il servizio sono descritti di seguito:

- **Passaggio 1**: creare un'istanza della `Uri` classe che contenga l'indirizzo di base del servizio. Un URL che contiene un indirizzo di base dispone di un URI facoltativo che identifica un servizio. L'indirizzo di base viene formattato come segue: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` . L'indirizzo di base per il servizio calcolatrice utilizza il trasporto HTTP, localhost, la porta 8000 e il segmento URI GettingStarted.

- **Passaggio 2**: creare un'istanza della <xref:System.ServiceModel.ServiceHost> classe, che viene utilizzata per ospitare il servizio. Il costruttore accetta due parametri: il tipo della classe che implementa il contratto di servizio e l'indirizzo di base del servizio.

- **Passaggio 3**: creare un' <xref:System.ServiceModel.Description.ServiceEndpoint> istanza. Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio. Il <xref:System.ServiceModel.Description.ServiceEndpoint> costruttore è costituito dal tipo di interfaccia del contratto di servizio, da un'associazione e da un indirizzo. Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio. L'associazione per questo esempio è <xref:System.ServiceModel.WSHttpBinding> , ovvero un'associazione incorporata e si connette agli endpoint conformi alle specifiche WS-*. Per ulteriori informazioni sulle associazioni WCF, vedere [Cenni preliminari sulle associazioni WCF](bindings-overview.md). L'indirizzo viene aggiunto all'indirizzo di base per identificare l'endpoint. Il codice specifica l'indirizzo come CalculatorService e l'indirizzo completo per l'endpoint come `http://localhost:8000/GettingStarted/CalculatorService` .

    > [!IMPORTANT]
    > Per .NET Framework versione 4 e successive, l'aggiunta di un endpoint del servizio è facoltativa. Per queste versioni, se non si aggiunge il codice o la configurazione, WCF aggiunge un endpoint predefinito per ogni combinazione di indirizzo di base e contratto implementato dal servizio. Per ulteriori informazioni sugli endpoint predefiniti, vedere [specifica di un indirizzo endpoint](specifying-an-endpoint-address.md). Per ulteriori informazioni sugli endpoint, le associazioni e i comportamenti predefiniti, vedere [Configurazione semplificata](simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](samples/simplified-configuration-for-wcf-services.md).

- **Passaggio 4**: abilitare lo scambio di metadati. I client utilizzano lo scambio di metadati per generare proxy per chiamare le operazioni del servizio. Per abilitare lo scambio di metadati, creare un' <xref:System.ServiceModel.Description.ServiceMetadataBehavior> istanza, impostarne la <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> proprietà su `true` e aggiungere l' `ServiceMetadataBehavior` oggetto alla <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> raccolta dell' <xref:System.ServiceModel.ServiceHost> istanza.

- **Passaggio 5**: aprire <xref:System.ServiceModel.ServiceHost> per restare in attesa dei messaggi in arrivo. L'applicazione attende la pressione del tasto **invio**. Una volta creata l'applicazione <xref:System.ServiceModel.ServiceHost> , viene eseguito un blocco try/catch. Per ulteriori informazioni su come rilevare in modo sicuro le eccezioni generate da <xref:System.ServiceModel.ServiceHost> , vedere [utilizzare Close and Abort per rilasciare le risorse client WCF](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> Quando si aggiunge una libreria di servizi WCF, Visual Studio lo ospita se viene eseguito il debug avviando un host del servizio. Per evitare conflitti, è possibile impedire a Visual Studio di ospitare la libreria del servizio WCF.
>
> 1. Selezionare il progetto **GettingStartedLib** in **Esplora soluzioni** e scegliere **proprietà** dal menu di scelta rapida.
> 2. Selezionare **opzioni WCF** e deselezionare **Avvia host del servizio WCF durante il debug di un altro progetto nella stessa soluzione**.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare e configurare un progetto di app console per l'hosting di un servizio WCF.
> - Aggiungere il codice per ospitare il servizio WCF.
> - Aggiornare il file di configurazione.
> - Avviare il servizio WCF e verificare che sia in esecuzione.

Passare all'esercitazione successiva per apprendere come creare un client WCF.

> [!div class="nextstepaction"]
> [Esercitazione: creare un client WCF](how-to-create-a-wcf-client.md)
