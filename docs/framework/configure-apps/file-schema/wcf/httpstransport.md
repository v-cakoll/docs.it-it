---
title: <httpsTransport>
ms.date: 03/30/2017
ms.assetid: f6ed4bc0-7e38-4348-9259-30bf61eb9435
ms.openlocfilehash: b70236e8bba93a49ca5b53538333fa63283a5f0a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928529"
---
# <a name="httpstransport"></a>\<httpsTransport>
Specifica un trasporto HTTP per la trasmissione di messaggi SOAP per un'associazione personalizzata.  
  
 \<system.serviceModel>  
\<Binding >  
\<customBinding>  
\<binding>  
\<httpsTransport>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpsTransport allowCookies="Boolean"
                authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
                bypassProxyOnLocal="Boolean"
                hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                manualAddressing="Boolean"
                maxBufferPoolSize="Integer"
                maxBufferSize="Integer"
                maxReceivedMessageSize="Integer"
                proxyAddress="Uri"
                proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"
                realm="String"
                requireClientCertificate="Boolean"
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
|authenticationScheme|Specifica il protocollo usato per autenticare le richieste del client elaborate da un listener HTTP. Di seguito vengono elencati i valori validi:<br /><br /> Digest Specifica l'autenticazione digest.<br />Negoziare Negozia con il client per determinare lo schema di autenticazione. Viene usato se il client e il server supportano entrambi Kerberos; in caso contrario, viene usato NTLM.<br />NTLM Specifica l'autenticazione NTLM.<br />Basic Specifica l'autenticazione di base.<br />Anonimo Consente di specificare l'autenticazione anonima.<br /><br /> Il valore predefinito è Anonymous. L'attributo è di tipo <xref:System.Net.AuthenticationSchemes>. Questo attributo può essere impostato solo una volta.|  
|bypassProxyOnLocal|Valore booleano che indica se ignorare il server proxy per indirizzi locali. Il valore predefinito è `false`.<br /><br /> Un indirizzo locale corrisponde a un indirizzo che si trova nella rete LAN o nell'Intranet locale.<br /><br /> Windows Communication Foundation (WCF) ignora sempre il proxy se l'indirizzo del servizio inizia con `http://localhost`.<br /><br /> È necessario usare il nome host invece di localhost se si desidera che i client passino da un proxy quando comunicano con servizi nello stesso computer.|  
|hostnameComparisonMode|Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI. I valori validi sono:<br /><br /> -StrongWildcard: ("+") corrisponde a tutti i nomi host possibili nel contesto dello schema, della porta e dell'URI relativo specificati.<br />-Exact: nessun carattere jolly<br />-WeakWildcard: ("\*") corrisponde a tutti i nomi host possibili nel contesto dello schema specificato, della porta e del UIR relativo che non sono stati confrontati in modo esplicito o tramite il meccanismo con carattere jolly complesso.<br /><br /> L'impostazione predefinita è StrongWildcard. L'attributo è di tipo `System.ServiceModel.HostnameComparison`.|  
|manualAddressing|Valore booleano che consente all'utente di assumere il controllo dell'indirizzamento dei messaggi. Questa proprietà viene usata in genere in scenari di router, in cui è l'applicazione a determinare a quale delle tante destinazioni inviare un messaggio.<br /><br /> Quando è impostato su `true`, il canale presuppone che il messaggio sia già stato indirizzato e non aggiunge ulteriori informazioni. L'utente può indirizzare quindi individualmente ogni messaggio.<br /><br /> Quando è impostato su `false`, il meccanismo di indirizzamento predefinito di Windows Communication Foundation (WCF) crea automaticamente indirizzi per tutti i messaggi.<br /><br /> Il valore predefinito è `false`.|  
|maxBufferPoolSize|Numero intero positivo che specifica la dimensione massima del pool di buffer. Il valore predefinito è 524288.<br /><br /> Molte parti di WCF usano buffer. La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer. Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool. In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.|  
|maxBufferSize|Numero intero positivo che specifica la dimensione massima del buffer. L'impostazione predefinita è 524288.|  
|maxReceivedMessageSize|Numero intero positivo che specifica la dimensione massima consentita del messaggio che può essere ricevuto. Il valore predefinito è 65536.|  
|proxyAddress|URI che specifica l'indirizzo del proxy HTTP. Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`. Il valore predefinito è `null`.|  
|proxyAuthenticationScheme|Specifica il protocollo usato per l'autenticazione delle richieste client elaborate da un proxy HTTP. Di seguito vengono elencati i valori validi:<br /><br /> Nessuno Non viene eseguita alcuna autenticazione.<br />Digest Specifica l'autenticazione digest.<br />Negoziare Negozia con il client per determinare lo schema di autenticazione. Viene usato se il client e il server supportano entrambi Kerberos; in caso contrario, viene usato NTLM.<br />NTLM Specifica l'autenticazione NTLM.<br />Basic Specifica l'autenticazione di base.<br />Anonimo Consente di specificare l'autenticazione anonima.<br /><br /> Il valore predefinito è Anonymous. L'attributo è di tipo <xref:System.Net.AuthenticationSchemes>. Si noti <xref:System.Net.AuthenticationSchemes.IntegratedWindowsAuthentication?displayProperty=nameWithType> che non è supportato.|  
|realm|Stringa che specifica l'area di autenticazione da usare sul proxy/server. Il valore predefinito è una stringa vuota.<br /><br /> I server usano aree di autenticazione per separare risorse protette. Ogni partizione può avere schema di autenticazione e/o database di autorizzazione propri. Le aree vengono usate solo per l'autenticazione di base e classificata. Se un client viene autenticato correttamente, l'autenticazione è valida per tutte le risorse in una determinata area. Per una descrizione dettagliata delle aree di autenticazione, vedere RFC 2617 sul [sito Web IETF](https://www.ietf.org).|  
|requireClientCertificate|Valore booleano che specifica se il server richiede al client di fornire un certificato client come parte dell'handshake HTTPS. Il valore predefinito è `false`.|  
|transferMode|Specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso in una richiesta o una risposta. Di seguito vengono elencati i valori validi:<br /><br /> Tamponata I messaggi di richiesta e risposta vengono memorizzati nel buffer.<br />Trasmessi I messaggi di richiesta e risposta vengono trasmessi.<br />StreamedRequest Il messaggio di richiesta viene inviato nel flusso e quello di risposta viene memorizzato nel buffer.<br />StreamedResponse Il messaggio di richiesta viene memorizzato nel buffer e quello di risposta viene inviato nel flusso.<br /><br /> L'impostazione predefinita è Buffered. L'attributo è di tipo <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Valore che specifica se nel server viene attivata la condivisione di connessioni non sicure. Il valore predefinito è `false`. Se abilitata, l'autenticazione NTLM viene eseguita una volta su ogni connessione TCP.|  
|useDefaultWebProxy|Valore booleano che specifica se vengono usate le impostazioni proxy a livello di computer anziché le impostazioni utente specifiche. Il valore predefinito è `true`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<binding>](../../../misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 L'elemento `httpsTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto HTTPS. HTTPS è il trasporto primario usato a fini di interoperabilità protetta. HTTPS è supportato dal Windows Communication Foundation (WCF) per garantire l'interoperabilità con altri stack di servizi Web.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.HttpsTransportElement>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Trasporti](../../../wcf/feature-details/transports.md)
- [Scelta di un trasporto](../../../wcf/feature-details/choosing-a-transport.md)
- [Associazioni](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
