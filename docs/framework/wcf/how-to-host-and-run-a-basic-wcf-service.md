---
title: 'Esercitazione: Ospitare ed eseguire un servizio Windows Communication Foundation di base'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: ad9536b1f27ba3945bf76d0474de4825033a1e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929103"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Esercitazione: Ospitare ed eseguire un servizio Windows Communication Foundation di base

Questa esercitazione illustra il terzo di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Iniziare con le applicazioni di Windows Communication Foundation](getting-started-tutorial.md).

L'attività successiva per la creazione di un'applicazione WCF deve ospitare un servizio WCF in un'applicazione console. Un servizio WCF espone uno o più *endpoint*, ognuno dei quali espone una o più operazioni del servizio. Un endpoint del servizio specifica le informazioni seguenti: 
- Un indirizzo in cui è possibile trovare il servizio.
- Un'associazione che contiene le informazioni che descrivono come un client deve comunicare con il servizio. 
- Un contratto che definisce la funzionalità che il servizio offre ai propri client.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> - Creare e configurare un progetto di app console per ospitare un servizio WCF.
> - Aggiungere codice per ospitare il servizio WCF.
> - Aggiornare il file di configurazione.
> - Avviare il servizio WCF e verificare sia in esecuzione.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Creare e configurare un progetto di app console per l'hosting del servizio

1. Creare un progetto app console in Visual Studio: 
 
    1. Dal **File** dal menu **Open** > **progetto/soluzione** e passare alla **GettingStarted** soluzione si creato in precedenza (*GettingStarted.sln*). Selezionare **Apri**.

    2. Dal **View** dal menu **Esplora soluzioni**.
    
    3. Nel **Esplora soluzioni** finestra, seleziona la **GettingStarted** soluzione (nodo in alto) e quindi selezionare **Add** > **nuovo progetto** dal menu di scelta rapida. 

    4. Nel **Aggiungi nuovo progetto** finestra a sinistra, seleziona il **Desktop di Windows** categoria sotto **Visual C#**  oppure **Visual Basic**. 

    5. Selezionare il **App Console (.NET Framework)** modello, quindi immettere *GettingStartedHost* per il **nome**. Scegliere **OK**.

2. Aggiungere un riferimento nel **GettingStartedHost** del progetto per il **GettingStartedLib** progetto: 

    1. Nel **Esplora soluzioni** finestra, seleziona la **riferimenti** cartella sotto la **GettingStartedHost** del progetto e quindi selezionare **Aggiungi riferimento** dal menu di scelta rapida. 

    2. Nel **Aggiungi riferimento** finestra di dialogo, sotto **progetti** sul lato sinistro della finestra, selezionare **soluzione**. 
 
    3. Selezionare **GettingStartedLib** nella sezione centrale della finestra e quindi selezionare **OK**. 

       Questa azione rende i tipi definiti nel **GettingStartedLib** progetto disponibili per il **GettingStartedHost** progetto.

3. Aggiungere un riferimento nel **GettingStartedHost** del progetto per il <xref:System.ServiceModel> assembly: 

    1. Nel **Esplora soluzioni** finestra, seleziona la **riferimenti** cartella sotto la **GettingStartedHost** del progetto e quindi selezionare **Aggiungi riferimento** dal menu di scelta rapida.
    
    2. Nel **Aggiungi riferimento** finestra, sotto **assembly** sul lato sinistro della finestra, selezionare **Framework**. 

    3. Selezionare **System. ServiceModel**, quindi selezionare **OK**. 
    
    4. Salvare la soluzione selezionando **File** > **Salva tutto**.

## <a name="add-code-to-host-the-service"></a>Aggiungere il codice per ospitare il servizio

Per ospitare il servizio, si aggiunge codice per eseguire i passaggi seguenti: 
   1. Creare un URI per l'indirizzo di base.
   2. Creare un'istanza della classe per l'hosting del servizio.
   3. Creare un endpoint del servizio.
   4. Consentire lo scambio di metadati.
   5. Aprire l'host del servizio per l'ascolto dei messaggi in arrivo.
  
Apportare le modifiche seguenti al codice:

