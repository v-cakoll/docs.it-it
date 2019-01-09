---
title: '&lt;add&gt; di &lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: fe9ce8bc2a0efb9e20800189cd9f948d5e6a2232
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150747"
---
# <a name="ltaddgt-of-ltfiltersgt"></a>&lt;add&gt; di &lt;filters&gt;
Filtro XPath che specifica il tipo di messaggio da registrare.  
  
 \<system.ServiceModel>  
\<diagnostica >  
\<messageLogging >  
\<i filtri >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|filtro|Stringa che specifica una query su un documento XML definito da un'espressione di XPath 1.0. Per altre informazioni, vedere <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<i filtri >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|Contiene una raccolta di filtri di XPath usati per controllare il tipo di messaggio registrato.|  
  
## <a name="remarks"></a>Note  
 I filtri vengono applicati solo al livello di trasporto, specificato da `logMessagesAtTransportLevel` impostato `true`. I filtri non influiscono sulla registrazione dei messaggi a livello di servizio e in formato non valido.  
  
 Per aggiungere un filtro alla raccolta, usare la parola chiave `add`. Quando sono definiti uno o più filtri, solo i messaggi che corrispondono almeno a uno dei filtri vengono registrati. Se non è definito alcun filtro, passeranno tutti i messaggi.  
  
 I filtri supportano la sintassi Xpath completa e sono applicati nell'ordine in cui vengono visualizzati nel file di configurazione. Un filtro sintatticamente errato determina un'eccezione di configurazione.  
  
 Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare un filtro che registra solo messaggi con una sezione intestazione SOAP.  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [Configurazione della registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [Configurazione della registrazione dei messaggi](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [\<messageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
