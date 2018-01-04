---
title: 'Procedura: ospitare ed eseguire un servizio Windows Communication Foundation di base'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e1c00abfec36622f5da493165259fb1786ab8d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Procedura: ospitare ed eseguire un servizio Windows Communication Foundation di base
Questa è la terza delle sei attività necessarie per creare un'applicazione [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Per una panoramica di tutte e sei le attività, vedere il [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md) argomento.  
  
 In questo argomento viene descritto come ospitare un servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] in un'applicazione console. Questa procedura è costituita dai passaggi seguenti:  
  
-   Creare un progetto di applicazione console per ospitare il servizio.  
  
-   Creare un host del servizio per il servizio.  
  
-   Consentire lo scambio di metadati.  
  
-   Aprire l’host del servizio.  
  
 Nell'esempio riportato dopo la procedura, viene fornito un elenco completo del codice scritto per questa attività.  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a>Per creare una nuova applicazione console per ospitare il servizio  
  
1.  Creare un nuovo progetto applicazione Console facendo clic su una soluzione di introduzione, se si seleziona, **Aggiungi**, **nuovo progetto**. Nel **Aggiungi nuovo progetto** sul lato sinistro della finestra di dialogo Seleziona **Windows** in **c#** o **VB**. Nella sezione centrale della finestra di dialogo selezionare **applicazione Console**. Denominare il progetto GettingStartedHost.  
  
2.  Impostare il framework di destinazione del progetto GettingStartedHost su .NET Framework 4.5 facendo clic su **GettingStartedHost** in Esplora soluzioni e selezionando **proprietà**. Nella casella a discesa **Framework di destinazione** selezionare **.NET Framework 4.5**. Il framework di destinazione per un progetto VB è leggermente diverso. nella finestra di dialogo Proprietà progetto GettingStartedHost fare clic sul **compilare** scheda sul lato sinistro della schermata e quindi scegliere il **avanzate compilare Opzioni** pulsante nell'angolo inferiore sinistro della finestra di dialogo. Selezionare quindi **.NET Framework 4.5** nella casella a discesa **Framework di destinazione**.  
  
     Impostazione del framework di destinazione causerà [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] per ricaricare la soluzione, premere **OK** quando richiesto.  
  
3.  Aggiungere un riferimento al progetto GettingStartedLib nel progetto GettingStartedHost facendo clic su di **riferimenti** cartella nel progetto GettingStartedHost in Esplora soluzioni e selezionare **Aggiungi riferimento** . Nel **Aggiungi riferimento** finestra di dialogo Seleziona **soluzione** sul lato sinistro della finestra di dialogo e scegliere GettingStartedLib nella sezione centrale della finestra di dialogo e fare clic su **Aggiungi**. In questo modo i tipi definiti in GettingStartedLib diventano disponibili nel progetto GettingStartedHost.  
  
4.  Aggiungere un riferimento a System. ServiceModel nel progetto GettingStartedHost facendo clic con il **riferimento** cartella nel progetto GettingStartedHost in Esplora soluzioni e selezionare **Aggiungi** Riferimento. Nel **Aggiungi riferimento** finestra di dialogo selezionare **Framework** sul lato sinistro della finestra di dialogo. Nella casella di testo di ricerca degli assembly digitare `System.ServiceModel`. Nella sezione centrale della finestra di dialogo selezionare **System. ServiceModel**, fare clic su di **Aggiungi** pulsante, quindi scegliere il **Chiudi** pulsante. Salvare la soluzione facendo clic sul pulsante Salva tutto sotto il menu principale.  
  
### <a name="to-host-the-service"></a>Per ospitare il servizio  
  
