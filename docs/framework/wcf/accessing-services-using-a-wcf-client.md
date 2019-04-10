---
title: Accesso ai servizi tramite client WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 6bf683cdd0a03a5d1dbc452c28e7b33911464f09
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297252"
---
# <a name="accessing-services-using-a-wcf-client"></a>Accesso ai servizi tramite client WCF

Dopo aver creato un servizio, il passaggio successivo consiste nel creare un proxy client WCF. Un'applicazione client usa il proxy client WCF per comunicare con il servizio. Le applicazioni client importano di norma i metadati del servizio per generare codice client WCF che può essere utilizzato per richiamare il servizio.

 Di seguito sono indicati i passaggi di base per la creazione di un client WCF:

1. Compilare il codice del servizio.

2. Generare il proxy client WCF.

3. Creare un'istanza del proxy client WCF.

Il proxy client WCF può essere generato manualmente utilizzando Service Model Metadata Utility Tool (SvcUtil.exe) per altre informazioni, vedere [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Il proxy client WCF può essere generato anche in Visual Studio usando il **Aggiungi riferimento al servizio** funzionalità. Per generare il proxy client WCF usando l'uno o l'altro metodo, è necessario che il servizio sia in esecuzione. Se il servizio è self-hosted, è necessario eseguire l'host. Se il servizio è ospitato in IIS/WAS, non è necessario effettuare nessun'altra operazione.

## <a name="servicemodel-metadata-utility-tool"></a>Strumento ServiceModel Metadata Utility Tool
 Il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) è uno strumento da riga di comando per la generazione di codice dai metadati. Di seguito è riportato un esempio di utilizzo di un comando Svcutil.exe di base.

```
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 In alternativa, è possibile usare Svcutil.exe con file WSDL (Web Services Description Language) e XSD (XML Schema Definition) sul file system.

```
Svcutil.exe <list of WSDL and XSD files on file system>
```

 Il risultato è un file di codice che contiene il codice client WCF che l'applicazione client può usare per richiamare il servizio.

 È inoltre possibile usare lo strumento per generare file di configurazione.

```
Svcutil.exe <file1 [,file2]>
```

 Se viene fornito un solo nome file, si tratta del nome del file di output. Se vengono forniti due nomi file, il primo indica un file di configurazione di input il cui contenuto viene unito con la configurazione generata e scritto nel secondo file. Per altre informazioni sulla configurazione, vedere [configurazione di associazioni per i servizi](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).

> [!IMPORTANT]
> Le richieste di metadati non protette generano rischi esattamente che effettua le richieste di rete non protetta: Se non si è certi che l'endpoint che si sta comunicando sia effettivamente chi dichiara di che è, le informazioni recuperate potrebbero essere i metadati da un servizio dannoso.

## <a name="add-service-reference-in-visual-studio"></a>Aggiungi riferimento al servizio in Visual Studio

 Pulsante destro del mouse con il servizio in esecuzione, fare clic sul progetto che conterrà il proxy client WCF e selezionare **Add** > **riferimento al servizio**. Nel **Aggiungi finestra di dialogo riferimento al servizio**, digitare l'URL per il servizio da chiamare e fare clic sui **Vai** pulsante. Nella finestra di dialogo viene visualizzato un elenco dei servizi disponibili all'indirizzo specificato. Fare doppio clic sul servizio per visualizzare i contratti e operazioni disponibili, specificare uno spazio dei nomi per il codice generato e fare clic sui **OK** pulsante.

## <a name="example"></a>Esempio
 Nell'esempio di codice seguente viene illustrato un contratto di servizio creato per un servizio.

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 Lo strumento ServiceModel Metadata utility Tool e **Aggiungi riferimento al servizio** in Visual Studio genera la seguente classe client WCF. La classe eredita dalla classe generica <xref:System.ServiceModel.ClientBase%601> e implementa l'interfaccia `ICalculator`. Lo strumento genera anche l'interfaccia `ICalculator` (procedure non illustrata di seguito).

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a>Utilizzo del client WCF
 Per usare il client di WCF, creare un'istanza del client WCF e quindi chiamarne i metodi, come illustrato nel codice seguente.

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a>Debug delle eccezioni generate da un client

Molte eccezioni generate da un client WCF sono causate da un'eccezione nel servizio. Di seguito ne vengono riportati alcuni esempi:

-   <xref:System.Net.Sockets.SocketException>: Una connessione esistente chiusa forzatamente dall'host remoto.

-   <xref:System.ServiceModel.CommunicationException>: La connessione sottostante chiusa in modo imprevisto.

-   <xref:System.ServiceModel.CommunicationObjectAbortedException>: La connessione socket è stata interrotta. Questo problema può essere causato da un errore durante l'elaborazione del messaggio, da un timeout di ricezione superato dall'host remoto o da un problema della risorsa di rete sottostante.

Quando si verificano questi tipi di eccezioni, il modo migliore per risolvere il problema è attivare la traccia sul lato servizio e individuare l'eccezione che si è verificata. Per ulteriori informazioni sulla traccia, vedere [Tracing](../../../docs/framework/wcf/diagnostics/tracing/index.md) e [tramite la traccia per risolvere i problemi dell'applicazione](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Procedura: Accedere ai servizi con un contratto duplex](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Procedura: Chiamare operazioni del servizio in modo asincrono](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [Procedura: Accedere ai servizi con contratti unidirezionali e Request/Reply](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [Procedura: Accedere a un servizio WSE 3.0](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [Informazioni sul codice client generato](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)
- [Procedura: Migliorare il tempo di avvio di applicazioni client WCF usando XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [Specifica del comportamento in fase di esecuzione dei client](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [Configurazione dei comportamenti client](../../../docs/framework/wcf/configuring-client-behaviors.md)
