---
title: 'Procedura: Configurare servizi WCF per interagire con client WSE 3.0'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 0349c9ba76b3f240bf98daa0e095b415bc98a87c
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045943"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Procedura: Configurare servizi WCF per interagire con client WSE 3.0

I servizi Windows Communication Foundation (WCF) sono compatibili a livello di rete con i miglioramenti dei servizi Web 3,0 per i client di Microsoft .NET (WSE) quando i servizi WCF sono configurati per l'utilizzo della versione agosto 2004 della specifica WS-Addressing.

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Per consentire a un servizio WCF di interagire con i client WSE 3.0

1. Definire un'associazione personalizzata per il servizio WCF.

    Per specificare l'utilizzo della versione dell'agosto 2004 della specifica WS-Addressing per la codifica dei messaggi, è necessario creare un'associazione personalizzata.

    1. Aggiungere un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) [ >CustomBindingfiglioalleassociazioni>delfilediconfigurazionedelservizio.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)

    2. Specificare un nome per l'associazione, aggiungendo un `name` [ \<binding](../../../../docs/framework/misc/binding.md) [ \<> al > CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) e impostando l'attributo.

    3. Specificare una modalità di autenticazione e la versione delle specifiche WS-Security utilizzate per proteggere i messaggi compatibili con WSE 3,0, aggiungendo un [ \<](../../../../docs/framework/misc/binding.md) [ \<> di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) figlio al > di associazione.

        Per impostare la modalità `authenticationMode` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)di autenticazione, impostare l'attributo del > di sicurezza. Una modalità di autenticazione è più o meno equivalente a un'asserzione di sicurezza turnkey in WSE 3.0. Nella tabella seguente viene eseguito il mapping delle modalità di autenticazione in WCF alle asserzioni di sicurezza chiavi in mano in WSE 3,0.

        |Modalità di autenticazione WCF|Asserzione di sicurezza turnkey WSE 3.0|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        \*Una delle principali differenze tra le `mutualCertificate10Security` asserzioni di sicurezza di e `mutualCertificate11Security` chiavi in mano è la versione della specifica WS-Security utilizzata da WSE per proteggere i messaggi SOAP. Per `mutualCertificate10Security` viene utilizzata la versione WS-Security 1.0, mentre per `mutualCertificate11Security` viene utilizzata la versione WS-Security 1.1. Per WCF, la versione della specifica WS-Security viene specificata nell' `messageSecurityVersion` attributo [ \<della > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).

        Per impostare la versione della specifica WS-Security utilizzata per proteggere i messaggi SOAP, impostare l' `messageSecurityVersion` attributo [ \<del > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Per interagire con WSE 3.0, impostare il valore dell'attributo `messageSecurityVersion` su <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.

    4. Specificare che la versione agosto 2004 della specifica WS-Addressing viene utilizzata da WCF mediante l'aggiunta di un [ \<> textMessageEncoding](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) e l'impostazione del <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> `messageVersion` valore su.

        > [!NOTE]
        > Quando si utilizza SOAP 1.2, impostare l'attributo `messageVersion` su <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.

2. Specificare l'utilizzo dell'associazione personalizzata da parte del servizio.

    1. Impostare l' `binding` attributo `customBinding` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) dell'elemento > dell'endpoint su.

    2. Impostare l' `bindingConfiguration` attributo dell'`name`elemento > dell' [ endpointsulvalorespecificatonell'attributodell'associazione>perl'associazionepersonalizzata.\<](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) [ \<](../../../../docs/framework/misc/binding.md)

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
