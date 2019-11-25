---
title: <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 84179d77-825d-44b9-895a-ab08e7aa044d
ms.openlocfilehash: 0bb6d1f40fe38cb13ed8ab07957de5db22d48fcc
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140497"
---
# <a name="webhttpbinding"></a>\<webHttpBinding>
Defines a binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webHttpBinding>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<webHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxBufferSize="integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
           useDefaultWebProxy="Boolean"
           writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding">
    <security mode="None/Transport/TransportCredentialOnly">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</webHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|allowCookies|Valore booleano che indica se il client accetta cookie e li propaga alle richieste future. Il valore predefinito è false.<br /><br /> È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie. In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.|  
|bypassProxyOnLocal|Valore booleano che indica se ignorare il server proxy per indirizzi locali. Il valore predefinito è `false`.|  
|closeTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|hostnameComparisonMode|Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI. L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI. Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.|  
|maxBufferPoolSize|Numero intero che specifica la dimensione del pool di buffer massima per questa associazione. Il valore predefinito è 524.288 byte (512 * 1024). Molte parti di Windows Communication Foundation (WCF) usano buffer. La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer. Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool. In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.|  
|maxBufferSize|Numero intero che specifica la quantità massima di memoria allocata al gestore dei buffer dei messaggi che riceve i messaggi dal canale. Il valore predefinito è 524,288 (0x80000) byte.|  
|maxReceivedMessageSize|Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione. Il mittente di un messaggio che supera questo limite riceverà un errore. Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia. Il valore predefinito è 65536. **Note:**  Increasing this value alone is not sufficient in ASP.NET compatible mode. You should also increase the value of `httpRuntime` (see [httpRuntime Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e1f13641(v=vs.100))).|  
|name|Stringa che contiene il nome della configurazione dell'associazione. Questo valore deve essere univoco perché viene usato per identificare l'associazione. Starting with .NET Framework 4, bindings and behaviors are not required to have a name. For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|proxyAddress|URI che specifica l'indirizzo del proxy HTTP. Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`. Il valore predefinito è `null`.|  
|receiveTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|sendTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|transferMode.|Valore <xref:System.ServiceModel.TransferMode> valido che indica se il servizio configurato con l'associazione usa modalità di trasferimento messaggi nel flusso o memorizzati nel buffer (o entrambe). Il valore predefinito è `Buffered`.|  
|useDefaultWebProxy|Valore booleano che specifica se viene usato il proxy HTTP di sistema configurato automaticamente. Il valore predefinito è `true`.|  
|writeEncoding|Specifica la codifica dei caratteri usata per il testo dei messaggi. Di seguito vengono elencati i valori validi:<br /><br /> UnicodeFffeTextEncoding: codifica Unicode BigEndian.<br /><br /> Utf16TextEncoding: codifica a 16 bit.<br /><br /> Utf8TextEncoding: codifica a 8 bit.<br /><br /> L'impostazione predefinita è Utf8TextEncoding.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definisce i vincoli sulla complessità dei messaggi POX che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<security>](security-of-webhttpbinding.md)|Definisce le impostazioni di sicurezza per l'associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.WebHttpSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Questo elemento contiene una raccolta di associazioni standard e personalizzate.|  
  
## <a name="remarks"></a>Note  
 The WCF Web Programming Model allows developers to expose WCF Web services through HTTP requests that use "plain old XML" (POX) style messaging instead of SOAP-based messaging. For clients to communicate with a service using HTTP requests, an endpoint of the service must be configured with the [\<webHttpBinding>](webhttpbinding.md) that has the \<WebHttpBehavior> attached to it.  
  
 Support in WCF for syndication and ASP.AJAX integration are both built on top of the Web Programming Model. For more information on the model, see [WCF Web HTTP Programming Model](../../../wcf/feature-details/wcf-web-http-programming-model.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- [Modello di programmazione HTTP Web di WCF](../../../wcf/feature-details/wcf-web-http-programming-model.md)
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
