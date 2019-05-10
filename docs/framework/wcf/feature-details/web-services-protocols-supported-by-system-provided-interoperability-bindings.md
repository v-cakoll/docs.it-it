---
title: Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: b77e0bf52e20ce5bd8f1c0deecfc822e9f910675
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648382"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema
Windows Communication Foundation (WCF) è realizzato per interoperare con servizi Web che supportano un set di specifiche note come specifiche dei servizi Web. Per semplificare la configurazione del servizio per le procedure consigliate di interoperabilità, WCF introduce tre associazioni interoperative fornite dal sistema: <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>, <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>, e <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Per l'interoperabilità con organizzazione per gli standard Advancement of Structured Information Standards (OASIS), WCF include un'associazione interoperativa fornita dal sistema: <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>. Per la pubblicazione dei metadati, WCF include due associazioni interoperative fornite dal sistema: [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) e [ \<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). In questo argomento vengono elencate le specifiche supportate dalle associazioni interoperative fornite dal sistema.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Protocolli di servizi Web supportati da associazioni basicHttpBinding, wsHttpBinding, ws2007HttpBinding e wsDualHttpBinding  
  
### <a name="all-bindings"></a>Tutte le associazioni  
 Il [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), e [ \<ws2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) supporto delle associazioni di protocolli seguenti.  
  
