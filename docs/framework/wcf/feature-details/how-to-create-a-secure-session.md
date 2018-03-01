---
title: 'Procedura: creare una sessione protetta'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: cd4f91ef5389dd4b8ecb63c1148d3a86918f2d10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="81564-102">Procedura: creare una sessione protetta</span><span class="sxs-lookup"><span data-stu-id="81564-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="81564-103">Ad eccezione del [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) l'associazione, le associazioni fornite dal sistema in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Usa sessioni protette quando è abilitata la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="81564-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="81564-104">Per impostazione predefinita, le sessioni protette non restano attive quando un server Web viene riciclato.</span><span class="sxs-lookup"><span data-stu-id="81564-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="81564-105">Quando si stabilisce una sessione protetta, il client e il servizio memorizzano nella cache la chiave associata alla sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="81564-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="81564-106">Durante lo scambio dei messaggi, viene scambiato solo un identificatore della chiave memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="81564-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="81564-107">Se il server Web viene riciclato, anche la cache viene riciclata, pertanto il server Web non può recuperare la chiave memorizzata nella cache per l'identificatore.</span><span class="sxs-lookup"><span data-stu-id="81564-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="81564-108">In questo caso, al client viene restituita un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="81564-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="81564-109">Le sessioni protette che usano un token del contesto di sicurezza (SCT) con stato possono restare attive quando un server Web viene riciclato.</span><span class="sxs-lookup"><span data-stu-id="81564-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="81564-110">uso di un token SCT con stato in una sessione protetta, vedere [procedura: creare un Token di contesto di sicurezza per una sessione protetta](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="81564-110"> using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="81564-111">Per specificare che un servizio usa sessioni protette mediante una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="81564-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="81564-112">Configurare un servizio per l'uso di un'associazione fornita dal sistema che supporta la protezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="81564-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="81564-113">Ad eccezione del [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, quando le associazioni fornite dal sistema sono configurate per utilizzare la sicurezza dei messaggi, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automaticamente Usa sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="81564-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically uses secure sessions.</span></span> <span data-ttu-id="81564-114">Nella tabella seguente vengono elencate le associazioni fornite dal sistema che supportano la protezione dei messaggi e viene indicato se la protezione del messaggio è il meccanismo di sicurezza predefinito.</span><span class="sxs-lookup"><span data-stu-id="81564-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="81564-115">Binding fornito dal sistema</span><span class="sxs-lookup"><span data-stu-id="81564-115">System-provided binding</span></span>|<span data-ttu-id="81564-116">Elemento Configuration</span><span class="sxs-lookup"><span data-stu-id="81564-116">Configuration element</span></span>|<span data-ttu-id="81564-117">Sicurezza dei messaggi attivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="81564-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="81564-118">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="81564-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="81564-119">No</span><span class="sxs-lookup"><span data-stu-id="81564-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="81564-120">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="81564-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="81564-121">Yes</span><span class="sxs-lookup"><span data-stu-id="81564-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="81564-122">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="81564-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="81564-123">Yes</span><span class="sxs-lookup"><span data-stu-id="81564-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="81564-124">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="81564-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="81564-125">Yes</span><span class="sxs-lookup"><span data-stu-id="81564-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="81564-126">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="81564-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="81564-127">No</span><span class="sxs-lookup"><span data-stu-id="81564-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="81564-128">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="81564-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="81564-129">No</span><span class="sxs-lookup"><span data-stu-id="81564-129">No</span></span>|  
  
     <span data-ttu-id="81564-130">Esempio di codice seguente utilizza la configurazione per specificare un'associazione denominata `wsHttpBinding_Calculator` che utilizza il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), protezione dei messaggi e proteggere le sessioni.</span><span class="sxs-lookup"><span data-stu-id="81564-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="81564-131">Esempio di codice seguente specifica che il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), protezione dei messaggi e proteggere le sessioni vengono utilizzate per proteggere il `secureCalculator` servizio.</span><span class="sxs-lookup"><span data-stu-id="81564-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="81564-132">Possano disattivare le sessioni protette per la [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) impostando il `establishSecurityContext` attributo `false`.</span><span class="sxs-lookup"><span data-stu-id="81564-132">Secure sessions can be turned off for the [<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="81564-133">Per le altre associazioni fornite dal sistema, è possibile disattivare le sessioni protette solo creando un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="81564-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="81564-134">Per specificare che un servizio usa sessioni protette mediante un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="81564-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="81564-135">Creare un'associazione personalizzata che specifica che i messaggi SOAP sono protetti mediante una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="81564-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="81564-136">creazione di un'associazione personalizzata, vedere [procedura: personalizzare un'associazione fornite dal sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="81564-136"> creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="81564-137">Nell'esempio di codice seguente viene usata la configurazione per specificare un'associazione personalizzata che protegge i messaggi mediante una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="81564-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="81564-138">Nell'esempio di codice seguente viene creata un'associazione personalizzata che usa la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> per l'avvio automatico di una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="81564-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="81564-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81564-139">See Also</span></span>  
 [<span data-ttu-id="81564-140">Panoramica delle associazioni WCF</span><span class="sxs-lookup"><span data-stu-id="81564-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
