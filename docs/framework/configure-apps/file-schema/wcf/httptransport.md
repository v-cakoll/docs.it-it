---
title: '&lt;httpTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 50cbf6521870a54f4f87c3eeb12030d5d7f2f6bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="lthttptransportgt"></a>&lt;httpTransport&gt;
Specifica un trasporto HTTP per la trasmissione di messaggi SOAP per un'associazione personalizzata.  
  
 \<System. ServiceModel >  
\<associazioni >  
\<customBinding >  
\<associazione >  
\<httpTransport >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpTransport  
    allowCookies=Boolean"  
    authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"  
    bypassProxyOnLocal=Boolean"  
    hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
    keepAliveEnabled="Boolean"  
    maxBufferSize="Integer"  
    proxyAddress="Uri"  
    proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"  
IntegratedWindowsAuthentication: Specifies Windows authentication"  
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
|authenticationScheme|Specifica il protocollo usato per autenticare le richieste del client elaborate da un listener HTTP. Di seguito vengono elencati i valori validi:<br /><br /> -Digest: Specifica l'autenticazione del digest.<br />-Negotiate: Negozia con il client per determinare lo schema di autenticazione. Viene usato se il client e il server supportano entrambi Kerberos; in caso contrario, viene usato NTLM.<br />-Ntlm: Specifica l'autenticazione NTLM.<br />-Basic: Specifica l'autenticazione di base.<br />-Anonymous: Specifica l'autenticazione anonima.<br /><br /> Il valore predefinito è Anonymous. L'attributo è di tipo <xref:System.Net.AuthenticationSchemes>. Questo attributo può essere impostato solo una volta.|  
|bypassProxyOnLocal|Valore booleano che indica se ignorare il server proxy per indirizzi locali. Il valore predefinito è `false`.<br /><br /> Un indirizzo locale corrisponde a un indirizzo che si trova nella rete LAN o nell'Intranet locale.<br /><br /> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ignora sempre il proxy se l'indirizzo del servizio inizia con http://localhost.<br /><br /> È necessario usare il nome host invece di localhost se si desidera che i client passino da un proxy quando comunicano con servizi nello stesso computer.|  
|hostnameComparisonMode|Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI. I valori validi sono:<br /><br /> -StrongWildcard: ("+") corrisponde tutti i possibili nomi host nel contesto dello schema specificato, porta e relativo URI.<br />-Esatte: nessun carattere jolly<br />-WeakWildcard: ("*") corrisponde a qualsiasi nome host possibile nel contesto dello schema specificato, porta e relativo UIR che non sono stati associati in modo esplicito o tramite il meccanismo sicuro dei caratteri jolly.<br /><br /> L'impostazione predefinita è StrongWildcard. L'attributo è di tipo `System.ServiceModel.HostnameComparisonMode`.|  
|keepAliveEnabled|Valore booleano che specifica se eseguire una connessione permanente alla risorsa Internet.|  
|maxBufferSize|Numero intero positivo che specifica la dimensione massima del buffer. L'impostazione predefinita è 524288.|  
|proxyAddress|URI che specifica l'indirizzo del proxy HTTP. Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`. Il valore predefinito è `null`.|  
|proxyAuthenticationScheme|Specifica il protocollo usato per l'autenticazione delle richieste client elaborate da un proxy HTTP. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna autenticazione viene eseguita.<br />-Digest: Specifica l'autenticazione del digest.<br />-Negotiate: Negozia con il client per determinare lo schema di autenticazione. Viene usato se il client e il server supportano entrambi Kerberos; in caso contrario, viene usato NTLM.<br />-Ntlm: Specifica l'autenticazione NTLM.<br />-Basic: Specifica l'autenticazione di base.<br />-Anonymous: Specifica l'autenticazione anonima.<br />-IntegratedWindowsAuthentication: Specifica l'autenticazione di Windows.<br /><br /> Il valore predefinito è Anonymous. L'attributo è di tipo <xref:System.Net.AuthenticationSchemes>.|  
|realm|Stringa che specifica l'area di autenticazione da usare sul proxy/server. Il valore predefinito è una stringa vuota.<br /><br /> I server usano aree di autenticazione per separare risorse protette. Ogni partizione può avere schema di autenticazione e/o database di autorizzazione propri. Le aree vengono usate solo per l'autenticazione di base e classificata. Se un client viene autenticato correttamente, l'autenticazione è valida per tutte le risorse in una determinata area. Per una descrizione dettagliata delle aree, vedere RFC 2617 all'indirizzo http://www.ietf.org.|  
|transferMode|Specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso in una richiesta o una risposta. Di seguito vengono elencati i valori validi:<br /><br /> -Memorizzati nel buffer: Vengono memorizzati nel buffer i messaggi di richiesta e risposta.<br />-Streaming: Messaggi di richiesta e risposta sono state trasmesse.<br />-StreamedRequest: Viene trasmesso il messaggio di richiesta e il messaggio di risposta viene memorizzato nel buffer.<br />-StreamedResponse: La richiesta viene memorizzato nel buffer e viene trasmesso il messaggio di risposta.<br /><br /> L'impostazione predefinita è Buffered. L'attributo è di tipo <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Valore che specifica se nel server viene attivata la condivisione di connessioni non sicure. Il valore predefinito è `false`. Se abilitata, l'autenticazione NTLM viene eseguita una volta su ogni connessione TCP.|  
|useDefaultWebProxy|Valore booleano che specifica se vengono usate le impostazioni proxy a livello di computer anziché le impostazioni utente specifiche. Il valore predefinito è `true`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<associazione >](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 L'elemento `httpTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto HTTP. Quest'ultimo è il principale trasporto usato per scopi di interoperabilità. Questo trasporto è supportato da [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] per assicurare l'interoperabilità con altri stack di servizi Web diversi da [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.HttpTransportElement>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
