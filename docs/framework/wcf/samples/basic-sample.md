---
title: Esempio di base
ms.date: 03/30/2017
ms.assetid: c1910bc1-3d0a-4fa6-b12a-4ed6fe759620
ms.openlocfilehash: 2ea5af0a1c05b5632632b2619c0ee4813696d2fc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738178"
---
# <a name="basic-sample"></a>Esempio di base

In questo esempio viene illustrato come rendere individuabile un servizio e come cercare e chiamare un servizio individuabile. Questo esempio è costituito da due progetti, ovvero il servizio e il client.

> [!NOTE]
> In questo esempio l'individuazione viene implementata nel codice.  Per un esempio di implementazione dell'individuazione nella configurazione, vedere [configurazione](../../../../docs/framework/wcf/samples/configuration-sample.md).

## <a name="service"></a>Servizio

Si tratta di una semplice implementazione del servizio di calcolatrice. Il codice correlato all'individuazione è disponibile in `Main` dove un oggetto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> viene aggiunto all'host del servizio e un oggetto <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> viene aggiunto come illustrato nel codice seguente.

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new
      WSHttpBinding(), String.Empty);

    // Make the service discoverable over UDP multicast
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    serviceHost.Open();
    // ...
}
```

## <a name="client"></a>Client

Il client usa un oggetto <xref:System.ServiceModel.Discovery.DynamicEndpoint> per individuare il servizio. <xref:System.ServiceModel.Discovery.DynamicEndpoint> è un endpoint standard che risolve l'endpoint del servizio all'apertura del client. In questo caso, <xref:System.ServiceModel.Discovery.DynamicEndpoint> cerca il servizio basato sul contratto di servizio. Per impostazione predefinita, <xref:System.ServiceModel.Discovery.DynamicEndpoint> esegue la ricerca su <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>. Dopo aver individuato un endpoint del servizio, il client si connette al servizio sull'associazione specificata.

```csharp
public static void Main()
{
   DynamicEndpoint dynamicEndpoint = new DynamicEndpoint( ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());
   // ...
}
```

Il client definisce un metodo denominato `InvokeCalculatorService` che usa la classe <xref:System.ServiceModel.Discovery.DiscoveryClient> per la ricerca di servizi. <xref:System.ServiceModel.Discovery.DynamicEndpoint> eredita da <xref:System.ServiceModel.Description.ServiceEndpoint>, pertanto può essere passato al metodo `InvokeCalculatorService`. Nell'esempio viene quindi usato <xref:System.ServiceModel.Discovery.DynamicEndpoint> per creare un'istanza di `CalculatorServiceClient` e chiamare le varie operazioni del servizio di calcolatrice.

```csharp
static void InvokeCalculatorService(ServiceEndpoint serviceEndpoint)
{
   // Create a client
   CalculatorServiceClient client = new CalculatorServiceClient(serviceEndpoint);

   Console.WriteLine("Invoking CalculatorService");
   Console.WriteLine();

   double value1 = 100.00D;
   double value2 = 15.99D;

   // Call the Add service operation.
   double result = client.Add(value1, value2);
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

   // Call the Subtract service operation.
   result = client.Subtract(value1, value2);
   Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

   // Call the Multiply service operation.
   result = client.Multiply(value1, value2);
   Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

   // Call the Divide service operation.
   result = client.Divide(value1, value2);
   Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);
   Console.WriteLine();

   //Closing the client gracefully closes the connection and cleans up resources
   client.Close();
}
```

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Questo esempio usa endpoint HTTP e per eseguirlo è necessario aggiungere elenchi di controllo di accesso (ACL) agli URL appropriati. Per ulteriori informazioni, vedere [configurazione di http e HTTPS](../feature-details/configuring-http-and-https.md). L'esecuzione del comando seguente con privilegi elevati consente di aggiungere gli elenchi di controllo di accesso appropriati. È possibile che si desideri sostituire il dominio e il nome utente per gli argomenti seguenti quando il comando non funziona nella forma originale. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. Utilizzando Visual Studio 2012, aprire il. sln di base e compilare l'esempio.

3. Eseguire l'applicazione service.exe.

4. Dopo aver avviato il servizio, eseguire client.exe.

5. Si osservi che il client è stato in grado di trovare il servizio senza conoscerne l'indirizzo.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Basic`
