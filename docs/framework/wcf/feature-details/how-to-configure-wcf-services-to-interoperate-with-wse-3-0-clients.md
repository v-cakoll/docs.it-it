---
title: 'Procedura: configurare i servizi WCF per interagire con i client WSE 3.0'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c93b91123c7622bea125bfa702c53a697b1ac84c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Procedura: configurare i servizi WCF per interagire con i client WSE 3.0
I servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sono compatibili a livello di rete con i client Web Services Enhancements 3.0 for Microsoft .NET (WSE) se tali servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono configurati per utilizzare la versione dell'agosto 2004 della specifica WS-Addressing.  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Per consentire a un servizio WCF di interagire con i client WSE 3.0  
  
1.  Definire un'associazione personalizzata per il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
     Per specificare l'utilizzo della versione dell'agosto 2004 della specifica WS-Addressing per la codifica dei messaggi, è necessario creare un'associazione personalizzata.  
  
    1.  Aggiungere un elemento figlio [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) per il [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del file di configurazione del servizio.  
  
    2.  Specificare un nome per l'associazione, aggiungendo un [ \<associazione >](../../../../docs/framework/misc/binding.md) per il [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) e impostando il `name` attributo.  
  
    3.  Specificare una modalità di autenticazione e la versione delle specifiche WS-Security che vengono utilizzati per proteggere i messaggi che sono compatibili con WSE 3.0, aggiungendo un elemento figlio [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) per il [ \<associazione >](../../../../docs/framework/misc/binding.md).  
  
         Per impostare la modalità di autenticazione, impostare il `authenicationMode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Una modalità di autenticazione è più o meno equivalente a un'asserzione di sicurezza turnkey in WSE 3.0. Nella tabella che segue viene illustrato il mapping delle modalità di autenticazione in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alle asserzioni di sicurezza turnkey in WSE 3.0.  
  
        |Modalità di autenticazione WCF|Asserzione di sicurezza turnkey WSE 3.0|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \*Una delle principali differenze tra il `mutualCertificate10Security` e `mutualCertificate11Security` asserzioni di sicurezza turnkey è la versione della specifica WS-Security utilizzata da WSE per proteggere i messaggi SOAP. Per `mutualCertificate10Security` viene utilizzata la versione WS-Security 1.0, mentre per `mutualCertificate11Security` viene utilizzata la versione WS-Security 1.1. Per [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], la versione della specifica WS-Security è specificata nel `messageSecurityVersion` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Per impostare la versione della specifica WS-Security che viene utilizzata per proteggere i messaggi SOAP, impostare il `messageSecurityVersion` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Per interagire con WSE 3.0, impostare il valore dell'attributo `messageSecurityVersion` su <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.  
  
    4.  Specificare che la versione di agosto 2004 della specifica WS-Addressing è utilizzata da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aggiungendo un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) e impostare il `messageVersion` al valore di <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  Quando si utilizza SOAP 1.2, impostare l'attributo `messageVersion` su <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.  
  
2.  Specificare l'utilizzo dell'associazione personalizzata da parte del servizio.  
  
    1.  Impostare il `binding` attributo del [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento `customBinding`.  
  
    2.  Impostare il `bindingConfiguration` attributo del [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento sul valore specificato nella `name` attributo del [ \<associazione >](../../../../docs/framework/misc/binding.md) personalizzata associazione.  
  
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
 [Procedura: Personalizzare un'associazione specificata dal sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
