---
title: Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: 963325604f66ddd4f8470933584b7880c86403bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951564"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
Windows Communication Foundation (WCF) è progettato per interagire con i servizi Web che supportano un set di specifiche note come specifiche dei servizi Web. Per semplificare la configurazione del servizio per le procedure consigliate di interoperabilità, in WCF sono state introdotte <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>tre <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>associazioni interoperative fornite dal sistema:, e <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Per l'interoperabilità con l'organizzazione per l'avanzamento degli standard OASIS (Structured Information Standards), WCF include un binding interoperativo fornito dal sistema: <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>. Per la pubblicazione di metadati, WCF include due associazioni interoperative fornite dal sistema: [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) e [ \<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). In questo argomento vengono elencate le specifiche supportate dalle associazioni interoperative fornite dal sistema.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Protocolli di servizi Web supportati da associazioni basicHttpBinding, wsHttpBinding, ws2007HttpBinding e wsDualHttpBinding  
  
### <a name="all-bindings"></a>Tutte le associazioni  
 [ Le\<associazioni BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \<WSHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)e [ \<WS2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) supportano i protocolli seguenti.  
  
> [!NOTE]
> Per informazioni sulle associazioni utilizzate per pubblicare metadati, vedere la sezione "Associazioni di metadati fornite dal sistema", più avanti in questo argomento.  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`, `WSHttpBinding` e `WS2007HttpBinding` utilizzano i trasporti HTTP e HTTPS.|  
|Messaggistica|MTOM|[MTOM](https://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`, `wsHttpBinding` e `ws2007HttpBinding` supportano Message Transmission Optimization Mechanism (MTOM). Non utilizzato per impostazione predefinita. Per utilizzare MTOM, impostare l'attributo `messageEncoding` su `"Mtom"`.<br /><br /> Esempio:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Metadata|WSDL 1.1|[WSDL 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF utilizza Web Services Description Language (WSDL) per descrivere i servizi.|  
|Metadata|WS-Policy|[WS-Policy](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> WCF utilizza la specifica WS-Policy insieme alle asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|Metadata|WS-Policy 1.5|[WS-Policy 1,5](https://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> WCF utilizza la specifica WS-Policy insieme alle asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|Metadata|WS-PolicyAttachment|[WS-PolicyAttachment](https://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> WCF implementa WS-PolicyAttachment per allineare espressioni di criteri in diversi ambiti in Web Services Description Language (WSDL).|  
|Metadata|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1,1|[SOAP 1.1](https://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> In conformità con Basic Profile 1.1, l'elemento `basicHttpBinding` implementa il protocollo di messaggi SOAP 1.1.|  
|Security|WSS SOAP Message Security 1.0|[Sicurezza messaggi SOAP WSS 1,0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> In conformità con Basic Security Profile, l'elemento `basicHttpBinding` implementa la specifica Web Services Security (WSS) SOAP Message Security 1.0 per protezione basata su nome utente/password e X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Security|WSS SOAP Message Security UsernameToken Profile 1.0|[Profilo UsernameToken per la sicurezza del messaggio SOAP WSS 1,0](https://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Security|Profilo del token del certificato X. 509 per la sicurezza del messaggio SOAP WSS 1,0|[Profilo del token del certificato X. 509 per la sicurezza del messaggio SOAP WSS 1,0](https://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding, e wsDualHttpBinding  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1.2|[Nozioni](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Aggiunte (incluso il binding HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1,0-Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Indirizzamento dei servizi Web 1,0-SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> `wsHttpBinding`, `ws2007HttpBinding` e `wsDualHttpBinding` implementano la raccomandazione WS-Addressing del World Wide Web Consortium (W3C) per abilitare la messaggistica asincrona, la correlazione dei messaggi e i meccanismi di indirizzamento indipendenti dal trasporto.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Messaggistica|WS-Addressing 1.0 - Metadata|[Metadati WS-Addressing 1,0](https://www.w3.org/2007/05/addressing/metadata) Il supporto per questo protocollo viene abilitato impostando la versione del criterio nel comportamento ServiceMetadata-con PolicyVersion impostato su 1,2 (impostazione predefinita), la descrizione WSDL è conforme a WS-Addressing WSDL, con PolicyVersion impostato su 1,5, la descrizione WSDL è conforme ai metadati di WS-Addressing.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Security|WSS SOAP Message Security 1.0|[Sicurezza messaggi SOAP WSS 1,0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> Deve essere utilizzato quando l'attributo `securityMode` è impostato su "wsSecurityOverHttp" (impostazione predefinita) e i parametri sono configurati utilizzando un elemento figlio `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Security|Profilo UsernameToken per la sicurezza del messaggio SOAP WSS 1,1|[Profilo UsernameToken per la sicurezza del messaggio SOAP WSS 1,0](https://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> Deve essere utilizzato quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Security|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[Profilo del token del certificato X. 509 per la sicurezza del messaggio SOAP WSS 1,1](https://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> Deve essere utilizzato per la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username", "Certificate" o "None". Utilizzarlo inoltre per l'autenticazione del client quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Certificate".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Security|WSS SOAP Message Security Kerberos Token Profile 1.1|[Profilo del token Kerberos per la sicurezza del messaggio SOAP WSS 1,1](https://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> Deve essere utilizzato per l'autenticazione e la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Security|WS-SecureConversation|[WS-SecureConversation](https://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Deve essere utilizzato per fornire una sessione protetta quando l'attributo `security/@mode` è impostato su "Message" e l'attributo `message/@establishSecurityContext` è impostato su "true" (impostazione predefinita).|  
|Security|WS-Trust|[WS-Trust](https://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> Utilizzato da WS-SecureConversation (vedere sopra).|  
|Messaggistica affidabile|WS-ReliableMessaging|[WS-ReliableMessaging](https://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> Deve essere utilizzato quando l'associazione è configurata per utilizzare `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transazioni|WS-AtomicTransaction|[WS-AtomicTransaction](https://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> Utilizzare per la comunicazione tra le gestioni transazioni. I client e i servizi WCF utilizzano sempre gestori transazioni locali.|  
|Transazioni|WS-Coordination|[WS-Coordination](https://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> Deve essere utilizzato per propagare il contesto della transazione quando l'attributo `flowTransactions` è impostato su "Allowed" o "Required".<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding e ws2007FederationHttpBinding  
 Gli elementi [ \<WSFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e [ \<WS2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) sono stati introdotti per fornire supporto per gli scenari federati, in cui una terza parte rilascia un token usato per autenticare un client. Oltre ai protocolli utilizzati da `wsHttpBinding`, `wsFederationHttpBinding` utilizza:  
  
- `WS-Trust` per il rilascio dei token.  
  
- WSS Security Assertions Markup Language (SAML) Token Profile 1.0 e 1.1 per il formato dei token rilasciati più comuni.  
  
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
  
 Per ulteriori informazioni, vedere [Federazione](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>System-Provided Metadata Bindings  
 Nelle tabelle seguenti vengono descritti i protocolli supportati dalle associazioni dei metadati interoperativi forniti dal sistema, esposte dalla classe <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 Il binding > mexHttpBinding supporta i protocolli seguenti. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) Per ulteriori informazioni sull'utilizzo di questa associazione, vedere [pubblicazione di metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)|  
|Messaggistica|SOAP 1.2|[Nozioni](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Aggiunte (incluso il binding HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1,0-Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Indirizzamento dei servizi Web 1,0-SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadata|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 mexHttpsBinding > supporta i protocolli seguenti. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) Per ulteriori informazioni sull'utilizzo di questa associazione, vedere [pubblicazione di metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> La protezione del trasporto è attivata.|  
|Messaggistica|SOAP 1.2|[Nozioni](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Aggiunte (incluso il binding HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1,0-Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Indirizzamento dei servizi Web 1,0-SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadata|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
## <a name="see-also"></a>Vedere anche

- [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
