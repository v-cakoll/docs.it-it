---
title: Configurazione dei valori di timeout per un'associazione
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: f323dfff338f8a3ba24caab6df3b3916d3ae0d13
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339762"
---
# <a name="configuring-timeout-values-on-a-binding"></a><span data-ttu-id="41ee3-102">Configurazione dei valori di timeout per un'associazione</span><span class="sxs-lookup"><span data-stu-id="41ee3-102">Configuring Timeout Values on a Binding</span></span>
<span data-ttu-id="41ee3-103">Esistono numerose impostazioni di timeout disponibili nelle associazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="41ee3-103">There are a number of timeout settings available in WCF bindings.</span></span> <span data-ttu-id="41ee3-104">La configurazione corretta di queste impostazioni di timeout non solo può migliorare le prestazioni del servizio, bensì anche svolgere un ruolo nell'usabilità e nella sicurezza del servizio.</span><span class="sxs-lookup"><span data-stu-id="41ee3-104">Setting these timeout settings correctly can improve not only your service’s performance but also play a role in the usability and security of your service.</span></span> <span data-ttu-id="41ee3-105">Nelle associazioni WCF sono disponibili i timeout seguenti:</span><span class="sxs-lookup"><span data-stu-id="41ee3-105">The following timeouts are available on WCF bindings:</span></span>  
  
1. <span data-ttu-id="41ee3-106">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="41ee3-106">OpenTimeout</span></span>  
  
2. <span data-ttu-id="41ee3-107">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="41ee3-107">CloseTimeout</span></span>  
  
3. <span data-ttu-id="41ee3-108">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="41ee3-108">SendTimeout</span></span>  
  
4. <span data-ttu-id="41ee3-109">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="41ee3-109">ReceiveTimeout</span></span>  
  
## <a name="wcf-binding-timeouts"></a><span data-ttu-id="41ee3-110">Timeout di associazioni WCF</span><span class="sxs-lookup"><span data-stu-id="41ee3-110">WCF Binding Timeouts</span></span>  
 <span data-ttu-id="41ee3-111">Ognuna delle impostazioni riportate in questo argomento viene effettuata sull'associazione stessa, nel codice o nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="41ee3-111">Each of the settings discussed in this topic are made on the binding itself, either in code or configuration.</span></span> <span data-ttu-id="41ee3-112">Nel codice seguente viene illustrato come impostare a livello di codice i timeout in un'associazione WCF nel contesto di un servizio self-hosted.</span><span class="sxs-lookup"><span data-stu-id="41ee3-112">The following code shows how to programmatically set timeouts on a WCF binding in the context of a self-hosted service.</span></span>  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");
    
    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));
        
        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);
        
        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();
        
        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 <span data-ttu-id="41ee3-113">Nell'esempio seguente viene illustrato come configurare i timeout su un'associazione in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="41ee3-113">The following example shows how to configure timeouts on a binding in a configuration file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00" 
                 closeTimeout="00:10:00" 
                 sendTimeout="00:10:00" 
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="41ee3-114">Per altre informazioni su queste impostazioni, vedere la documentazione per la classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="41ee3-114">More information about these settings can be found in the documentation for the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
### <a name="client-side-timeouts"></a><span data-ttu-id="41ee3-115">Timeout lato client</span><span class="sxs-lookup"><span data-stu-id="41ee3-115">Client-side Timeouts</span></span>  
 <span data-ttu-id="41ee3-116">Sul lato client:</span><span class="sxs-lookup"><span data-stu-id="41ee3-116">On the client side:</span></span>  
  
1. <span data-ttu-id="41ee3-117">SendTimeout: usata per inizializzare OperationTimeout, che definisce l'intero processo di invio di un messaggio, inclusa la ricezione di un messaggio di risposta per un'operazione del servizio request/reply.</span><span class="sxs-lookup"><span data-stu-id="41ee3-117">SendTimeout – used to initialize the OperationTimeout, which governs the whole process of sending a message, including receiving a reply message for a request/reply service operation.</span></span> <span data-ttu-id="41ee3-118">Questo timeout si applica anche quando si inviano messaggi di risposta da un metodo del contratto di callback.</span><span class="sxs-lookup"><span data-stu-id="41ee3-118">This timeout also applies when sending reply messages from a callback contract method.</span></span>  
  
2. <span data-ttu-id="41ee3-119">OpenTimeout: usata durante l'apertura di canali quando viene specificato alcun valore di timeout esplicito.</span><span class="sxs-lookup"><span data-stu-id="41ee3-119">OpenTimeout – used when opening channels when no explicit timeout value is specified.</span></span>  
  
3. <span data-ttu-id="41ee3-120">CloseTimeout: usata durante la chiusura di canali viene specificato alcun valore di timeout esplicito.</span><span class="sxs-lookup"><span data-stu-id="41ee3-120">CloseTimeout – used when closing channels when no explicit timeout value is specified.</span></span>  
  
4. <span data-ttu-id="41ee3-121">ReceiveTimeout: non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="41ee3-121">ReceiveTimeout – is not used.</span></span>  
  
### <a name="service-side-timeouts"></a><span data-ttu-id="41ee3-122">Timeout sul lato servizio</span><span class="sxs-lookup"><span data-stu-id="41ee3-122">Service-side Timeouts</span></span>  
 <span data-ttu-id="41ee3-123">Sul lato servizio:</span><span class="sxs-lookup"><span data-stu-id="41ee3-123">On the service side:</span></span>  
  
1. <span data-ttu-id="41ee3-124">SendTimeout, OpenTimeout, CloseTimeout sono identiche a quelle del client.</span><span class="sxs-lookup"><span data-stu-id="41ee3-124">SendTimeout, OpenTimeout, CloseTimeout are the same as on the client.</span></span>  
  
2. <span data-ttu-id="41ee3-125">ReceiveTimeout: usata a livello del framework dei servizi per inizializzare un timeout di sessione inattiva che controlla la possibile durata dell'inattività di una sessione prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="41ee3-125">ReceiveTimeout – used by the Service Framework Layer to initialize the session-idle timeout which controls how long a session can be idle before timing out.</span></span>