> [!NOTE]
>  Per informazioni sulle associazioni utilizzate per pubblicare metadati, vedere la sezione "Associazioni di metadati fornite dal sistema", più avanti in questo argomento.  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`, `WSHttpBinding` e `WS2007HttpBinding` utilizzano i trasporti HTTP e HTTPS.|  
|Messaggistica|MTOM|[MTOM](https://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`, `wsHttpBinding` e `ws2007HttpBinding` supportano Message Transmission Optimization Mechanism (MTOM). Non utilizzato per impostazione predefinita. Per utilizzare MTOM, impostare l'attributo `messageEncoding` su `"Mtom"`.<br /><br /> Esempio:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Metadati|WSDL 1.1|[WSDL 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF Usa Web Services Description Language (WSDL) per descrivere i servizi.|  
|Metadati|WS-Policy|[WS-Policy](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> WCF utilizza la specifica WS-Policy insieme alle asserzioni specifiche del dominio per descrivere le funzionalità e requisiti del servizio.|  
|Metadati|WS-Policy 1.5|[WS-Policy 1.5](https://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> WCF utilizza la specifica WS-Policy insieme alle asserzioni specifiche del dominio per descrivere le funzionalità e requisiti del servizio.|  
|Metadati|WS-PolicyAttachment|[WS-PolicyAttachment](https://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> WCF implementa WS-PolicyAttachment per allegare espressioni di criteri a vari ambiti in servizi di linguaggio WSDL (Web Description).|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1,1|[SOAP 1.1](https://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> In conformità con Basic Profile 1.1, l'elemento `basicHttpBinding` implementa il protocollo di messaggi SOAP 1.1.|  
|Sicurezza|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1,0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> In conformità con Basic Security Profile, l'elemento `basicHttpBinding` implementa la specifica Web Services Security (WSS) SOAP Message Security 1.0 per protezione basata su nome utente/password e X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security UsernameToken Profile 1.0|[WSS SOAP messaggio Security Kerberos token Profile 1.0](https://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Sicurezza|WSS SOAP messaggio sicurezza X.509 Certificate Token Profile 1.0|[WSS SOAP messaggio sicurezza X.509 Certificate Token Profile 1.0](https://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding, e wsDualHttpBinding  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Messaggistica|SOAP 1.2|[Primer](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Aggiunte (inclusa l'associazione HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> `wsHttpBinding`, `ws2007HttpBinding` e `wsDualHttpBinding` implementano la raccomandazione WS-Addressing del World Wide Web Consortium (W3C) per abilitare la messaggistica asincrona, la correlazione dei messaggi e i meccanismi di indirizzamento indipendenti dal trasporto.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Messaggistica|WS-Addressing 1.0 - Metadata|[WS-Addressing 1.0 Metadata](https://www.w3.org/2007/05/addressing/metadata) supporto per questo protocollo viene abilitato impostando la versione dei criteri nel comportamento ServiceMetadata - con la impostata su 1,2 (impostazione predefinita), la descrizione wsdl è conforme a WS-Addressing wsdl, con specifica impostata su 1,5, la descrizione wsdl è conforme con i metadati ws-addressing.<br /><br /> WCF non supporta la crittografia delle intestazioni WS-Addressing, sebbene sia consentita dalle specifiche WS-*.|  
|Sicurezza|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1,0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> Deve essere utilizzato quando l'attributo `securityMode` è impostato su "wsSecurityOverHttp" (impostazione predefinita) e i parametri sono configurati utilizzando un elemento figlio `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP messaggio Security UsernameToken Profile 1.1|[WSS SOAP messaggio Security Kerberos token Profile 1.0](https://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> Deve essere utilizzato quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP messaggio sicurezza X.509 Certificate Token Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> Deve essere utilizzato per la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Username", "Certificate" o "None". Utilizzarlo inoltre per l'autenticazione del client quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Certificate".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicurezza|WSS SOAP Message Security Kerberos Token Profile 1.1|[WSS SOAP messaggio Security Kerberos Token Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> Deve essere utilizzato per l'autenticazione e la protezione dei messaggi quando l'attributo `wsSecurity` dell'elemento `authenticationMode` è impostato su "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicurezza|WS-SecureConversation|[WS-SecureConversation](https://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Deve essere utilizzato per fornire una sessione protetta quando l'attributo `security/@mode` è impostato su "Message" e l'attributo `message/@establishSecurityContext` è impostato su "true" (impostazione predefinita).|  
|Sicurezza|WS-Trust|[WS-Trust](https://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> Utilizzato da WS-SecureConversation (vedere sopra).|  
|Messaggistica affidabile|WS-ReliableMessaging|[WS-ReliableMessaging](https://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> Deve essere utilizzato quando l'associazione è configurata per utilizzare `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transazioni|WS-AtomicTransaction|[WS-AtomicTransaction](https://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> Utilizzare per la comunicazione tra le gestioni transazioni. Servizi e client WCF utilizzano sempre Gestioni transazioni locali.|  
|Transazioni|WS-Coordination|[WS-Coordination](https://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> Deve essere utilizzato per propagare il contesto della transazione quando l'attributo `flowTransactions` è impostato su "Allowed" o "Required".<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding e ws2007FederationHttpBinding  
 Il [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e [ \<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elementi sono stati introdotti per fornire supporto per gli scenari federati, dove un terzo parte rilascia un token utilizzato per autenticare un client. Oltre ai protocolli utilizzati da `wsHttpBinding`, `wsFederationHttpBinding` utilizza:  
  
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
  
 Per altre informazioni, vedere [federazione](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>System-Provided Metadata Bindings  
 Nelle tabelle seguenti vengono descritti i protocolli supportati dalle associazioni dei metadati interoperativi forniti dal sistema, esposte dalla classe <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 Il [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) associazione supporta i protocolli seguenti. Per altre informazioni sull'uso di questa associazione, vedere [pubblicazione di metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)|  
|Messaggistica|SOAP 1.2|[Primer](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Aggiunte (inclusa l'associazione HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 [\<l'associazione mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) supporta i protocolli seguenti. Per altre informazioni sull'uso di questa associazione, vedere [pubblicazione di metadati](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocol|Specifica e utilizzo|  
|--------------|--------------|-----------------------------|  
|Trasporto|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> La protezione del trasporto è attivata.|  
|Messaggistica|SOAP 1.2|[Primer](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Framework di messaggistica](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Aggiunte (inclusa l'associazione HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaggistica|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadati|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange per recuperare XML Schema, WSDL e WS-Policy.|  
  
## <a name="see-also"></a>Vedere anche

- [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
