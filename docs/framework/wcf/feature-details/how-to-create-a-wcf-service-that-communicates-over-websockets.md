---
title: 'Procedura: creare un servizio WCF che comunica tramite WebSockets'
ms.date: 03/30/2017
ms.assetid: bafbbd89-eab8-4e9a-b4c3-b7b0178e12d8
ms.openlocfilehash: d420ac8fcb98ddec195093be8ae25be37443da4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184981"
---
# <a name="how-to-create-a-wcf-service-that-communicates-over-websockets"></a><span data-ttu-id="d0b7d-102">Procedura: creare un servizio WCF che comunica tramite WebSockets</span><span class="sxs-lookup"><span data-stu-id="d0b7d-102">How to: Create a WCF Service that Communicates over WebSockets</span></span>
<span data-ttu-id="d0b7d-103">I servizi e i client WCF possono usare l'associazione <xref:System.ServiceModel.NetHttpBinding> per comunicare tramite WebSockets.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-103">WCF services and clients can use the <xref:System.ServiceModel.NetHttpBinding> binding to communicate over WebSockets.</span></span>  <span data-ttu-id="d0b7d-104">La tecnologia WebSockets viene usata quando <xref:System.ServiceModel.NetHttpBinding> determina che il contratto di servizio definisce un contratto di callback.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-104">WebSockets will be used when the <xref:System.ServiceModel.NetHttpBinding> determines the service contract defines a callback contract.</span></span> <span data-ttu-id="d0b7d-105">In questo argomento viene descritto come implementare un servizio e un client WCF in cui viene usato l'oggetto <xref:System.ServiceModel.NetHttpBinding> per comunicare tramite WebSockets.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-105">This topic describes how to implement a WCF service and client that uses the <xref:System.ServiceModel.NetHttpBinding> to communicate over WebSockets.</span></span>  
  
### <a name="define-the-service"></a><span data-ttu-id="d0b7d-106">Definire il servizio</span><span class="sxs-lookup"><span data-stu-id="d0b7d-106">Define the Service</span></span>  
  
1. <span data-ttu-id="d0b7d-107">Definire un contratto di callback</span><span class="sxs-lookup"><span data-stu-id="d0b7d-107">Define a callback contract</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IStockQuoteCallback  
        {  
            [OperationContract(IsOneWay = true)]  
            Task SendQuote(string code, double value);  
        }  
    ```  
  
     <span data-ttu-id="d0b7d-108">Questo contratto sarà implementato dall'applicazione client per consentire al servizio di restituire i messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-108">This contract will be implemented by the client application to allow the service to send messages back to the client.</span></span>  
  
2. <span data-ttu-id="d0b7d-109">Definire il contratto di servizio e specificare l'interfaccia `IStockQuoteCallback` come contratto di callback.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-109">Define the service contract and specify the `IStockQuoteCallback` interface as the callback contract.</span></span>  
  
    ```csharp  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
        public interface IStockQuoteService  
        {  
            [OperationContract(IsOneWay = true)]  
            Task StartSendingQuotes();  
        }  
    ```  
  
3. <span data-ttu-id="d0b7d-110">Implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="d0b7d-110">Implement the service contract.</span></span>  
  
    ```csharp
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  

            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="d0b7d-111">L'operazione del servizio `StartSendingQuotes` viene implementata come chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-111">The service operation `StartSendingQuotes` is implemented as an asynchronous call.</span></span> <span data-ttu-id="d0b7d-112">Si recupera il canale di callback usando `OperationContext` e, se il canale è aperto, si effettua una chiamata asincrona sul canale di callback.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-112">We retrieve the callback channel using the `OperationContext` and if the channel is open, we make an async call on the callback channel.</span></span>  
  