-   Aprire il file Program.cs o Module.vb e immettere il codice seguente:  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
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
    'Module1.vb  
    Imports System  
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
  
    1.  Passaggio 1: viene creata un'istanza della classe URI per contenere l'indirizzo di base del servizio. I servizi vengono identificati con un URL contenente un indirizzo di base e un URI facoltativo. L'indirizzo di base è il seguente formato: [Trasporto] :// [nome computer o dominio] [: facoltativo numero di porta] / [segmento URI facoltativo] indirizzo di base per il servizio di calcolatrice utilizza il trasporto HTTP, localhost, porta 8000 e il segmento URI "GettingStarted"  
  
    2.  Passaggio 2: viene creata un'istanza della classe <xref:System.ServiceModel.ServiceHost> per ospitare il servizio. Il costruttore accetta due parametri, il tipo di classe che implementa il contratto di servizio e l'indirizzo di base del servizio.  
  
    3.  Passaggio 3: viene creata una <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` istanza. Un endpoint di un servizio è composto da un indirizzo, un'associazione e un contratto di servizio. Il <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` costruttore accetta pertanto un indirizzo, un'associazione e il tipo di interfaccia di contratto di servizio. Il contratto di servizio è `ICalculator`, definito e implementato nel tipo di servizio. L'associazione utilizzata in questo esempio è <xref:System.ServiceModel.WSHttpBinding>, cioè un'associazione predefinita che viene utilizzata per la connessione agli endpoint conformi alle specifiche WS-*. Per ulteriori informazioni sulle associazioni di WCF, vedere [panoramica delle associazioni WCF](../../../docs/framework/wcf/bindings-overview.md). L'indirizzo viene accodato all'indirizzo di base per identificare l'endpoint. L'indirizzo specificato in questo codice è "CalculatorService", pertanto l'indirizzo completo per l'endpoint è `"http://localhost:8000/GettingStarted/CalculatorService"` aggiunta di un endpoint del servizio è facoltativa quando si utilizza .NET Framework 4.0 o versione successiva. In queste versioni, se non viene aggiunto alcun endpoint nel codice o nella configurazione, ne viene automaticamente aggiunto uno predefinito per ogni combinazione di indirizzo di base e contratto implementata dal servizio. Per ulteriori informazioni sull'impostazione predefinita gli endpoint vedere [specificando un indirizzo Endpoint](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
        > [!IMPORTANT]
        >  L'aggiunta dell'endpoint di un servizio è facoltativa quando si utilizza .NET Framework 4 o versioni successive. In queste versioni, se non viene aggiunto alcun endpoint nel codice o nella configurazione, ne viene automaticamente aggiunto uno predefinito per ogni combinazione di indirizzo di base e contratto implementata dal servizio. Per ulteriori informazioni sull'impostazione predefinita gli endpoint vedere [specificando un indirizzo Endpoint](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
    4.  Passaggio 4: viene abilitato lo scambio di metadati. I client utilizzeranno lo scambio di metadati per generare i proxy che saranno utilizzati per chiamare le operazioni del servizio. Per abilitare lo scambio di metadati, creare un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> dell'istanza, impostarlo del <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> proprietà `true`e aggiungere il comportamento per la <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` insieme del <xref:System.ServiceModel.ServiceHost> istanza.  
  
    5.  Passaggio 5: viene aperto l'oggetto <xref:System.ServiceModel.ServiceHost> per attendere i messaggi in arrivo. Si noti che il codice attende che l'utente prema Invio. In caso contrario, l'applicazione verrà chiusa immediatamente e il servizio verrà arrestato. Si noti inoltre l'utilizzo di un blocco try/catch. Dopo la creazione di un'istanza di <xref:System.ServiceModel.ServiceHost>, tutto l'altro codice viene inserito in un blocco try/catch. Per ulteriori informazioni in modo sicuro intercettare le eccezioni generate da <xref:System.ServiceModel.ServiceHost>, vedere [evitare problemi con l'istruzione Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)  
  
### <a name="to-verify-the-service-is-working"></a>Per verificare il funzionamento del servizio  
  
1.  Eseguire l'applicazione console GettingStartedHost da [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]. In caso di esecuzione in [!INCLUDE[wv](../../../includes/wv-md.md)] e sistemi operativi successivi, il servizio deve essere eseguito con privilegi di amministratore. Poiché [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] è stato eseguito con privilegi di amministratore, anche GettingStartedHost viene eseguito con privilegi di amministratore. È inoltre possibile avviare un nuovo prompt dei comandi che esegua il servizio con privilegi di amministratore e utilizzarlo per eseguire service.exe.  
  
2.  Aprire Internet Explorer e passare alla pagina di debug del servizio in `http://localhost:8000/GettingStarted/CalculatorService`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente sono inclusi il contratto di servizio e l'implementazione dai passaggi precedenti nell'esercitazione e l'hosting del servizio in un'applicazione console.  
  
 Per effettuare la compilazione con un compilatore da riga di comando, compilare IService1.cs e Service1. cs in una classe che fanno riferimento a libreria `System.ServiceModel.dll`. Compilare inoltre Program.cs in un'applicazione console.  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
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
'IService1.vb  
Imports System  
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
'Service1.vb  
Imports System  
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
'Module1.vb  
Imports System  
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
>  Servizi come questo richiedono l'autorizzazione per registrare gli indirizzi HTTP nel computer per l'ascolto. Gli account amministratore dispongono di questa autorizzazione, ma agli account senza privilegi di amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP. [!INCLUDE[crabout](../../../includes/crabout-md.md)]come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). In caso di esecuzione in [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], il servizio.exe deve essere eseguito con privilegi di amministratore.  
  
 Il servizio è ora in esecuzione. Passare alla [procedura: creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Per ulteriori informazioni, vedere [esercitazione introduttiva di risoluzione dei problemi](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)
