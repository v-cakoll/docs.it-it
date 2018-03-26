---
title: Migrazione dei servizi Web WSE 3.0 a WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7e7187eb6ed444ba2c28aa301ce4b3b16129030
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2018
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migrazione dei servizi Web WSE 3.0 a WCF
La migrazione dei servizi Web WSE 3.0 a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] comporta diversi vantaggi, fra cui il miglioramento delle prestazioni, il supporto di trasporti e scenari di sicurezza aggiuntivi nonché la possibilità di applicare le specifiche WS-*. In particolare, la migrazione di un servizio Web da WSE 3.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può comportare un miglioramento delle prestazioni compreso fra 200% e 400%. Per ulteriori informazioni sui trasporti supportati da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere [scelta di un trasporto](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Per un elenco degli scenari supportati da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere [comuni scenari di sicurezza](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Per un elenco delle specifiche supportate da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere [Guida di interoperabilità di protocolli di servizi Web](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 Nelle sezioni seguenti vengono fornite indicazioni su come eseguire la migrazione di funzionalità specifiche di un servizio Web da WSE 3.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="general"></a>Generale  
 Le applicazioni WSE 3.0 e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] prevedono l'interoperabilità a livello di trasmissione e un set comune di terminologia. L'interoperabilità a livello di trasmissione delle applicazioni WSE 3.0 e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si basa sul set di specifiche WS-* supportato da entrambe. Lo sviluppo di un'applicazione WSE 3.0 o [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] presenta un set comune di terminologia, ad esempio i nomi delle asserzioni di sicurezza turnkey in WSE e le modalità di autenticazione.  
  
 Benché vi siano molte analogie fra il modello di programmazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e quello di ASP.NET o WSE 3.0, di fatto tali modelli sono diversi. Per informazioni dettagliate sul [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modello di programmazione, vedere [ciclo di programmazione di base](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  Eseguire la migrazione di un servizio Web WSE a WCF i [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento può essere utilizzato per generare un client. Tuttavia, le interfacce e le classi contenute in questo client sono utilizzabili anche come base per un servizio WCF. L'attributo <xref:System.ServiceModel.OperationContractAttribute> delle interfacce che vengono generate viene applicato ai membri del contratto con la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> impostata su `*`. Quando un client WSE chiama un servizio Web con questa impostazione, viene generata l'eccezione seguente: **Web.Services3.ResponseProcessingException: WSE910: si è verificato un errore durante l'elaborazione di un messaggio di risposta ed è possibile trovare l'errore in interna eccezione**. Per risolvere questo problema, impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> dell'attributo <xref:System.ServiceModel.OperationContractAttribute> su un valore diverso da `null`, ad esempio `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Sicurezza  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Servizi Web WSE 3.0 protetti mediante un file dei criteri  
 I servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono utilizzare un file di configurazione per proteggere un servizio. Tale meccanismo è analogo a un file dei criteri di WSE 3.0. Quando in WSE 3.0 si protegge un servizio Web tramite un file dei criteri, si utilizza un'asserzione di sicurezza turnkey oppure un'asserzione di criteri personalizzata. Le asserzioni di sicurezza turnkey corrispondono in modo quasi identico alla modalità di autenticazione di un elemento di associazione di sicurezza di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Oltre a presentare una denominazione analoga o identica, le modalità di autenticazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e le asserzioni di sicurezza turnkey di WSE 3.0 proteggono i messaggi utilizzando gli stessi tipi di credenziale. Ad esempio, l'asserzione di sicurezza turnkey `usernameForCertificate` di WSE 3.0 corrisponde alla modalità di autenticazione `UsernameForCertificate` di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Gli esempi di codice seguenti illustrano la corrispondenza fra un criterio minimo che utilizza un'asserzione di sicurezza turnkey `usernameForCertificate` di WSE 3.0 e una modalità di autenticazione `UsernameForCertificate` di un'associazione personalizzata di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"   
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 Per eseguire la migrazione delle impostazioni di sicurezza di un servizio Web specificate in un file dei criteri da WSE 3.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], è necessario creare un'associazione personalizzata in un file di configurazione e quindi impostare l'asserzione di sicurezza turnkey sulla relativa modalità di autenticazione equivalente. Quando i client WSE 3.0 comunicano con il servizio occorre inoltre configurare l'associazione personalizzata in modo che utilizzi la specifica WS-Addressing dell'agosto 2004. Quando il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di cui è stata eseguita la migrazione non richiede la comunicazione con i client WSE 3.0 e deve gestire solo la parità di sicurezza, anziché creare un'associazione personalizzata può essere conveniente utilizzare le associazioni definite dal sistema di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con le impostazioni di sicurezza appropriate.  
  
 Nella tabella seguente viene illustrata la corrispondenza fra un file dei criteri di WSE 3.0 e l'associazione personalizzata equivalente di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
|Asserzione di sicurezza turnkey di WSE 3.0|Configurazione dell'associazione personalizzata di WCF|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security / >|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Per ulteriori informazioni sulla creazione di associazioni personalizzate in WCF, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Servizi Web WSE 3.0 protetti mediante il codice dell'applicazione  
 Quando si utilizza WSE 3.0 o [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] i requisiti di sicurezza possono essere specificati nel codice anziché nella configurazione dell'applicazione. Per eseguire questa operazione in WSE 3.0 occorre creare una classe che deriva dalla classe `Policy` e quindi aggiungere i requisiti chiamando il metodo `Add`. Per ulteriori informazioni su come specificare i requisiti di sicurezza nel codice, vedere [procedura: proteggere un servizio Web senza utilizzando un File di criteri](http://go.microsoft.com/fwlink/?LinkId=73747). In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], per specificare in codice i requisiti di sicurezza, è necessario creare un'istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection> e quindi aggiungere un'istanza di un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> alla raccolta <xref:System.ServiceModel.Channels.BindingElementCollection>. Per impostare i requisiti delle asserzioni di sicurezza occorre utilizzare i metodi di supporto statici della modalità di autenticazione della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>. Per ulteriori informazioni su come specificare i requisiti di sicurezza nel codice usando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere [procedura: creare un personalizzato associazione usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) e [come: creare un elemento SecurityBindingElement per una Modalità di autenticazione specificato](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Asserzione di criteri personalizzata di WSE 3.0  
 In WSE 3.0 sono disponibili due tipi di asserzioni di criteri personalizzate: le asserzioni che proteggono i messaggi SOAP e quelle che non li proteggono. Le asserzioni di criteri che proteggono i messaggi SOAP derivano dalla classe `SecurityPolicyAssertion` di WSE 3.0 e l'equivalente concettuale in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è la classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Un importante punto da tenere presente è che le asserzioni di sicurezza turnkey WSE 3.0 sono un sottoinsieme delle modalità di autenticazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Se è stata creata un'asserzione di criteri personalizzata in WSE 3.0 è possibile che esista una modalità di autenticazione equivalente in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Ad esempio, anziché fornire un'asserzione di sicurezza CertificateOverTransport equivalente all'asserzione di sicurezza turnkey `UsernameOverTransport`, WSE 3.0 utilizza un certificato X.509 per eseguire l'autenticazione client. Se è stata definita un'asserzione di criteri personalizzata per questo scenario, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] semplifica la migrazione. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definisce una modalità di autenticazione per questo scenario, consentendo di utilizzare i metodi di supporto statici della modalità di autenticazione per configurare un oggetto [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Quando in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non esiste alcuna modalità di autenticazione equivalente a un'asserzione di criteri personalizzata che protegge i messaggi SOAP, derivare una classe dalla classe <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> oppure <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e specificare l'elemento di associazione equivalente. Per ulteriori informazioni, vedere [procedura: creare un personalizzato associazione usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Per convertire un'asserzione di criteri personalizzati che non è possibile protetta un messaggio SOAP, vedere [filtro](../../../../docs/framework/wcf/feature-details/filtering.md) e l'esempio [intercettatore di messaggi personalizzato](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Token di sicurezza personalizzato di WSE 3.0  
 Il modello di programmazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per la creazione di un token personalizzato è diverso che WSE 3.0. Per informazioni dettagliate sulla creazione di un token personalizzato in WSE, vedere [la creazione di token di sicurezza personalizzato](http://go.microsoft.com/fwlink/?LinkID=73750). Per informazioni dettagliate sulla creazione di un token personalizzato in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere [procedura: creare un Token personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Gestore del token personalizzato di WSE 3.0  
 Il modello di programmazione per la creazione di un gestore di token personalizzati è diverso in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] rispetto a WSE 3.0. Per informazioni dettagliate su come creare un gestore del token personalizzato e gli altri componenti necessari per un token di sicurezza personalizzato, vedere [procedura: creare un Token personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  Se è stato creato un gestore del token di sicurezza `UsernameToken` personalizzato, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] offre un meccanismo per specificare la logica di autenticazione in modo più semplice rispetto alla creazione di un gestore del token di sicurezza personalizzato. Per ulteriori informazioni, vedere [procedura: utilizzare un nome utente personalizzata e convalida della Password](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Servizi Web WSE 3.0 che utilizzano messaggi SOAP con codifica MTOM  
 Analogamente a un'applicazione WSE 3, un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può specificare in configurazione l'utilizzo del meccanismo di codifica dei messaggi MTOM. Per eseguire la migrazione questa impostazione, aggiungere il [ \<mtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) all'associazione per il servizio. L'esempio di codice seguente illustra come specificare la codifica MTOM in WSE 3.0 per un servizio equivalente in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>Messaggistica  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>Applicazioni WSE 3.0 che utilizzano l'API del sistema di messaggistica di WSE  
 Quando si utilizza l'API del sistema di messaggistica di WSE per accedere in modo diretto ai dati XML scambiati fra il client e il servizio Web, l'applicazione può essere convertita in modo da utilizzare il formato POX (Plain Old XML). Per ulteriori dettagli su POX, vedere [l'interoperabilità con applicazioni POX](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md). Per ulteriori informazioni sull'API di messaggistica di WSE, vedere [invio e ricezione di messaggi con WSE messaggistica API SOAP](http://go.microsoft.com/fwlink/?LinkID=73755).  
  
## <a name="transports"></a>Trasporti  
  
### <a name="tcp"></a>TCP  
 Per impostazione predefinita, i client e i servizi Web WSE 3.0 che inviano messaggi SOAP utilizzando il trasporto TCP non sono interoperativi con i client e i servizi Web [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Questa incompatibilità è dovuta a differenze nella modalità di frame del protocollo TCP e si basa inoltre su motivi legati alle prestazioni. Tuttavia, nell'esempio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene indicato come implementare una sessione TCP personalizzata che interopera con WSE 3.0. Per informazioni dettagliate su questo esempio, vedere [trasporto: interoperabilità di WSE 3.0 TCP](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Per specificare che un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applicazione utilizza il trasporto TCP, utilizzare il [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Trasporto personalizzato  
 L'equivalente di un trasporto personalizzato di WSE 3.0 in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è un'estensione di canale. Per informazioni dettagliate sulla creazione di un'estensione di canale, vedere [estendendo il livello del canale](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Ciclo di vita della programmazione di base](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Procedura: Creare un elemento SecurityBindingElement per una modalità di autenticazione specificata](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
