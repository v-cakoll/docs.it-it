---
title: '&lt;diagnostica&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d558bf6ac71a3a19fb8c28989fd9262e7a13f0f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiagnosticsgt"></a>&lt;diagnostica&gt;
L'elemento `diagnostics` definisce le impostazioni che possono essere usate da un amministratore per il controllo e l'ispezione in fase di esecuzione.  
  
 \<System. ServiceModel >  
\<diagnostica >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>  
   <diagnostics etwProviderId="String"       performanceCounters="Off/ServiceOnly/All/Default"              wmiProviderEnabled="Boolean" >       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
          maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
             <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|etwProviderId|Stringa che specifica l'identificatore per il provider Event-Tracing che determina la scrittura di eventi nelle sessioni ETW.|  
|performanceCounters|Specifica se sono abilitati i contatori delle prestazioni per l'assembly. I valori validi sono:<br /><br /> -Off: I contatori delle prestazioni sono disattivati.<br />-ServiceOnly: Solo i contatori delle prestazioni attinente a questo servizio è abilitato.<br />-Tutto: Prestazioni contatori possono essere visualizzati in fase di esecuzione.<br />-Impostazione predefinita: Viene creata un'istanza del contatore singolo prestazioni wcf_admin. L'istanza viene usata per attivare la raccolta di dati SQM che devono essere usati dall'infrastruttura. Nessuno dei valori di contatore per questa istanza è aggiornato e pertanto rimarrà a zero. Questo è il valore predefinito se per WCF non è presente alcuna configurazione.|  
|wmiProviderEnabled|Valore booleano che specifica se il provider WMI per l'assembly è abilitato. Il provider WMI è necessario per consentire all'utente di ottenere l'accesso in fase di esecuzione alle funzionalità di ispezione e controllo di Windows Communication Foundation (WCF). Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endToEndTracing >](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.|  
|[\<registrazione messaggi >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|Descrive le impostazioni per la registrazione dei messaggi WCF.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|serviceModel|Elemento radice di tutti gli elementi di configurazione WCF.|  
  
## <a name="remarks"></a>Note  
 La sezione `diagnostics` definisce le impostazioni dei diagnostica per tutti i servizi trovati in un assembly. Non è possibile definire impostazioni diagnostiche separate a livello di servizio a meno che l'assembly non comprenda solo uno servizio. Gli attributi sono impostati secondo i requisiti della sezione.  
  
## <a name="example"></a>Esempio  
  
```xml  
<diagnostics wmiProviderEnabled="false"  
       performanceCounters="all">  
       <messageLogging logEntireMessage="true"  
          logMalformedMessages="true"  
          logMessagesAtServiceLevel="true"  
          logMessagesAtTransportLevel="true"  
          maxMessagesToLog="42"  
          maxSizeOfMessageToLog="42">  
         <filters>  
         <clear />  
    </filters>  
       </messageLogging>  
</diagnostics>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>