1. Aprire il **Program.cs** o **Module1.vb** del file nei **GettingStartedHost** del progetto e sostituire il codice con il codice seguente:

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
    
    Per informazioni sul funzionamento di questo codice, vedere [servizio di hosting passaggi programma](#service-hosting-program-steps).

2. Aggiornare le proprietà del progetto:

   1. Nel **Esplora soluzioni** finestra, seleziona la **GettingStartedHost** cartella e quindi selezionare **proprietà** dal menu di scelta rapida.

   2. Nel **GettingStartedHost** pagina delle proprietà, seleziona la **applicazione** scheda:

      - Per C# progetti, selezionare **GettingStartedHost.Program** dal **oggetto di avvio** elenco.

      - Per i progetti Visual Basic, selezionare **Service.Program** dalle **oggetto di avvio** elenco.

   3. Dal **File** dal menu **Salva tutto**.

## <a name="verify-the-service-is-working"></a>Verificare che il servizio sia in funzione

1. Compilare la soluzione e quindi eseguire la **GettingStartedHost** console all'applicazione dall'interno di Visual Studio. 

    Il servizio deve essere eseguito con privilegi di amministratore. Poiché è stato aperto Visual Studio con privilegi di amministratore, quando si esegue **GettingStartedHost** in Visual Studio, l'applicazione viene eseguita con privilegi di amministratore anche. In alternativa, è possibile aprire un nuovo prompt dei comandi come amministratore (selezionare **altre** > **Esegui come amministratore** dal menu di scelta) ed eseguire **GettingStartedHost.exe**  in esso contenuti.

2. Aprire un web browser e passare alla pagina del servizio all'indirizzo `http://localhost:8000/GettingStarted/CalculatorService`.
   
   > [!NOTE]
   > Servizi come questo richiedono l'autorizzazione appropriata per registrare indirizzi HTTP nel computer in ascolto. Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP. Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS). 

## <a name="service-hosting-program-steps"></a>Procedura programma host di servizio

I passaggi descritti nel codice che aggiunto per ospitare il servizio sono descritte come segue:

- **Passaggio 1**: Creare un'istanza di `Uri` classe per contenere l'indirizzo di base del servizio. Un URL che contiene un indirizzo di base ha un URI facoltativo che identifica un servizio. L'indirizzo di base è formattato come segue: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`. L'indirizzo di base per il servizio calcolatrice utilizza il trasporto HTTP, localhost, la porta 8000 e il segmento URI, GettingStarted.

- **Passaggio 2**: Creare un'istanza di <xref:System.ServiceModel.ServiceHost> (classe), che consente di ospitare il servizio. Il costruttore accetta due parametri: il tipo della classe che implementa il contratto di servizio e l'indirizzo di base del servizio.

- **Passaggio 3**: Creare un'istanza di <xref:System.ServiceModel.Description.ServiceEndpoint>. Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio. Il <xref:System.ServiceModel.Description.ServiceEndpoint> costruttore è costituito da un indirizzo, un'associazione e il tipo di interfaccia di contratto di servizio. Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio. L'associazione per questo esempio è <xref:System.ServiceModel.WSHttpBinding>, che è un'associazione predefinita e si connette agli endpoint conformi a WS-* specifiche. Per altre informazioni sulle associazioni di WCF, vedere [panoramica delle associazioni WCF](bindings-overview.md). Si accodare l'indirizzo per l'indirizzo di base per identificare l'endpoint. Il codice specifica l'indirizzo come CalculatorService e l'indirizzo completo dell'endpoint come `http://localhost:8000/GettingStarted/CalculatorService`.

    > [!IMPORTANT]
    > Per .NET Framework versione 4 e versioni successive, l'aggiunta di un endpoint del servizio è facoltativa. Per queste versioni, se non si aggiunge il codice o configurazione, WCF aggiunge un endpoint predefinito per ogni combinazione di indirizzo di base e contratto implementato dal servizio. Per altre informazioni sugli endpoint predefiniti, vedere [che specifica un indirizzo endpoint](specifying-an-endpoint-address.md). Per altre informazioni sull'endpoint predefiniti, associazioni e comportamenti, vedere [configurazione semplificata](simplified-configuration.md) e [configurazione semplificata per i servizi WCF](samples/simplified-configuration-for-wcf-services.md).

- **Passaggio 4**: Consentire lo scambio di metadati. I client di usano lo scambio di metadati per generare i proxy per chiamare le operazioni del servizio. Per abilitare lo scambio di metadati, creare un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> dell'istanza, impostare relativi <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> proprietà `true`e aggiungere il `ServiceMetadataBehavior` dell'oggetto per il <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> insieme del <xref:System.ServiceModel.ServiceHost> istanza.

- **Passaggio 5**: Apri <xref:System.ServiceModel.ServiceHost> in ascolto dei messaggi in ingresso. L'applicazione attende che venga premuto **invio**. Dopo l'applicazione crea un'istanza <xref:System.ServiceModel.ServiceHost>, esegue un blocco try/catch. Per altre informazioni su una rilevazione sicura delle eccezioni generate da <xref:System.ServiceModel.ServiceHost>, vedere [utilizzare Chiudi e Interrompi per rilasciare le risorse del client WCF](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> Quando si aggiunge una libreria di servizi WCF, Visual Studio lo ospita automaticamente se si esegue il debug, avviando un host del servizio. Per evitare conflitti, è possibile impedire Visual Studio che ospita la libreria di servizi WCF. 
> 1. Selezionare il **GettingStartedLib** del progetto **Esplora soluzioni** e scegliere **proprietà** dal menu di scelta rapida.
> 2. Selezionare **opzioni WCF** e deselezionare **avvia Host del servizio WCF durante il debug di un altro progetto nella stessa soluzione**.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> - Creare e configurare un progetto di app console per ospitare un servizio WCF.
> - Aggiungere codice per ospitare il servizio WCF.
> - Aggiornare il file di configurazione.
> - Avviare il servizio WCF e verificare sia in esecuzione.

Passare all'esercitazione successiva per informazioni su come creare un client WCF.

> [!div class="nextstepaction"]
> [Esercitazione: Creare un client WCF](how-to-create-a-wcf-client.md)
