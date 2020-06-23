---
title: Configurazione dei valori di timeout per un'associazione
description: Informazioni su come gestire le impostazioni di timeout per i binding WCF per migliorare le prestazioni, l'usabilità e la sicurezza del servizio.
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: c41824a242d9b42290183cd70b9acf5b8ee59e6b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245115"
---
# <a name="configuring-timeout-values-on-a-binding"></a><span data-ttu-id="7ae43-103">Configurazione dei valori di timeout per un'associazione</span><span class="sxs-lookup"><span data-stu-id="7ae43-103">Configuring Timeout Values on a Binding</span></span>
<span data-ttu-id="7ae43-104">Esistono numerose impostazioni di timeout disponibili nelle associazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="7ae43-104">There are a number of timeout settings available in WCF bindings.</span></span> <span data-ttu-id="7ae43-105">La configurazione corretta di queste impostazioni di timeout non solo può migliorare le prestazioni del servizio, bensì anche svolgere un ruolo nell'usabilità e nella sicurezza del servizio.</span><span class="sxs-lookup"><span data-stu-id="7ae43-105">Setting these timeout settings correctly can improve not only your service’s performance but also play a role in the usability and security of your service.</span></span> <span data-ttu-id="7ae43-106">Nelle associazioni WCF sono disponibili i timeout seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ae43-106">The following timeouts are available on WCF bindings:</span></span>  
  
1. <span data-ttu-id="7ae43-107">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="7ae43-107">OpenTimeout</span></span>  
  
2. <span data-ttu-id="7ae43-108">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="7ae43-108">CloseTimeout</span></span>  
  
3. <span data-ttu-id="7ae43-109">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="7ae43-109">SendTimeout</span></span>  
  
4. <span data-ttu-id="7ae43-110">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="7ae43-110">ReceiveTimeout</span></span>  
  
## <a name="wcf-binding-timeouts"></a><span data-ttu-id="7ae43-111">Timeout di associazioni WCF</span><span class="sxs-lookup"><span data-stu-id="7ae43-111">WCF Binding Timeouts</span></span>  
 <span data-ttu-id="7ae43-112">Ognuna delle impostazioni riportate in questo argomento viene effettuata sull'associazione stessa, nel codice o nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="7ae43-112">Each of the settings discussed in this topic are made on the binding itself, either in code or configuration.</span></span> <span data-ttu-id="7ae43-113">Nel codice seguente viene illustrato come impostare a livello di codice i timeout in un'associazione WCF nel contesto di un servizio self-hosted.</span><span class="sxs-lookup"><span data-stu-id="7ae43-113">The following code shows how to programmatically set timeouts on a WCF binding in the context of a self-hosted service.</span></span>  
  
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
  
 <span data-ttu-id="7ae43-114">Nell'esempio seguente viene illustrato come configurare i timeout su un'associazione in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7ae43-114">The following example shows how to configure timeouts on a binding in a configuration file.</span></span>  
  
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
  
 <span data-ttu-id="7ae43-115">Per altre informazioni su queste impostazioni, vedere la documentazione per la classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="7ae43-115">More information about these settings can be found in the documentation for the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
### <a name="client-side-timeouts"></a><span data-ttu-id="7ae43-116">Timeout lato client</span><span class="sxs-lookup"><span data-stu-id="7ae43-116">Client-side Timeouts</span></span>  
 <span data-ttu-id="7ae43-117">Sul lato client:</span><span class="sxs-lookup"><span data-stu-id="7ae43-117">On the client side:</span></span>  
  
1. <span data-ttu-id="7ae43-118">SendTimeout: usata per inizializzare OperationTimeout, che definisce l'intero processo di invio di un messaggio, inclusa la ricezione di un messaggio di risposta per un'operazione del servizio request/reply.</span><span class="sxs-lookup"><span data-stu-id="7ae43-118">SendTimeout – used to initialize the OperationTimeout, which governs the whole process of sending a message, including receiving a reply message for a request/reply service operation.</span></span> <span data-ttu-id="7ae43-119">Questo timeout si applica anche quando si inviano messaggi di risposta da un metodo del contratto di callback.</span><span class="sxs-lookup"><span data-stu-id="7ae43-119">This timeout also applies when sending reply messages from a callback contract method.</span></span>  
  
2. <span data-ttu-id="7ae43-120">OpenTimeout: usato per l'apertura di canali quando non è specificato alcun valore di timeout esplicito.</span><span class="sxs-lookup"><span data-stu-id="7ae43-120">OpenTimeout – used when opening channels when no explicit timeout value is specified.</span></span>  
  
3. <span data-ttu-id="7ae43-121">CloseTimeout: usato per chiudere i canali quando non è specificato alcun valore di timeout esplicito.</span><span class="sxs-lookup"><span data-stu-id="7ae43-121">CloseTimeout – used when closing channels when no explicit timeout value is specified.</span></span>  
  
4. <span data-ttu-id="7ae43-122">ReceiveTimeout: non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7ae43-122">ReceiveTimeout – is not used.</span></span>  
  
### <a name="service-side-timeouts"></a><span data-ttu-id="7ae43-123">Timeout lato servizio</span><span class="sxs-lookup"><span data-stu-id="7ae43-123">Service-side Timeouts</span></span>  
 <span data-ttu-id="7ae43-124">Sul lato servizio:</span><span class="sxs-lookup"><span data-stu-id="7ae43-124">On the service side:</span></span>  
  
1. <span data-ttu-id="7ae43-125">SendTimeout nell'elemento, OpenTimeout, CloseTimeout sono identici a quelli del client.</span><span class="sxs-lookup"><span data-stu-id="7ae43-125">SendTimeout, OpenTimeout, CloseTimeout are the same as on the client.</span></span>  
  
2. <span data-ttu-id="7ae43-126">ReceiveTimeout: usata a livello del framework dei servizi per inizializzare un timeout di sessione inattiva che controlla la possibile durata dell'inattività di una sessione prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="7ae43-126">ReceiveTimeout – used by the Service Framework Layer to initialize the session-idle timeout which controls how long a session can be idle before timing out.</span></span>
