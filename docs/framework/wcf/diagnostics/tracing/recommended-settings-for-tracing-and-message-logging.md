---
title: Impostazioni consigliate per la traccia e la registrazione dei messaggi
description: Informazioni sulle impostazioni di traccia e registrazione dei messaggi consigliate per diversi ambienti operativi in WCF.
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: 71067a4d6f4cec65a148a8162c40e44d82b85784
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245326"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="9ac44-103">Impostazioni consigliate per la traccia e la registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="9ac44-103">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="9ac44-104">In questo argomento vengono illustrate le impostazioni consigliate di traccia e registrazione dei messaggi per diversi ambienti operativi.</span><span class="sxs-lookup"><span data-stu-id="9ac44-104">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="9ac44-105">Impostazioni consigliate per un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="9ac44-105">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="9ac44-106">Per un ambiente di produzione, se si usano origini di traccia WCF, impostare `switchValue` su Avviso.</span><span class="sxs-lookup"><span data-stu-id="9ac44-106">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="9ac44-107">Se si usa l'origine di traccia WCF `System.ServiceModel`, impostare l'attributo `switchValue` su `Warning` e l'attributo `propagateActivity` su `true`.</span><span class="sxs-lookup"><span data-stu-id="9ac44-107">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="9ac44-108">Se si usa un'origine di traccia definita dall'utente, impostare l'attributo `switchValue` su `Warning, ActivityTracing`.</span><span class="sxs-lookup"><span data-stu-id="9ac44-108">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="9ac44-109">Questa operazione può essere eseguita manualmente tramite lo [strumento Editor di configurazione (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9ac44-109">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="9ac44-110">Se non si prevede un calo delle prestazioni, è possibile impostare l'attributo `switchValue` su `Information` in tutti i casi prima menzionati, generando così una notevole quantità di dati di traccia.</span><span class="sxs-lookup"><span data-stu-id="9ac44-110">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="9ac44-111">Nell'esempio seguente vengono illustrate queste impostazioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="9ac44-111">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="9ac44-112">Impostazioni consigliate per la distribuzione o il debug</span><span class="sxs-lookup"><span data-stu-id="9ac44-112">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="9ac44-113">Per ambienti di distribuzione o di debug, scegliere `Information` o `Verbose`, insieme a `ActivityTracing` per un'origine di traccia definita dall'utente o `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="9ac44-113">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="9ac44-114">Per ottimizzare il debug, è necessario inoltre aggiungere un'ulteriore origine di traccia (`System.ServiceModel.MessageLogging`) alla configurazione per abilitare la registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9ac44-114">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="9ac44-115">Si noti che l'attributo `switchValue` non ha alcun impatto su questa origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="9ac44-115">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="9ac44-116">Nell'esempio seguente vengono illustrate le impostazioni consigliate, mediante un listener condiviso che usa `XmlWriterTraceListener`.</span><span class="sxs-lookup"><span data-stu-id="9ac44-116">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="9ac44-117">Uso di WMI per modificare le impostazioni</span><span class="sxs-lookup"><span data-stu-id="9ac44-117">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="9ac44-118">È possibile usare WMI per modificare le impostazioni di configurazione in fase di runtime (abilitando l'attributo `wmiProviderEnabled` nella configurazione, come dimostrato nel precedente esempio di configurazione).</span><span class="sxs-lookup"><span data-stu-id="9ac44-118">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="9ac44-119">Ad esempio, è possibile usare WMI all'interno di strumenti CIM per modificare i livelli dell'origine di traccia da Avviso a Informazioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9ac44-119">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="9ac44-120">È necessario tenere presente che il costo in termini di prestazioni del debug attivo eseguito in questo modo può essere molto elevato.</span><span class="sxs-lookup"><span data-stu-id="9ac44-120">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="9ac44-121">Per ulteriori informazioni sull'utilizzo di WMI, vedere l'argomento [using Strumentazione gestione Windows for Diagnostics](../wmi/index.md) .</span><span class="sxs-lookup"><span data-stu-id="9ac44-121">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="9ac44-122">Attivare eventi correlati in un'analisi di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ac44-122">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="9ac44-123">Gli eventi ASP.NET non impostano l'ID di correlazione (ActivityID) a meno che la traccia degli eventi ASP.NET non sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="9ac44-123">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="9ac44-124">Per visualizzare correttamente gli eventi correlati, è necessario attivare la traccia degli eventi di ASP.NET usando il comando seguente nella console dei comandi, che può essere richiamata da **avvio**, **Esegui** e digitare **cmd**,</span><span class="sxs-lookup"><span data-stu-id="9ac44-124">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="9ac44-125">Per disattivare l'analisi degli eventi ASP.NET, usare il comando seguente,</span><span class="sxs-lookup"><span data-stu-id="9ac44-125">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ac44-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ac44-126">See also</span></span>

- [<span data-ttu-id="9ac44-127">Uso di Strumentazione gestione Windows per la diagnostica</span><span class="sxs-lookup"><span data-stu-id="9ac44-127">Using Windows Management Instrumentation for Diagnostics</span></span>](../wmi/index.md)
