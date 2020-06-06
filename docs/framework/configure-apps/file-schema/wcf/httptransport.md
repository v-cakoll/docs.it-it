---
title: <httpTransport>
ms.date: 03/30/2017
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
ms.openlocfilehash: b3558db6018d79f0fad27ff28657bfadb5637467
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736773"
---
# \<httpTransport>
Specifica un trasporto HTTP per la trasmissione di messaggi SOAP per un'associazione personalizzata.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpTransport>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpTransport allowCookies="Boolean"
               authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
               bypassProxyOnLocal="Boolean"
               hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
               keepAliveEnabled="Boolean"
               maxBufferSize="Integer"
               proxyAddress="Uri"
               proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"
               realm="String"
               transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
               unsafeConnectionNtlmAuthentication="Boolean"
               useDefaultWebProxy="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|allowCookies|Valore booleano che specifica se il client accetta cookie e li propaga alle richieste future. Il valore predefinito è `false`.<br /><br /> È possibile usare questo attributo quando si interagisce con servizi Web ASMX che usano cookie. In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.|  
|authenticationScheme|Specifica il protocollo usato per autenticare le richieste del client elaborate da un listener HTTP. I valori validi sono i seguenti:<br /><br /> -Digest: specifica l'autenticazione del digest.<br />-Negotiate: negozia con il client per determinare lo schema di autenticazione. Viene usato se il client e il server supportano entrambi Kerberos; in caso contrario, viene usato NTLM.<br />-NTLM: specifica l'autenticazione NTLM.<br />-Basic: specifica l'autenticazione di base.<br />-Anonymous: specifica l'autenticazione anonima.<br /><br /> Il valore predefinito è Anonymous. L'attributo è di tipo <xref:System.Net.AuthenticationSchemes>. Questo attributo può essere impostato solo una volta.|  
|bypassProxyOnLocal|Valore booleano che indica se ignorare il server proxy per indirizzi locali. Il valore predefinito è `false`.<br /><br /> Un indirizzo locale corrisponde a un indirizzo che si trova nella rete LAN o nell'Intranet locale.<br /><br /> Windows Communication Foundation (WCF) ignora sempre il proxy se l'indirizzo del servizio inizia con `http://localhost` .<br /><br /> È necessario usare il nome host invece di localhost se si desidera che i client passino da un proxy quando comunicano con servizi nello stesso computer.|  
|hostnameComparisonMode|Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI. I valori validi sono:<br /><br /> -StrongWildcard: ("+") corrisponde a tutti i nomi host possibili nel contesto dello schema, della porta e dell'URI relativo specificati.<br />-Exact: nessun carattere jolly<br />-WeakWildcard: (" \* ") corrisponde a tutti i nomi host possibili nel contesto dello schema specificato, della porta e del UIR relativo che non sono stati confrontati in modo esplicito o tramite il meccanismo con carattere jolly complesso.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>. Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>.|  
|keepAliveEnabled|Valore booleano che specifica se eseguire una connessione permanente alla risorsa Internet.|  
|maxBufferSize|Numero intero positivo che specifica la dimensione massima del buffer. L'impostazione predefinita è 524288.|  
|proxyAddress|URI che specifica l'indirizzo del proxy HTTP. Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`. Il valore predefinito è `null`.|  
|proxyAuthenticationScheme|Specifica il protocollo usato per l'autenticazione delle richieste client elaborate da un proxy HTTP. I valori validi sono i seguenti:<br /><br /> -None: non viene eseguita alcuna autenticazione.<br />-Digest: specifica l'autenticazione del digest.<br />-Negotiate: negozia con il client per determinare lo schema di autenticazione. Viene usato se il client e il server supportano entrambi Kerberos; in caso contrario, viene usato NTLM.<br />-NTLM: specifica l'autenticazione NTLM.<br />-Basic: specifica l'autenticazione di base.<br />-Anonymous: specifica l'autenticazione anonima.<br /><br /> Il valore predefinito è Anonymous. L'attributo è di tipo <xref:System.Net.AuthenticationSchemes>. Si noti che <xref:System.Net.AuthenticationSchemes.IntegratedWindowsAuthentication?displayProperty=nameWithType> non è supportato.|  
|realm|Stringa che specifica l'area di autenticazione da usare sul proxy/server. Il valore predefinito è una stringa vuota.<br /><br /> I server usano aree di autenticazione per separare risorse protette. Ogni partizione può avere schema di autenticazione e/o database di autorizzazione propri. Le aree vengono usate solo per l'autenticazione di base e classificata. Se un client viene autenticato correttamente, l'autenticazione è valida per tutte le risorse in una determinata area. Per una descrizione dettagliata delle aree di autenticazione, vedere RFC 2617 sul [sito Web IETF](https://www.ietf.org).|  
|transferMode|Specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso in una richiesta o una risposta. I valori validi sono i seguenti:<br /><br /> -Buffered: i messaggi di richiesta e risposta vengono memorizzati nel buffer.<br />-Streamed: i messaggi di richiesta e risposta vengono trasmessi.<br />-StreamedRequest: il messaggio di richiesta viene trasmesso e il messaggio di risposta viene memorizzato nel buffer.<br />-StreamedResponse: il messaggio di richiesta viene memorizzato nel buffer e il messaggio di risposta viene trasmesso.<br /><br /> L'impostazione predefinita è Buffered. L'attributo è di tipo <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Valore che specifica se nel server viene attivata la condivisione di connessioni non sicure. Il valore predefinito è `false`. Se abilitata, l'autenticazione NTLM viene eseguita una volta su ogni connessione TCP.|  
|useDefaultWebProxy|Valore booleano che specifica se vengono usate le impostazioni proxy a livello di computer anziché le impostazioni utente specifiche. Il valore predefinito è `true`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Commenti  
 L'elemento `httpTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto HTTP. Quest'ultimo è il principale trasporto usato per scopi di interoperabilità. Questo trasporto è supportato dal Windows Communication Foundation (WCF) per garantire l'interoperabilità con altri stack di servizi Web non WCF.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.HttpTransportElement>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Trasporti](../../../wcf/feature-details/transports.md)
- [Scelta di un trasporto](../../../wcf/feature-details/choosing-a-transport.md)
- [Binding](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
