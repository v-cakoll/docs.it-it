---
title: Client ASMX con un servizio WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: fd13d4907f1be09440387a36e14ecdc4926ba7e7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594777"
---
# <a name="asmx-client-with-a-wcf-service"></a>Client ASMX con un servizio WCF

In questo esempio viene illustrato come creare un servizio utilizzando Windows Communication Foundation (WCF) e quindi accedere al servizio da un client non WCF, ad esempio un client ASMX.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

Questo esempio è costituito da un programma di console client (.exe) e da una libreria di servizi (.dll) ospitati da Internet Information Services (IIS). Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta. Il contratto viene definito dall'interfaccia `ICalculator` che espone operazioni matematiche (`Add`, `Subtract`, `Multiply` e `Divide`). Il client ASMX esegue richieste sincrone a un'operazione matematica e il servizio risponde fornendo il risultato.

Il servizio implementa un contratto `ICalculator`, come definito nel codice seguente.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]
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
```

<xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Xml.Serialization.XmlSerializer> eseguono il mapping dei tipi CLR a una rappresentazione XML. <xref:System.Runtime.Serialization.DataContractSerializer> interpreta alcune rappresentazioni XML in modo diverso da XmlSerializer. I generatori di proxy non WCF, ad esempio WSDL. exe, generano un'interfaccia più utilizzabile quando si utilizza XmlSerializer. <xref:System.ServiceModel.XmlSerializerFormatAttribute>Viene applicato all'interfaccia per `ICalculator` assicurarsi che XmlSerializer venga utilizzato per il mapping di tipi CLR a XML. L'implementazione del servizio calcola e restituisce il risultato appropriato.

Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante un file di configurazione (Web.config). L'endpoint è costituito da un indirizzo, un'associazione e un contratto. Il servizio espone l'endpoint dell'indirizzo di base fornito dall'host IIS. L'attributo `binding` è impostato su basicHttpBinding  per fornire la comunicazione HTTP mediante SOAP 1.1, che è conforme a WS-BasicProfile 1.1, come illustrato nella configurazione di esempio seguente.

```xml
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->
    <endpoint address=""
              binding="basicHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
</services>
```

Il client ASMX comunica con il servizio WCF utilizzando un proxy tipizzato generato dall'utilità Web Services Description Language (WSDL) (WSDL. exe). Il proxy tipizzato è contenuto nel file generatedClient.cs. L'utilità WSDL recupera i metadati per il servizio specificato e genera un proxy tipizzato che può essere utilizzato da un client per comunicare. Per impostazione predefinita, il framework non espone metadati. Per esporre i metadati necessari per generare il proxy, è necessario aggiungere un [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) e impostare il relativo `httpGetEnabled` attributo su, `True` come illustrato nella configurazione seguente.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <!-- Setting httpGetEnabled to True on the serviceMetadata
           behavior exposes the service's wsdl at <base address>?wsdl :
           http://localhost/servicemodelsamples/service.svc?wsdl -->
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

Eseguire il comando seguente da un prompt dei comandi nella directory del client per generare il proxy tipizzato.

```console
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl
```

Utilizzando il proxy tipizzato generato, il client può accedere a uno specifico endpoint del servizio configurando l'indirizzo appropriato. Il client utilizza un file di configurazione (App.config) per specificare l'endpoint con il quale comunicare.

```xml
<appSettings>
  <add key="CalculatorServiceAddress"
       value="http://localhost/ServiceModelSamples/service.svc"/>
</appSettings>
```

L'implementazione client costruisce un'istanza del proxy tipizzato per iniziare a comunicare con il servizio.

```csharp
// Create a client to the CalculatorService.
using (CalculatorService client = new CalculatorService())
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

    // Call the Subtract service operation.
    value1 = 145.00D;
    value2 = 76.54D;
    result = client.Subtract(value1, value2);
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

    // Call the Multiply service operation.
    value1 = 9.00D;
    value2 = 81.25D;
    result = client.Multiply(value1, value2);
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

    // Call the Divide service operation.
    value1 = 22.00D;
    value2 = 7.00D;
    result = client.Divide(value1, value2);
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

}

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

> [!NOTE]
> Per ulteriori informazioni sul passaggio e la restituzione di tipi di dati complessi, vedere: [Data Binding in a Windows Forms client](data-binding-in-a-windows-forms-client.md), [associazione dati in un client di Windows Presentation Foundation](data-binding-in-a-wpf-client.md)e [data binding in un client ASP.NET](data-binding-in-an-aspnet-client.md)

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`
