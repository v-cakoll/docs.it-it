---
title: Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4bfc4342435580796423056889b1c3bd22153740
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2018
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è realizzato per interoperare con servizi Web che supportano un set di specifiche note come specifiche dei servizi Web. Per semplificare la configurazione del servizio per le procedure consigliate di interoperabilità, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono state introdotte tre associazioni interoperative fornite dal sistema: <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>, <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType> e <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Per l'interoperabilità con gli standard OASIS (Organization for the Advancement of Structured Information Standards), in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è inclusa un'associazione interoperativa fornita dal sistema: <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>. Per la pubblicazione dei metadati, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] include due associazioni interoperative fornita dal sistema: [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) e [ \<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). In questo argomento vengono elencate le specifiche supportate dalle associazioni interoperative fornite dal sistema.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Protocolli di servizi Web supportati da associazioni basicHttpBinding, wsHttpBinding, ws2007HttpBinding e wsDualHttpBinding  
  
### <a name="all-bindings"></a>Tutte le associazioni  
 Il [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), e [ \<ws2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) supporto delle associazioni di protocolli seguenti.  
  
> [!NOTE]
>  Per informazioni sulle associazioni utilizzate per pubblicare metadati, vedere la sezione "Associazioni di metadati fornite dal sistema", più avanti in questo argomento.  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`, `WSHttpBinding` e `WS2007HttpBinding` utilizzano i trasporti HTTP e HTTPS.|  
|Messaggistica|MTOM|[MTOM](http://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`, `wsHttpBinding` e `ws2007HttpBinding` supportano Message Transmission Optimization Mechanism (MTOM). Non utilizzato per impostazione predefinita. Per utilizzare MTOM, impostare l'attributo `messageEncoding` su `"Mtom"`.<br /><br /> Esempio:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Metadati|WSDL 1.1|[WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa Web Services Description Language (WSDL) per descrivere i servizi.|  
|Metadati|WS-Policy|[WS-Policy](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza la specifica WS-Policy insieme ad asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|Metadati|WS-Policy 1.5|[WS-Policy 1.5](http://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza la specifica WS-Policy insieme ad asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|Metadati|WS-PolicyAttachment|[WS-PolicyAttachment](http://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS-PolicyAttachment per allegare espressioni di criteri a vari ambiti in Web Services Description Language (WSDL).|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1,1|[SOAP 1.1](http://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> In conformità con Basic Profile 1.1, l'elemento `basicHttpBinding` implementa il protocollo di messaggi SOAP 1.1.|  
|Sicurezza|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1,0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> In conformità con Basic Security Profile, l'elemento `basicHttpBinding` implementa la specifica Web Services Security (WSS) SOAP Message Security 1.0 per protezione basata su nome utente/password e X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security UsernameToken Profile 1.0|[WSS SOAP messaggio Security UsernameToken Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Sicurezza|WSS SOAP messaggio sicurezza x. 509 Certificate Token Profile 1.0|[WSS SOAP messaggio sicurezza x. 509 Certificate Token Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding, e wsDualHttpBinding  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1.2|[Nozioni di base](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Componenti aggiuntivi (incluso l'associazione HTTP)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[1.0 - Core indirizzamento dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> `wsHttpBinding`, `ws2007HttpBinding` e `wsDualHttpBinding` implementano la raccomandazione WS-Addressing del World Wide Web Consortium (W3C) per abilitare la messaggistica asincrona, la correlazione dei messaggi e i meccanismi di indirizzamento indipendenti dal trasporto.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Messaggistica|WS-Addressing 1.0 - Metadata|[WS-Addressing 1.0 metadati](http://www.w3.org/2007/05/addressing/metadata) il supporto per questo protocollo viene abilitato impostando la versione del criterio nel comportamento di ServiceMetadata - con policyversion impostato su 1.2 (impostazione predefinita), descrizione wsdl è conforme a WS-Addressing wsdl con policyversion impostato su 1.5, la descrizione wsdl è compatibile con i metadati ws-addressing.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Sicurezza|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1,0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> Deve essere utilizzato quando l'attributo `securityMode` è impostato su "wsSecurityOverHttp" (impostazione predefinita) e i parametri sono configurati utilizzando un elemento figlio `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP messaggio Security UsernameToken Profile 1.1|[WSS SOAP messaggio Security UsernameToken Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> Deve essere utilizzato quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP messaggio sicurezza X.509 Certificate Token Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> Deve essere utilizzato per la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username", "Certificate" o "None". Utilizzarlo inoltre per l'autenticazione del client quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Certificate".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security Kerberos Token Profile 1.1|[WSS SOAP messaggio Security Kerberos Token Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> Deve essere utilizzato per l'autenticazione e la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicurezza|WS-SecureConversation|[WS-SecureConversation](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Deve essere utilizzato per fornire una sessione protetta quando l'attributo `security/@mode` è impostato su "Message" e l'attributo `message/@establishSecurityContext` è impostato su "true" (impostazione predefinita).|  
|Sicurezza|WS-Trust|[WS-Trust](http://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> Utilizzato da WS-SecureConversation (vedere sopra).|  
|Messaggistica affidabile|WS-ReliableMessaging|[WS-ReliableMessaging](http://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> Deve essere utilizzato quando l'associazione è configurata per utilizzare `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transazioni|WS-AtomicTransaction|[WS-AtomicTransaction](http://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> Utilizzare per la comunicazione tra le gestioni transazioni. I client e i servizi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizzano sempre le gestioni transazioni locali.|  
|Transazioni|WS-Coordination|[WS-Coordination](http://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> Deve essere utilizzato per propagare il contesto della transazione quando l'attributo `flowTransactions` è impostato su "Allowed" o "Required".<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding e ws2007FederationHttpBinding  
 Il [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e [ \<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) vengono introdotti gli elementi per supportare gli scenari federati, dove un terzo entità rilascia un token utilizzato per autenticare un client. Oltre ai protocolli utilizzati da `wsHttpBinding`, `wsFederationHttpBinding` utilizza:  
  
-   `WS-Trust` per il rilascio dei token.  
  
-   WSS Security Assertions Markup Language (SAML) Token Profile 1.0 e 1.1 per il formato dei token rilasciati più comuni.  
  
 Esempio:  
  
```xml  
<wsFederationHttpBinding>  
  <binding name="myBinding">  
     <security mode="Message">  
       <message issuedKeyType="Symmetric"   
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
         <issuerMetadata address =   
         'http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex'>  
       </message>  
     </security>  
  </binding>  
</wsFederationHttpBinding>  
```  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Federazione](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>System-Provided Metadata Bindings  
 Nelle tabelle seguenti vengono descritti i protocolli supportati dalle associazioni dei metadati interoperativi forniti dal sistema, esposte dalla classe <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 Il [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) associazione supporta i seguenti protocolli. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] utilizzando questa associazione, vedere [pubblicazione dei metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)|  
|Messaggistica|SOAP 1.2|[Nozioni di base](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Componenti aggiuntivi (incluso l'associazione HTTP)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[1.0 - Core indirizzamento dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 [\<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) supporta i seguenti protocolli. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] utilizzando questa associazione, vedere [pubblicazione dei metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> La protezione del trasporto è attivata.|  
|Messaggistica|SOAP 1.2|[Nozioni di base](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Componenti aggiuntivi (incluso l'associazione HTTP)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[1.0 - Core indirizzamento dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
## <a name="see-also"></a>Vedere anche  
 [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)  
 [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)  
 [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)  
 [\<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)  
 [\<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
