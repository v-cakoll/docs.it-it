---
title: 'Procedura: configurare i servizi WCF per interagire con i client WSE 3.0'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 600b9c28d92f9e2b6e4d586b052cc5762d591521
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599061"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="d1032-102">Procedura: configurare i servizi WCF per interagire con i client WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d1032-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>

<span data-ttu-id="d1032-103">I servizi Windows Communication Foundation (WCF) sono compatibili a livello di rete con i miglioramenti dei servizi Web 3,0 per i client di Microsoft .NET (WSE) quando i servizi WCF sono configurati per l'utilizzo della versione agosto 2004 della specifica WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="d1032-103">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="d1032-104">Per consentire a un servizio WCF di interagire con i client WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d1032-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>

1. <span data-ttu-id="d1032-105">Definire un'associazione personalizzata per il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="d1032-105">Define a custom binding for the WCF service.</span></span>

    <span data-ttu-id="d1032-106">Per specificare l'utilizzo della versione dell'agosto 2004 della specifica WS-Addressing per la codifica dei messaggi, è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d1032-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>

    1. <span data-ttu-id="d1032-107">Aggiungere un elemento figlio [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) all'oggetto [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) del file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="d1032-107">Add a child [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>

    2. <span data-ttu-id="d1032-108">Specificare un nome per l'associazione, aggiungendo un oggetto [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) e impostando l' `name` attributo.</span><span class="sxs-lookup"><span data-stu-id="d1032-108">Specify a name for the binding, by adding a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>

    3. <span data-ttu-id="d1032-109">Specificare una modalità di autenticazione e la versione delle specifiche WS-Security utilizzate per proteggere i messaggi compatibili con WSE 3,0, aggiungendo un elemento figlio [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .</span><span class="sxs-lookup"><span data-stu-id="d1032-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md).</span></span>

        <span data-ttu-id="d1032-110">Per impostare la modalità di autenticazione, impostare l' `authenticationMode` attributo dell'oggetto [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d1032-110">To set the authentication mode, set the `authenticationMode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="d1032-111">Una modalità di autenticazione è più o meno equivalente a un'asserzione di sicurezza turnkey in WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="d1032-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="d1032-112">Nella tabella seguente viene eseguito il mapping delle modalità di autenticazione in WCF alle asserzioni di sicurezza chiavi in mano in WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="d1032-112">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>

        |<span data-ttu-id="d1032-113">Modalità di autenticazione WCF</span><span class="sxs-lookup"><span data-stu-id="d1032-113">WCF Authentication Mode</span></span>|<span data-ttu-id="d1032-114">Asserzione di sicurezza turnkey WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d1032-114">WSE 3.0 turnkey security assertion</span></span>|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        <span data-ttu-id="d1032-115">\*Una delle principali differenze tra le `mutualCertificate10Security` `mutualCertificate11Security` asserzioni di sicurezza di e chiavi in mano è la versione della specifica WS-Security utilizzata da WSE per proteggere i messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="d1032-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="d1032-116">Per `mutualCertificate10Security` viene utilizzata la versione WS-Security 1.0, mentre per `mutualCertificate11Security` viene utilizzata la versione WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="d1032-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="d1032-117">Per WCF, la versione della specifica WS-Security viene specificata nell' `messageSecurityVersion` attributo dell'oggetto [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d1032-117">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>

        <span data-ttu-id="d1032-118">Per impostare la versione della specifica WS-Security utilizzata per proteggere i messaggi SOAP, impostare l' `messageSecurityVersion` attributo dell'oggetto [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d1032-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="d1032-119">Per interagire con WSE 3.0, impostare il valore dell'attributo `messageSecurityVersion` su <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1032-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>

    4. <span data-ttu-id="d1032-120">Specificare che la versione agosto 2004 della specifica WS-Addressing viene utilizzata da WCF mediante l'aggiunta di un oggetto [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) e l'impostazione del `messageVersion` valore su <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> .</span><span class="sxs-lookup"><span data-stu-id="d1032-120">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d1032-121">Quando si utilizza SOAP 1.2, impostare l'attributo `messageVersion` su <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1032-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>

2. <span data-ttu-id="d1032-122">Specificare l'utilizzo dell'associazione personalizzata da parte del servizio.</span><span class="sxs-lookup"><span data-stu-id="d1032-122">Specify that the service uses the custom binding.</span></span>

    1. <span data-ttu-id="d1032-123">Impostare l' `binding` attributo dell' [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento su `customBinding` .</span><span class="sxs-lookup"><span data-stu-id="d1032-123">Set the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>

    2. <span data-ttu-id="d1032-124">Impostare l' `bindingConfiguration` attributo dell' [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento sul valore specificato nell' `name` attributo dell'oggetto [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d1032-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) for the custom binding.</span></span>

## <a name="example"></a><span data-ttu-id="d1032-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1032-125">Example</span></span>

<span data-ttu-id="d1032-126">Nell'esempio di codice seguente viene specificato che `Service.HelloWorldService` utilizza un'associazione personalizzata per interagire con i client WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="d1032-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="d1032-127">L'associazione personalizzata specifica che per la codifica dei messaggi scambiati viene utilizzata la versione dell'agosto 2004 del set di specifiche WS-Addressing e WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="d1032-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="d1032-128">I messaggi vengono protetti utilizzando la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.</span><span class="sxs-lookup"><span data-stu-id="d1032-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d1032-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1032-129">See also</span></span>

- [<span data-ttu-id="d1032-130">Procedura: Personalizzare un'associazione specificata dal sistema</span><span class="sxs-lookup"><span data-stu-id="d1032-130">How to: Customize a System-Provided Binding</span></span>](../extending/how-to-customize-a-system-provided-binding.md)
