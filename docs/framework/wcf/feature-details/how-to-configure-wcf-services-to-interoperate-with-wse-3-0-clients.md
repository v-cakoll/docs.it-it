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
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="3bcb1-102">Procedura: configurare i servizi WCF per interagire con i client WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="3bcb1-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
<span data-ttu-id="3bcb1-103">I servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sono compatibili a livello di rete con i client Web Services Enhancements 3.0 for Microsoft .NET (WSE) se tali servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono configurati per utilizzare la versione dell'agosto 2004 della specifica WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="3bcb1-104">Per consentire a un servizio WCF di interagire con i client WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="3bcb1-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1.  <span data-ttu-id="3bcb1-105">Definire un'associazione personalizzata per il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bcb1-105">Define a custom binding for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
     <span data-ttu-id="3bcb1-106">Per specificare l'utilizzo della versione dell'agosto 2004 della specifica WS-Addressing per la codifica dei messaggi, è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1.  <span data-ttu-id="3bcb1-107">Aggiungere un elemento figlio [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) per il [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2.  <span data-ttu-id="3bcb1-108">Specificare un nome per l'associazione, aggiungendo un [ \<associazione >](../../../../docs/framework/misc/binding.md) per il [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) e impostando il `name` attributo.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3.  <span data-ttu-id="3bcb1-109">Specificare una modalità di autenticazione e la versione delle specifiche WS-Security che vengono utilizzati per proteggere i messaggi che sono compatibili con WSE 3.0, aggiungendo un elemento figlio [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) per il [ \<associazione >](../../../../docs/framework/misc/binding.md).</span><span class="sxs-lookup"><span data-stu-id="3bcb1-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="3bcb1-110">Per impostare la modalità di autenticazione, impostare il `authenicationMode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="3bcb1-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="3bcb1-111">Una modalità di autenticazione è più o meno equivalente a un'asserzione di sicurezza turnkey in WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="3bcb1-112">Nella tabella che segue viene illustrato il mapping delle modalità di autenticazione in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alle asserzioni di sicurezza turnkey in WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-112">The following table maps authentication modes in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="3bcb1-113">Modalità di autenticazione WCF</span><span class="sxs-lookup"><span data-stu-id="3bcb1-113">WCF Authentication Mode</span></span>|<span data-ttu-id="3bcb1-114">Asserzione di sicurezza turnkey WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="3bcb1-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="3bcb1-115">\*Una delle principali differenze tra il `mutualCertificate10Security` e `mutualCertificate11Security` asserzioni di sicurezza turnkey è la versione della specifica WS-Security utilizzata da WSE per proteggere i messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="3bcb1-116">Per `mutualCertificate10Security` viene utilizzata la versione WS-Security 1.0, mentre per `mutualCertificate11Security` viene utilizzata la versione WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="3bcb1-117">Per [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], la versione della specifica WS-Security è specificata nel `messageSecurityVersion` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="3bcb1-117">For [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="3bcb1-118">Per impostare la versione della specifica WS-Security che viene utilizzata per proteggere i messaggi SOAP, impostare il `messageSecurityVersion` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="3bcb1-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="3bcb1-119">Per interagire con WSE 3.0, impostare il valore dell'attributo `messageSecurityVersion` su <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4.  <span data-ttu-id="3bcb1-120">Specificare che la versione di agosto 2004 della specifica WS-Addressing è utilizzata da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aggiungendo un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) e impostare il `messageVersion` al valore di <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-120">Specify that the August 2004 version of the WS-Addressing specification is used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3bcb1-121">Quando si utilizza SOAP 1.2, impostare l'attributo `messageVersion` su <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2.  <span data-ttu-id="3bcb1-122">Specificare l'utilizzo dell'associazione personalizzata da parte del servizio.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-122">Specify that the service uses the custom binding.</span></span>  
  
    1.  <span data-ttu-id="3bcb1-123">Impostare il `binding` attributo del [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento `customBinding`.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2.  <span data-ttu-id="3bcb1-124">Impostare il `bindingConfiguration` attributo del [ \<endpoint >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento sul valore specificato nella `name` attributo del [ \<associazione >](../../../../docs/framework/misc/binding.md) personalizzata associazione.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bcb1-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="3bcb1-125">Example</span></span>  
 <span data-ttu-id="3bcb1-126">Nell'esempio di codice seguente viene specificato che `Service.HelloWorldService` utilizza un'associazione personalizzata per interagire con i client WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="3bcb1-127">L'associazione personalizzata specifica che per la codifica dei messaggi scambiati viene utilizzata la versione dell'agosto 2004 del set di specifiche WS-Addressing e WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="3bcb1-128">I messaggi vengono protetti utilizzando la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.</span><span class="sxs-lookup"><span data-stu-id="3bcb1-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3bcb1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bcb1-129">See Also</span></span>  
 [<span data-ttu-id="3bcb1-130">Procedura: Personalizzare un'associazione specificata dal sistema</span><span class="sxs-lookup"><span data-stu-id="3bcb1-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
