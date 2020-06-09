---
title: Impostazioni consigliate per la traccia e la registrazione dei messaggi
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: 9d2586570a3f590735c2a8e1ca176580886c8d92
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578916"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a>Impostazioni consigliate per la traccia e la registrazione dei messaggi
In questo argomento vengono illustrate le impostazioni consigliate di traccia e registrazione dei messaggi per diversi ambienti operativi.  
  
## <a name="recommended-settings-for-a-production-environment"></a>Impostazioni consigliate per un ambiente di produzione  
 Per un ambiente di produzione, se si usano origini di traccia WCF, impostare `switchValue` su Avviso. Se si usa l'origine di traccia WCF `System.ServiceModel`, impostare l'attributo `switchValue` su `Warning` e l'attributo `propagateActivity` su `true`. Se si usa un'origine di traccia definita dall'utente, impostare l'attributo `switchValue` su `Warning, ActivityTracing`. Questa operazione può essere eseguita manualmente tramite lo [strumento Editor di configurazione (SvcConfigEditor. exe)](../../configuration-editor-tool-svcconfigeditor-exe.md). Se non si prevede un calo delle prestazioni, è possibile impostare l'attributo `switchValue` su `Information` in tutti i casi prima menzionati, generando così una notevole quantità di dati di traccia. Nell'esempio seguente vengono illustrate queste impostazioni consigliate.  
  
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
  
## <a name="recommended-settings-for-deployment-or-debugging"></a>Impostazioni consigliate per la distribuzione o il debug  
 Per ambienti di distribuzione o di debug, scegliere `Information` o `Verbose`, insieme a `ActivityTracing` per un'origine di traccia definita dall'utente o `System.ServiceModel`. Per ottimizzare il debug, è necessario inoltre aggiungere un'ulteriore origine di traccia (`System.ServiceModel.MessageLogging`) alla configurazione per abilitare la registrazione dei messaggi. Si noti che l'attributo `switchValue` non ha alcun impatto su questa origine di traccia.  
  
 Nell'esempio seguente vengono illustrate le impostazioni consigliate, mediante un listener condiviso che usa `XmlWriterTraceListener`.  
  
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
  
## <a name="using-wmi-to-modify-settings"></a>Uso di WMI per modificare le impostazioni  
 È possibile usare WMI per modificare le impostazioni di configurazione in fase di runtime (abilitando l'attributo `wmiProviderEnabled` nella configurazione, come dimostrato nel precedente esempio di configurazione). Ad esempio, è possibile usare WMI all'interno di strumenti CIM per modificare i livelli dell'origine di traccia da Avviso a Informazioni in fase di esecuzione. È necessario tenere presente che il costo in termini di prestazioni del debug attivo eseguito in questo modo può essere molto elevato. Per ulteriori informazioni sull'utilizzo di WMI, vedere l'argomento [using Strumentazione gestione Windows for Diagnostics](../wmi/index.md) .  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a>Attivare eventi correlati in un'analisi di ASP.NET  
 Gli eventi ASP.NET non impostano l'ID di correlazione (ActivityID) a meno che la traccia degli eventi ASP.NET non sia abilitata. Per visualizzare correttamente gli eventi correlati, è necessario attivare la traccia degli eventi di ASP.NET usando il comando seguente nella console dei comandi, che può essere richiamata da **avvio**, **Esegui** e digitare **cmd**,  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 Per disattivare l'analisi degli eventi ASP.NET, usare il comando seguente,  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di Strumentazione gestione Windows per la diagnostica](../wmi/index.md)
