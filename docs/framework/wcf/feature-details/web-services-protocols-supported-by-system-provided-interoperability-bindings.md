---
title: Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: 80fa0e501f425bd5b917059e90f2811f075db651
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746900"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
Windows Communication Foundation (WCF) è progettato per interagire con i servizi Web che supportano un set di specifiche note come specifiche dei servizi Web. Per semplificare la configurazione del servizio per le procedure consigliate di interoperabilità, in WCF sono state introdotte tre associazioni interoperative fornite dal sistema: <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>, <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>e <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Per l'interoperabilità con l'organizzazione per l'avanzamento degli standard OASIS (Structured Information Standards), WCF include un binding fornito dal sistema interoperativo: <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>. Per la pubblicazione di metadati, WCF include due associazioni interoperative fornite dal sistema: [\<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) e [\<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). In questo argomento vengono elencate le specifiche supportate dalle associazioni interoperative fornite dal sistema.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Protocolli di servizi Web supportati da associazioni basicHttpBinding, wsHttpBinding, ws2007HttpBinding e wsDualHttpBinding  
  
### <a name="all-bindings"></a>Tutte le associazioni  
 Le associazioni [\<basichttpbinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [\<wshttpbinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)e [\<WS2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) supportano i protocolli seguenti.  
  
> [!NOTE]
> Per informazioni sulle associazioni utilizzate per pubblicare metadati, vedere la sezione "Associazioni di metadati fornite dal sistema", più avanti in questo argomento.  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1,1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> `BasicHttpBinding`, `WSHttpBinding` e `WS2007HttpBinding` utilizzano i trasporti HTTP e HTTPS.|  
|Messaggistica|MTOM|[MTOM](https://www.w3.org/TR/soap12-mtom/)<br /><br /> `basicHttpBinding`, `wsHttpBinding` e `ws2007HttpBinding` supportano Message Transmission Optimization Mechanism (MTOM). Non utilizzato per impostazione predefinita. Per utilizzare MTOM, impostare l'attributo `messageEncoding` su `"Mtom"`.<br /><br /> Esempio:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Metadati|WSDL 1.1|[WSDL 1,1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF utilizza Web Services Description Language (WSDL) per descrivere i servizi.|  
|Metadati|WS-Policy|[WS-Policy](https://www.w3.org/Submission/WS-Policy/)<br /><br /> WCF utilizza la specifica WS-Policy insieme alle asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|Metadati|WS-Policy 1.5|[WS-Policy 1,5](https://www.w3.org/TR/2007/CR-ws-policy-20070605/)<br /><br /> WCF utilizza la specifica WS-Policy insieme alle asserzioni specifiche del dominio per descrivere le funzionalità e i requisiti del servizio.|  
|Metadati|WS-PolicyAttachment|[WS-PolicyAttachment](http://specs.xmlsoap.org/ws/2004/09/policy/ws-policyattachment.pdf)<br /><br /> WCF implementa WS-PolicyAttachment per allineare espressioni di criteri in diversi ambiti in Web Services Description Language (WSDL).|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1,1|[SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)<br /><br /> In conformità con Basic Profile 1.1, l'elemento `basicHttpBinding` implementa il protocollo di messaggi SOAP 1.1.|  
|Sicurezza|WSS SOAP Message Security 1.0|[Sicurezza messaggi SOAP WSS 1,0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> In conformità con Basic Security Profile, l'elemento `basicHttpBinding` implementa la specifica Web Services Security (WSS) SOAP Message Security 1.0 per protezione basata su nome utente/password e X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security UsernameToken Profile 1.0|[Profilo UsernameToken per la sicurezza del messaggio SOAP WSS 1,0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Sicurezza|Profilo del token del certificato X. 509 per la sicurezza del messaggio SOAP WSS 1,0|[Profilo del token del certificato X. 509 per la sicurezza del messaggio SOAP WSS 1,0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding, e wsDualHttpBinding  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1.2|[Nozioni di base](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Framework di messaggistica](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Aggiunte (incluso il binding HTTP)](https://www.w3.org/TR/soap12-part2/)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1,0-Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Indirizzamento dei servizi Web 1,0-SOAP](https://www.w3.org/TR/ws-addr-soap/)<br /><br /> `wsHttpBinding`, `ws2007HttpBinding` e `wsDualHttpBinding` implementano la raccomandazione WS-Addressing del World Wide Web Consortium (W3C) per abilitare la messaggistica asincrona, la correlazione dei messaggi e i meccanismi di indirizzamento indipendenti dal trasporto.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Messaggistica|WS-Addressing 1.0 - Metadata|[Metadati WS-Addressing 1,0](https://www.w3.org/2007/05/addressing/metadata/) Il supporto per questo protocollo viene abilitato impostando la versione del criterio in comportamento ServiceMetadata-con PolicyVersion impostato su 1,2 (impostazione predefinita), la descrizione WSDL è conforme a WSDL WS-Addressing, con PolicyVersion impostato su 1,5, la descrizione WSDL è conforme ai metadati WS-Addressing.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Sicurezza|WSS SOAP Message Security 1.0|[Sicurezza messaggi SOAP WSS 1,0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> Deve essere utilizzato quando l'attributo `securityMode` è impostato su "wsSecurityOverHttp" (impostazione predefinita) e i parametri sono configurati utilizzando un elemento figlio `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Sicurezza|Profilo UsernameToken per la sicurezza del messaggio SOAP WSS 1,1|[Profilo UsernameToken per la sicurezza del messaggio SOAP WSS 1,0](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> Deve essere utilizzato quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[Profilo del token del certificato X. 509 per la sicurezza del messaggio SOAP WSS 1,1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)<br /><br /> Deve essere utilizzato per la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username", "Certificate" o "None". Utilizzarlo inoltre per l'autenticazione del client quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Certificate".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security Kerberos Token Profile 1.1|[Profilo del token Kerberos per la sicurezza del messaggio SOAP WSS 1,1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)<br /><br /> Deve essere utilizzato per l'autenticazione e la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicurezza|WS-SecureConversation|[WS-SecureConversation](http://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> Deve essere utilizzato per fornire una sessione protetta quando l'attributo `security/@mode` è impostato su "Message" e l'attributo `message/@establishSecurityContext` è impostato su "true" (impostazione predefinita).|  
|Sicurezza|WS-Trust|[WS-Trust](http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf)<br /><br /> Utilizzato da WS-SecureConversation (vedere sopra).|  
|Messaggistica affidabile|WS-ReliableMessaging|[WS-ReliableMessaging](http://specs.xmlsoap.org/ws/2005/02/rm/ws-reliablemessaging.pdf)<br /><br /> Deve essere utilizzato quando l'associazione è configurata per utilizzare `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transazioni|WS-AtomicTransaction|[WS-AtomicTransaction](http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)<br /><br /> Utilizzare per la comunicazione tra le gestioni transazioni. I client e i servizi WCF utilizzano sempre gestori transazioni locali.|  
|Transazioni|WS-Coordination|[WS-Coordination](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))<br /><br /> Deve essere utilizzato per propagare il contesto della transazione quando l'attributo `flowTransactions` è impostato su "Allowed" o "Required".<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding e ws2007FederationHttpBinding  
 Gli elementi [\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e [\<WS2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) sono stati introdotti per fornire supporto per gli scenari federati, in cui una terza parte rilascia un token usato per autenticare un client. Oltre ai protocolli utilizzati da `wsHttpBinding`, `wsFederationHttpBinding` utilizza:  
  
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
 Il binding [\<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) supporta i protocolli seguenti. Per ulteriori informazioni sull'utilizzo di questa associazione, vedere [pubblicazione di metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1,1](https://www.ietf.org/rfc/rfc2616.txt)|  
|Messaggistica|SOAP 1.2|[Nozioni di base](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Framework di messaggistica](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Aggiunte (incluso il binding HTTP)](https://www.w3.org/TR/soap12-part2/)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1,0-Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Indirizzamento dei servizi Web 1,0-SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 [\<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) supporta i protocolli seguenti. Per ulteriori informazioni sull'utilizzo di questa associazione, vedere [pubblicazione di metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocollo|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1,1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> La protezione del trasporto è attivata.|  
|Messaggistica|SOAP 1.2|[Nozioni di base](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Framework di messaggistica](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Aggiunte (incluso il binding HTTP)](https://www.w3.org/TR/soap12-part2/)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1,0-Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Indirizzamento dei servizi Web 1,0-SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
## <a name="see-also"></a>Vedere anche

- [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
