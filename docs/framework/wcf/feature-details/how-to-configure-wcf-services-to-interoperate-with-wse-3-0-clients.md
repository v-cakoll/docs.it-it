---
title: 'Procedura: configurare i servizi WCF per interagire con i client WSE 3.0'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: bd9f2bec94ca45f76590f64366428a00edd5d6ea
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141739"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Procedura: configurare i servizi WCF per interagire con i client WSE 3.0

I servizi Windows Communication Foundation (WCF) sono compatibili a livello di rete con i miglioramenti dei servizi Web 3,0 per i client di Microsoft .NET (WSE) quando i servizi WCF sono configurati per l'utilizzo della versione agosto 2004 della specifica WS-Addressing.

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Per consentire a un servizio WCF di interagire con i client WSE 3.0

1. Definire un'associazione personalizzata per il servizio WCF.

    Per specificare l'utilizzo della versione dell'agosto 2004 della specifica WS-Addressing per la codifica dei messaggi, è necessario creare un'associazione personalizzata.

    1. Aggiungere un elemento figlio [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) al [\<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del file di configurazione del servizio.

    2. Specificare un nome per l'associazione, aggiungendo un' [associazione\<](../../configure-apps/file-schema/wcf/bindings.md) al [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) e impostando l'attributo `name`.

    3. Specificare una modalità di autenticazione e la versione delle specifiche WS-Security utilizzate per proteggere i messaggi compatibili con WSE 3,0, aggiungendo una [> di sicurezza\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) figlio al [Binding\<](../../configure-apps/file-schema/wcf/bindings.md).

        Per impostare la modalità di autenticazione, impostare l'attributo `authenticationMode` del [> di sicurezza\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Una modalità di autenticazione è più o meno equivalente a un'asserzione di sicurezza turnkey in WSE 3.0. Nella tabella seguente viene eseguito il mapping delle modalità di autenticazione in WCF alle asserzioni di sicurezza chiavi in mano in WSE 3,0.

        |Modalità di autenticazione WCF|Asserzione di sicurezza turnkey WSE 3.0|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        \* una delle principali differenze tra le asserzioni di sicurezza `mutualCertificate10Security` e `mutualCertificate11Security` chiavi in mano è la versione della specifica WS-Security utilizzata da WSE per proteggere i messaggi SOAP. Per `mutualCertificate10Security` viene utilizzata la versione WS-Security 1.0, mentre per `mutualCertificate11Security` viene utilizzata la versione WS-Security 1.1. Per WCF, la versione della specifica WS-Security viene specificata nell'attributo `messageSecurityVersion` del [> di sicurezza\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).

        Per impostare la versione della specifica WS-Security utilizzata per proteggere i messaggi SOAP, impostare l'attributo `messageSecurityVersion` del [> di sicurezza\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Per interagire con WSE 3.0, impostare il valore dell'attributo `messageSecurityVersion` su <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.

    4. Specificare che la versione agosto 2004 della specifica WS-Addressing viene utilizzata da WCF aggiungendo un [\<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) e impostare il `messageVersion` sul relativo valore su <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.

        > [!NOTE]
        > Quando si utilizza SOAP 1.2, impostare l'attributo `messageVersion` su <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.

2. Specificare l'utilizzo dell'associazione personalizzata da parte del servizio.

    1. Impostare l'attributo `binding` dell'elemento [\<endpoint](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) su `customBinding`.

    2. Impostare l'attributo `bindingConfiguration` dell'elemento [\<endpoint](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) sul valore specificato nell'attributo `name` del [\<di associazione >](../../configure-apps/file-schema/wcf/bindings.md) per l'associazione personalizzata.

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

- [Procedura: Personalizzare un'associazione specificata dal sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