4. <span data-ttu-id="d0b7d-113">Configurare il servizio</span><span class="sxs-lookup"><span data-stu-id="d0b7d-113">Configure the service</span></span>  
  
    ```xml  
    <configuration>  
        <appSettings>  
          <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
        </appSettings>  
        <system.web>  
          <compilation debug="true" targetFramework="4.5" />
        </system.web>  
        <system.serviceModel>  
            <protocolMapping>  
              <add scheme="http" binding="netHttpBinding"/>  
              <add scheme="https" binding="netHttpsBinding"/>  
            </protocolMapping>  
            <behaviors>  
                <serviceBehaviors>  
                    <behavior name="">  
                        <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                        <serviceDebug includeExceptionDetailInFaults="false" />  
                    </behavior>  
                </serviceBehaviors>  
            </behaviors>  
            <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
                multipleSiteBindingsEnabled="true" />  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="d0b7d-114">Il file di configurazione del servizio si basa sugli endpoint predefiniti di WCF.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-114">The service’s configuration file relies on WCF’s default endpoints.</span></span> <span data-ttu-id="d0b7d-115">La sezione `<protocolMapping>` viene usata per specificare che `NetHttpBinding` deve essere usato per gli endpoint predefiniti creati.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-115">The `<protocolMapping>` section is used to specify that the `NetHttpBinding` should be used for the default endpoints created.</span></span>  
  
### <a name="define-the-client"></a><span data-ttu-id="d0b7d-116">Definire il client</span><span class="sxs-lookup"><span data-stu-id="d0b7d-116">Define the Client</span></span>  
  
1. <span data-ttu-id="d0b7d-117">Implementare il contratto di callback.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-117">Implement the callback contract.</span></span>  
  
    ```csharp  
    private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
    ```  
  
     <span data-ttu-id="d0b7d-118">L'operazione del contratto di callback viene implementata come metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-118">The callback contract operation is implemented as an asynchronous method.</span></span>  
  
    1. <span data-ttu-id="d0b7d-119">Implementare il codice del client.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-119">Implement the client code.</span></span>  
  
        ```csharp  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                var context = new InstanceContext(new CallbackHandler());  
                var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
                client.StartSendingQuotes();
                Console.ReadLine();  
            }  
  
            private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
        }  
        ```  
  
         <span data-ttu-id="d0b7d-120">L'oggetto CallbackHandler viene ripetuto di seguito per maggiore chiarezza.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-120">The CallbackHandler is repeated here for clarity.</span></span> <span data-ttu-id="d0b7d-121">L'applicazione client crea un nuovo oggetto InstanceContext e specifica l'implementazione dell'interfaccia di callback.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-121">The client application creates a new InstanceContext and specifies the implementation of the callback interface.</span></span> <span data-ttu-id="d0b7d-122">Successivamente, crea un'istanza della classe proxy che invia un riferimento all'oggetto InstanceContext appena creato.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-122">Next it creates an instance of the proxy class sending a reference to the newly created InstanceContext.</span></span> <span data-ttu-id="d0b7d-123">Quando il client chiama il servizio, quest'ultimo chiamerà il client mediante il contratto di callback specificato.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-123">When the client calls the service, the service will call the client using the callback contract specified.</span></span>  
  
    2. <span data-ttu-id="d0b7d-124">Configurare il client</span><span class="sxs-lookup"><span data-stu-id="d0b7d-124">Configure the client</span></span>  
  
        ```xml  
        <?xml version="1.0" encoding="utf-8" ?>  
        <configuration>  
            <startup>
                <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
            </startup>  
            <system.serviceModel>  
                <bindings>  
                    <netHttpBinding>  
                        <binding name="NetHttpBinding_IStockQuoteService">  
                            <webSocketSettings transportUsage="Always" />  
                        </binding>  
                    </netHttpBinding>  
                </bindings>  
                <client>  
                    <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                        binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                        contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
                </client>  
            </system.serviceModel>  
        </configuration>  
        ```  
  
         <span data-ttu-id="d0b7d-125">Per la configurazione del client è sufficiente specificare l'endpoint lato client usando `NetHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-125">There is nothing special you need to do in the client configuration, just specify the client side endpoint using the `NetHttpBinding`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0b7d-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0b7d-126">Example</span></span>  
 <span data-ttu-id="d0b7d-127">Di seguito è riportato il codice completo usato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d0b7d-127">The following is the complete code used in this topic.</span></span>  
  
```csharp  
// IStockQuoteService.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
    public interface IStockQuoteService  
    {  
        [OperationContract(IsOneWay = true)]  
        Task StartSendingQuotes();  
    }  
  
    [ServiceContract]  
    public interface IStockQuoteCallback  
    {  
        [OperationContract(IsOneWay = true)]  
        Task SendQuote(string code, double value);  
    }  
}  
```  
  
```csharp
// StockQuoteService.svc.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  
  
            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
}  
```  
  
```xml  
<?xml version="1.0"?>  
  
<!--  
  For more information on how to configure your ASP.NET application, please visit  
  https://go.microsoft.com/fwlink/?LinkId=169433  
  -->  
  
<configuration>  
    <appSettings>  
      <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
    </appSettings>  
    <system.web>  
      <compilation debug="true" targetFramework="4.5" />
    </system.web>  
    <system.serviceModel>  
        <protocolMapping>  
          <add scheme="http" binding="netHttpBinding"/>  
          <add scheme="https" binding="netHttpsBinding"/>  
        </protocolMapping>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="">  
                    <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                    <serviceDebug includeExceptionDetailInFaults="false" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
        <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
            multipleSiteBindingsEnabled="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
```
<!-- StockQuoteService.svc -->  
<%@ ServiceHost Language="C#" Debug="true" Service="Server.StockQuoteService" CodeBehind="StockQuoteService.svc.cs" %>  
```  
  
```csharp  
// Client.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            var context = new InstanceContext(new CallbackHandler());  
            var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
            client.StartSendingQuotes();
            Console.ReadLine();  
        }  
  
        private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
        {  
            public async Task SendQuoteAsync(string code, double value)  
            {  
                Console.WriteLine("{0}: {1:f2}", code, value);  
            }  
        }  
    }  
}  
```  
  
```xml  
<!--App.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
    </startup>  
    <system.serviceModel>  
        <bindings>  
            <netHttpBinding>  
                <binding name="NetHttpBinding_IStockQuoteService">  
                    <webSocketSettings transportUsage="Always" />  
                </binding>  
            </netHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0b7d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0b7d-128">See also</span></span>

- [<span data-ttu-id="d0b7d-129">Operazioni sincrone e asincrone</span><span class="sxs-lookup"><span data-stu-id="d0b7d-129">Synchronous and Asynchronous Operations</span></span>](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
- [<span data-ttu-id="d0b7d-130">Uso di NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d0b7d-130">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)
