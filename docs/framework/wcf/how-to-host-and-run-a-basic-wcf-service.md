---
title: Come ospitare ed eseguire un servizio Windows Communication Foundation di base
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 3a029ef23ba3e9a0dd62e410739fa8734acc202a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277771"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Come ospitare ed eseguire un servizio Windows Communication Foundation di base

Questa è la terza delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](getting-started-tutorial.md).

In questo articolo viene descritto come ospitare un servizio Windows Communication Foundation (WCF) in un'applicazione console. Questa procedura è costituita dai passaggi seguenti:

- Creare un progetto di applicazione console per ospitare il servizio.

- Creare un host del servizio per il servizio.

- Consentire lo scambio di metadati.

- Aprire l’host del servizio.

Nell'esempio riportato dopo la procedura, viene fornito un elenco completo del codice scritto per questa attività.

## <a name="create-a-new-console-application-to-host-the-service"></a>Creare una nuova applicazione console per ospitare il servizio

1. Creare un nuovo progetto di applicazione Console in Visual Studio facendo clic sulla soluzione di introduzione e selezionando **Add** > **nuovo progetto**. Nel **Aggiungi nuovo progetto** finestra di dialogo sul lato sinistro, seleziona la **Desktop di Windows** categoria sotto **Visual c#** oppure **Visual Basic**. Selezionare il **App Console (.NET Framework)** modello e quindi denominare il progetto **GettingStartedHost**.

2. Aggiungere un riferimento al progetto GettingStartedLib nel progetto GettingStartedHost. Fare clic sui **riferimenti** cartella nel progetto GettingStartedHost in **Esplora soluzioni**e quindi selezionare **Aggiungi riferimento**. Nel **Aggiungi riferimento** finestra di dialogo, seleziona **soluzione** sul lato sinistro della finestra di dialogo, scegliere GettingStartedLib nella sezione centrale della finestra di dialogo e quindi scegliere **Add**. In questo modo i tipi definiti in GettingStartedLib diventano disponibili nel progetto GettingStartedHost.

3. Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedHost. Fare doppio clic il **riferimenti** cartella nel progetto GettingStartedHost in **Esplora soluzioni** e selezionare **Aggiungi riferimento**. Nel **Aggiungi riferimento** finestra di dialogo, seleziona **Framework** sul lato sinistro della finestra di dialogo sotto **assembly**. Individuare e selezionare **System. ServiceModel**, quindi scegliere **OK**. Salvare la soluzione selezionando **File** > **Salva tutto**.

## <a name="host-the-service"></a>Host del servizio

Aprire il file Program.cs o Module.vb e immettere il codice seguente:

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
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

**Passaggio 1** -crea un'istanza della classe Uri per contenere l'indirizzo di base del servizio. I servizi vengono identificati con un URL contenente un indirizzo di base e un URI facoltativo. L'indirizzo di base ha il formato seguente: [trasporto]://[nome-computer o dominio][:n. porta facoltativo]/[segmento URI facoltativo]. Nell'indirizzo di base per il servizio calcolatrice vengono utilizzati il trasporto HTTP, il localhost, la porta 8000 e il segmento URI "GettingStarted"

**Passaggio 2** : crea un'istanza di <xref:System.ServiceModel.ServiceHost> classe per ospitare il servizio. Il costruttore accetta due parametri, il tipo di classe che implementa il contratto di servizio e l'indirizzo di base del servizio.

**Passaggio 3** – consente di creare un <xref:System.ServiceModel.Description.ServiceEndpoint> istanza. Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio. Il costruttore di <xref:System.ServiceModel.Description.ServiceEndpoint> accetta quindi il tipo di interfaccia del contratto di servizio, un'associazione e un indirizzo. Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio. L'associazione utilizzata in questo esempio è <xref:System.ServiceModel.WSHttpBinding>, cioè un'associazione predefinita che viene utilizzata per la connessione agli endpoint conformi alle specifiche WS-*. Per ulteriori informazioni sulle associazioni di WCF, vedere [Panoramica sulle associazioni di Windows Communication Foundation](bindings-overview.md). L'indirizzo viene accodato all'indirizzo di base per identificare l'endpoint. L'indirizzo specificato in questo codice è "CalculatorService" in modo che l'indirizzo completo per l'endpoint è `"http://localhost:8000/GettingStarted/CalculatorService"`.

    > [!IMPORTANT]
    > Adding a service endpoint is optional when using .NET Framework 4 or later. In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service. For more information about default endpoints see [Specifying an Endpoint Address](specifying-an-endpoint-address.md). For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).

