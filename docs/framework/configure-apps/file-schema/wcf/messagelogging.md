---
title: '&lt;registrazione messaggi&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5b232e3faf1e0e8976b0c08264c8ba03988902a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagelogginggt"></a>&lt;registrazione messaggi&gt;
Questo elemento definisce le impostazioni per le funzionalità di registrazione dei messaggi di Windows Communication Foundation (WCF).  
  
 \<System. ServiceModel >  
\<diagnostica >  
\<registrazione messaggi >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
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
|`logEntireMessage`|Valore che specifica se l'intero messaggio (intestazione e corpo del messaggio) viene registrato. Il valore predefinito è `false` ovvero solo l'intestazione del messaggio viene registrata. Questa impostazione influisce su tutti i livelli di registrazione dei messaggi (servizio, trasporto e formato non valido).|  
|`logMalformedMessages`|Valore che specifica se i messaggi in formato non valido vengono registrati. I messaggi in formato non valido non vengono conteggiati per `maxMessagesToLog`. Il valore predefinito è `false`.|  
|`logMessagesAtServiceLevel`|Valore che specifica se i messaggi vengono tracciati al livello del servizio (prima delle trasformazioni relative a crittografia e trasporto). Il valore predefinito è `false`.|  
|`logMessagesAtTransportLevel`|Valore che specifica se i messaggi vengono tracciati al livello del trasporto. Tutti i filtri specificati nel file config vengono applicati e solo i messaggi che corrispondono ai filtri vengono tracciati. Il valore predefinito è `false`.|  
|`maxMessagesToLog`|Valore che specifica il numero massimo di messaggi da registrare. Il valore predefinito è 1000.|  
|`maxSizeOfMessageToLog`|Valore che specifica la dimensione massima, in byte, di un messaggio da registrare. I messaggi di dimensioni maggiori del limite non vengono registrati. Questa impostazione influisce su tutti i livelli di traccia. L'impostazione predefinita è 262144(0x4000).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|filtri|L'elemento `filters` contiene una raccolta dei filtri di XPath. Se la registrazione dei messaggi di trasporto è attivata (`logMessagesAtTransportLevel` è `true`), verranno registrati solo i messaggi corrispondenti ai filtri.<br /><br /> I filtri vengono applicati solo a livello di trasporto. I filtri non influiscono sulla registrazione dei messaggi a livello di servizio e in formato non valido.<br /><br /> L'unico attributo di questo elemento, `filter`, è un XpathFilter.<br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|diagnostica|Definisce le impostazioni WCF per l'ispezione e il controllo in fase di esecuzione da parte dell'amministratore.|  
  
## <a name="remarks"></a>Note  
 I messaggi vengono registrati a tre livelli diversi nello stack: servizio, trasportare e formato non valido. Ciascun livello può essere attivato separatamente.  
  
 È possibile aggiungere filtri XPath per registrare messaggi specifici a livello di trasporto e di servizio. Se non viene definito nessun filtro, tutti i messaggi vengono registrati. I filtri vengono applicati solo alle intestazioni del messaggio. Il corpo viene ignorato. WCF ignora il corpo del messaggio per migliorare le prestazioni. Se si desidera applicare un filtro in base al contenuto del corpo del messaggio, è possibile creare un listener personalizzato con un filtro appropriato.  
  
 Per attivare la traccia dei messaggi è necessario creare un listener di traccia. Il listener stesso può essere un qualsiasi listener che funziona con l'architettura di traccia di <xref:System.Diagnostics>. Nell'esempio seguente viene illustrato come creare un listener di questo tipo.  
  
```xml  
<system.diagnostics>  
    <sources>  
          <source name="System.ServiceModel" switchValue="Verbose">  
              <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="ServiceModel Listener" traceOutputOptions="None" />  
               </listeners>  
        </source>  
            <source name="System.ServiceModel.MessageLogging">  
                <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="MessageLogging Listener" traceOutputOptions="None"/>  
               </listeners>  
        </source>  
    </sources>  
     <sharedListeners>  
            <add initializeData="C:\ItProTools\TraceLog.xml"  
                    type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
                    name="ServiceModel Listener"  
                    traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />  
            <add initializeData="C:\ItProTools\MessageLog.log"  
                    type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
                   name="MessageLogging Listener"  
                   traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />  
    </sharedListeners>  
</system.diagnostics>  
```  
  
## <a name="example"></a>Esempio  
  
```xml  
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
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 [Configurazione di registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
