---
title: WSTrustChannelFactory e WSTrustChannel
ms.date: 03/30/2017
ms.assetid: 96cec467-e963-4132-b18b-7d0b3a2e979f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 78bf58b6d1b9059d2513b9f81eb382487bb4004b
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998466"
---
# <a name="wstrustchannelfactory-and-wstrustchannel"></a>WSTrustChannelFactory e WSTrustChannel
Se si ha già familiarità con Windows Communication Foundation (WCF), si sa che un client WCF supporta già la federazione. Configurando un client WCF con <xref:System.ServiceModel.WSFederationHttpBinding> o un binding personalizzato simile, è possibile abilitare l'autenticazione federata in un servizio.  
  
 WCF ottiene il token rilasciato dal servizio token di sicurezza in background e lo usa per l'autenticazione nel servizio. La limitazione principale a questo approccio è l'assenza di visibilità nelle comunicazioni del client con il server. WCF genera automaticamente il token di sicurezza delle richieste per il servizio token di sicurezza in base ai parametri del token rilasciato nel binding. Il client non può quindi variare i parametri del token di sicurezza delle richieste per una singola richiesta, esaminare la risposta del token di sicurezza delle richieste per ottenere informazioni come le attestazioni di visualizzazione o memorizzare nella cache il token per l'uso futuro.  
  
 Il client WCF è attualmente adatto per scenari di federazione di base. Uno degli scenari principali supportati da Windows Identity Foundation (WIF) richiede tuttavia il controllo sul token di sicurezza delle richieste a un livello non facilmente consentito da WCF. WIF aggiunge quindi funzionalità che offrono un maggiore controllo sulla comunicazione con il servizio token di sicurezza.  
  
 WIF supporta gli scenari di federazione seguenti:  
  
-   Uso di un client WCF senza dipendenze WIF per l'autenticazione in un servizio federato  
  
-   Possibilità per WIF in un client WCF di inserire un elemento ActAs o OnBehalfOf nel token di sicurezza delle richieste per il servizio token di sicurezza  
  
-   Uso solo di WIF per ottenere un token dal servizio token di sicurezza e quindi consentire a un client WCF di eseguire l'autenticazione con questo token. Per altre informazioni, vedere l'esempio [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406).  
  
 Il primo scenario è ovvio: i client WCF esistenti continueranno a usare i servizi token di sicurezza e le relying party WIF. Questo argomento illustra i due scenari rimanenti.  
  
## <a name="enhancing-an-existing-wcf-client-with-actas--onbehalfof"></a>Miglioramento di un client WCF esistente con ActAs/OnBehalfOf  
 In uno scenario di delega di identità tipico, un client chiama un servizio di livello intermedio, che chiama quindi un servizio back-end. Il servizio di livello intermedio funge da client o agisce per conto del client.  
  
> [!TIP]
>  Qual è la differenza tra ActAs e OnBehalfOf?  
>   
>  Dal punto di vista protocollo WS-Trust:  
>   
> 1. Un elemento token di sicurezza delle richieste ActAs indica che il richiedente vuole un token che include attestazioni relative a due entità distinte, ovvero il richiedente e un'entità esterna rappresentata dal token nell'elemento ActAs.  
> 2. Un elemento token di sicurezza delle richieste OnBehalfOf indica che il richiedente vuole un token che include attestazioni relative a una sola entità, ovvero l'entità esterna rappresentata dal token nell'elemento OnBehalfOf.  
>   
>  La funzionalità ActAs viene usata in genere in scenari che richiedono la delega composita, dove il destinatario finale del token rilasciato può controllare l'intera catena di delega e vedere non solo il client, ma tutti gli intermediari. Ciò consente di eseguire il controllo di accesso, le attività di controllo e altre attività correlate basate sull'intera catena di delega di identità. La funzionalità ActAs viene in genere usata in sistemi multilivello per autenticare e passare informazioni sulle identità tra i livelli, senza dover passare tali informazioni a livello di applicazione/logica di business.  
>   
>  La funzionalità OnBehalfOf viene usata negli scenari in cui è importante solo l'identità del client originale ed è in effetti uguale alla funzionalità di rappresentazione dell'identità disponibile in Windows. Quando viene usata la funzionalità OnBehalfOf, il destinatario finale del token rilasciato può visualizzare solo le attestazioni relative al client originale e le informazioni relative agli intermediari non vengono mantenute. Un modello comune in cui viene usata la funzionalità OnBehalfOf è il modello basato su proxy, nel quale il client non può accedere direttamente al servizio token di sicurezza, ma comunica invece tramite un gateway proxy. Il gateway proxy autentica il chiamante e inserisce le informazioni sul chiamante nell'elemento OnBehalfOf del messaggio del token di sicurezza delle richieste, che viene quindi inviato al vero servizio token di sicurezza per l'elaborazione. Il token risultante contiene solo attestazioni correlate al client del proxy, rendendo completamente trasparente il proxy al destinatario del token rilasciato. Si noti che WIF non supporta \<wsse:SecurityTokenReference> o \<wsa:EndpointReferences> come elemento figlio di \<wst:OnBehalfOf>. La specifica WS-Trust offre tre modi per identificare il richiedente originale, per conto del quale opera il proxy. Questi sono:  
>   
>  -   Riferimento al token di sicurezza. Un riferimento a un token, all'interno del messaggio o eventualmente recuperato fuori banda.  
> -   Riferimento all'endpoint. Usato come chiave per la ricerca dei dati, anche in questo caso fuori banda.  
> -   Token di sicurezza. Identifica direttamente il richiedente originale.  
>   
>  WIF supporta solo i token di sicurezza, crittografati o non crittografati, come elemento figlio diretto di \<wst:OnBehalfOf>.  
  
 Queste informazioni vengono trasmesse a un'autorità di certificazione WS-Trust mediante gli elementi token ActAs e OnBehalfOf nel token di sicurezza delle richieste.  
  
 WCF espone un punto di estendibilità nel binding che consente di aggiungere elementi XML arbitrari al token di sicurezza delle richieste. Tuttavia, poiché il punto di estendibilità è collegato al binding, negli scenari in cui il contenuto del token di sicurezza delle richieste deve variare per ogni chiamata, è necessario ricreare il client per ogni chiamata, con un conseguente peggioramento delle prestazioni. WIF usa metodi di estensione nella classe `ChannelFactory` per consentire agli sviluppatori di allegare i token ottenuti fuori banda al token di sicurezza delle richieste. L'esempio di codice seguente illustra come accettare un token che rappresenta il client, ad esempio un token X.509, un nome utente o un token SAML (Security Assertion Markup Language), e allegarlo al token di sicurezza delle richieste inviato all'autorità di certificazione.  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelActingAs<IHelloService>( clientSamlToken );  
