---
title: 'Procedura: Configurare i servizi WCF per interagire con WSE 3.0 client'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: d42e2d4c0bf4c708f2dbb27d14d1adddc3fead41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635793"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Procedura: Configurare i servizi WCF per interagire con WSE 3.0 client
Servizi Windows Communication Foundation (WCF) sono compatibili a livello di transito con Web Services Enhancements 3.0 per i client Microsoft .NET (WSE) quando i servizi WCF sono configurati per usare la versione di agosto 2004 della specifica WS-Addressing.  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Per consentire a un servizio WCF di interagire con i client WSE 3.0  
  
1.  Definire un'associazione personalizzata per il servizio WCF.  
  
     Per specificare l'utilizzo della versione dell'agosto 2004 della specifica WS-Addressing per la codifica dei messaggi, è necessario creare un'associazione personalizzata.  
  
    1.  Aggiungere un elemento figlio [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) per il [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del file di configurazione del servizio.  
  
    2.  Specificare un nome per l'associazione, aggiungendo un [ \<associazione >](../../../../docs/framework/misc/binding.md) per il [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) e impostando il `name` attributo.  
  
    3.  Specificare una modalità di autenticazione e la versione delle specifiche WS-Security utilizzate per proteggere i messaggi che sono compatibili con WSE 3.0, aggiungendo un elemento figlio [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) per il [ \<binding >](../../../../docs/framework/misc/binding.md).  
  
         Per impostare la modalità di autenticazione, impostare il `authenicationMode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Una modalità di autenticazione è più o meno equivalente a un'asserzione di sicurezza turnkey in WSE 3.0. Nella tabella seguente le modalità di autenticazione in WCF per le asserzioni di sicurezza turnkey in WSE 3.0.  
  
        |Modalità di autenticazione WCF|Asserzione di sicurezza turnkey WSE 3.0|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \* Una delle principali differenze tra il `mutualCertificate10Security` e `mutualCertificate11Security` asserzioni di sicurezza turnkey è la versione della specifica WS-Security utilizzata da WSE per proteggere i messaggi SOAP. Per `mutualCertificate10Security` viene utilizzata la versione WS-Security 1.0, mentre per `mutualCertificate11Security` viene utilizzata la versione WS-Security 1.1. Per WCF, la versione della specifica WS-Security è specificata nel `messageSecurityVersion` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Per impostare la versione della specifica WS-Security che viene usata per proteggere i messaggi SOAP, impostare il `messageSecurityVersion` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Per interagire con WSE 3.0, impostare il valore dell'attributo `messageSecurityVersion` su <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.  
  
    4.  Specificare che la versione dell'agosto 2004 della specifica WS-Addressing è utilizzata da WCF tramite l'aggiunta di un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) e impostare il `messageVersion` sul relativo valore <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  Quando si utilizza SOAP 1.2, impostare l'attributo `messageVersion` su <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.  
  
2.  Specificare l'utilizzo dell'associazione personalizzata da parte del servizio.  
  
    1.  Impostare il `binding` attributo del [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento `customBinding`.  
  
    2.  Impostare il `bindingConfiguration` attributo del [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento sul valore specificato nella `name` attributo del [ \<associazione >](../../../../docs/framework/misc/binding.md) per l'oggetto personalizzato associazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene specificato che `Service.HelloWorldService` utilizza un'associazione personalizzata per interagire con i client WSE 3.0. L'associazione personalizzata specifica che per la codifica dei messaggi scambiati viene utilizzata la versione dell'agosto 2004 del set di specifiche WS-Addressing e WS-Security 1.1. I messaggi vengono protetti utilizzando la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Personalizzare un'associazione fornita dal sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