**Passaggio 4** : consentire lo scambio di metadati. I client utilizzeranno lo scambio di metadati per generare i proxy che saranno utilizzati per chiamare le operazioni del servizio. Per abilitare lo scambio di metadati, creare un'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, impostare la relativa proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true` e aggiungere il comportamento alla raccolta <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> dell'istanza di <xref:System.ServiceModel.ServiceHost>.

**Passaggio 5** : aprire il <xref:System.ServiceModel.ServiceHost> in ascolto dei messaggi in ingresso. Si noti che il codice attende che l'utente prema Invio. In caso contrario, l'applicazione verrà chiusa immediatamente e il servizio verrà arrestato. Si noti inoltre l'utilizzo di un blocco try/catch. Dopo la creazione di un'istanza di <xref:System.ServiceModel.ServiceHost>, tutto l'altro codice viene inserito in un blocco try/catch. Per altre informazioni su una rilevazione sicura delle eccezioni generate da <xref:System.ServiceModel.ServiceHost>, vedere [utilizzare Chiudi e Interrompi per rilasciare le risorse del client WCF](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> Modificare app. config in gettingstartedlib diventano in modo da riflettere le modifiche apportate nel codice:
> 1. Modificare la riga 14 per `<service name="GettingStartedLib.CalculatorService">`
> 2. Modificare la riga 17 per `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
> 3. Modificare la riga 22 per `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

## <a name="verify-the-service-is-working"></a>Verificare che il servizio sia in funzione

1. Esegue la console GettingStartedHost all'applicazione dall'interno di Visual Studio.

   Il servizio deve essere eseguito con privilegi di amministratore. Visual Studio è stata aperta con privilegi di amministratore, anche GettingStartedHost viene eseguito con privilegi di amministratore. È anche possibile aprire un nuovo prompt dei comandi usando **Esegui come amministratore** ed eseguire service.exe in esso contenuti.

2. Aprire un web browser e passare alla pagina di debug del servizio all'indirizzo `http://localhost:8000/GettingStarted/CalculatorService`.

## <a name="example"></a>Esempio

Nell'esempio seguente sono inclusi il contratto di servizio e l'implementazione dai passaggi precedenti nell'esercitazione e l'hosting del servizio in un'applicazione console.

Per effettuare la compilazione con un compilatore da riga di comando, compilare IService1.cs e Service1.cs in una libreria di classi che fa riferimento a `System.ServiceModel.dll`. Compilare inoltre Program.cs come applicazione console.

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
        public interface ICalculator
        {
            [OperationContract]
            double Add(double n1, double n2);
            [OperationContract]
            double Subtract(double n1, double n2);
            [OperationContract]
            double Multiply(double n1, double n2);
            [OperationContract]
            double Divide(double n1, double n2);
        }
}
```

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

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
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> Servizi come questo richiedono l'autorizzazione per registrare gli indirizzi HTTP nel computer per l'ascolto. Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP. Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS). In caso di esecuzione in Visual Studio, il servizio.exe deve essere eseguito con privilegi di amministratore.

## <a name="next-steps"></a>Passaggi successivi

Il servizio è ora in esecuzione. Nell'attività successiva, si crea un client WCF.

> [!div class="nextstepaction"]
> [Procedura: Creare un client WCF](how-to-create-a-wcf-client.md)

Per altre informazioni, vedere [Troubleshooting the Getting Started Tutorial](troubleshooting-the-getting-started-tutorial.md) (Risoluzione dei problemi relativi all'esercitazione introduttiva).

## <a name="see-also"></a>Vedere anche

- [Introduzione](samples/getting-started-sample.md)
- [Servizio indipendente](samples/self-host.md)