serviceChannel.Hello("Hi!");  
```  
  
 WIF offre i vantaggi seguenti:  
  
-   Il token di sicurezza delle richieste può essere modificato per ogni canale, quindi i servizi di livello intermedio non devono ricreare la factory canale per ogni client e ciò consente un miglioramento delle prestazioni.  
  
-   Funziona con i client WCF esistenti, rendendo possibile un facile percorso di aggiornamento per i servizi di livello intermedio WCF esistenti che vogliono abilitare la semantica di delega delle identità.  
  
 Anche in questo caso non c'è tuttavia visibilità nella comunicazione del client con il servizio token di sicurezza. Questo aspetto verrà esaminato nel terzo scenario.  
  
## <a name="communicating-directly-with-an-issuer-and-using-the-issued-token-to-authenticate"></a>Comunicazione diretta con un autorità di certificazione e uso del token rilasciato per l'autenticazione  
 Per alcuni scenari avanzati, il miglioramento di un client WCF non è sufficiente. Gli sviluppatori che usano solo WCF usano in genere contratti Message In/Message Out e gestiscono manualmente l'analisi lato client della risposta dell'autorità di certificazione.  
  
 WIF introduce le classi <xref:System.ServiceModel.Security.WSTrustChannelFactory> e <xref:System.ServiceModel.Security.WSTrustChannel> per consentire al client di comunicare direttamente con un'autorità di certificazione WS-Trust. Le classi <xref:System.ServiceModel.Security.WSTrustChannelFactory> e <xref:System.ServiceModel.Security.WSTrustChannel> consentono il flusso di oggetti token di sicurezza delle richieste e risposta del token di sicurezza delle richieste fortemente tipizzati tra il client e l'autorità di certificazione, come illustrato nell'esempio di codice seguente.  
  
```  
WSTrustChannelFactory trustChannelFactory = new WSTrustChannelFactory( stsBinding, stsAddress );  
WSTrustChannel channel = (WSTrustChannel) trustChannelFactory.CreateChannel();  
RequestSecurityToken rst = new RequestSecurityToken(RequestTypes.Issue);  
rst.AppliesTo = new EndpointAddress(serviceAddress);  
RequestSecurityTokenResponse rstr = null;  
SecurityToken token = channel.Issue(rst, out rstr);  
```  
  
 Si noti che il parametro `out` nel metodo <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> consente l'accesso alla risposta del token di sicurezza delle richieste per l'analisi sul lato client.  
  
 Fino a questo momento è stato illustrato come ottenere un token. Il token restituito dall'oggetto <xref:System.ServiceModel.Security.WSTrustChannel> è un oggetto `GenericXmlSecurityToken` che contiene tutte le informazioni necessarie per l'autenticazione in una relying party. L'esempio di codice seguente illustra come usare questo token.  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelWithIssuedToken<IHelloService>( token ); serviceChannel.Hello("Hi!");  
```  
  
 Il metodo di estensione <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> nell'oggetto `ChannelFactory` indica a WIF che è stato ottenuto un token fuori banda e che deve interrompere la normale chiamata WCF all'autorità di certificazione e usare invece il token ottenuto per autenticare la relying party. Questo metodo offre i vantaggi seguenti:  
  
-   Consente il controllo completo sul processo di rilascio del token.  
  
-   Supporta scenari ActAs/OnBehalfOf impostando direttamente queste proprietà sul token di sicurezza delle richieste in uscita.  
  
-   Consente di prendere decisioni dinamiche sull'attendibilità sul lato client in base al contenuto della risposta del token di sicurezza delle richieste.  
  
-   Consente di memorizzare nella cache e riutilizzare il token restituito dal metodo <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A>.  
  
-   <xref:System.ServiceModel.Security.WSTrustChannelFactory> e <xref:System.ServiceModel.Security.WSTrustChannel> consentono il controllo della semantica relativa a recupero, errori e memorizzazione nella cache del canale in base alle procedure consigliate per WCF.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzionalità di WIF](../../../docs/framework/security/wif-features.md)
