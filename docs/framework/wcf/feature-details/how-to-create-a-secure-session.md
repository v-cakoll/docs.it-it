---
title: 'Procedura: Creare una sessione protetta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: bdb0f89b950d086e04cbb9d6da161bd315fc64b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934376"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="9db0e-102">Procedura: Creare una sessione protetta</span><span class="sxs-lookup"><span data-stu-id="9db0e-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="9db0e-103">Fatta eccezione per l' [ \<associazione > BasicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) , le associazioni fornite dal sistema in Windows Communication Foundation (WCF) utilizzano automaticamente le sessioni protette quando è abilitata la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9db0e-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="9db0e-104">Per impostazione predefinita, le sessioni protette non restano attive quando un server Web viene riciclato.</span><span class="sxs-lookup"><span data-stu-id="9db0e-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="9db0e-105">Quando si stabilisce una sessione protetta, il client e il servizio memorizzano nella cache la chiave associata alla sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="9db0e-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="9db0e-106">Durante lo scambio dei messaggi, viene scambiato solo un identificatore della chiave memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="9db0e-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="9db0e-107">Se il server Web viene riciclato, anche la cache viene riciclata, pertanto il server Web non può recuperare la chiave memorizzata nella cache per l'identificatore.</span><span class="sxs-lookup"><span data-stu-id="9db0e-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="9db0e-108">In questo caso, al client viene restituita un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9db0e-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="9db0e-109">Le sessioni protette che usano un token del contesto di sicurezza (SCT) con stato possono restare attive quando un server Web viene riciclato.</span><span class="sxs-lookup"><span data-stu-id="9db0e-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="9db0e-110">Per ulteriori informazioni sull'utilizzo di un token SCT con stato in una sessione protetta [, vedere Procedura: Creare un token del contesto di sicurezza per una](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="9db0e-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="9db0e-111">Per specificare che un servizio usa sessioni protette mediante una delle associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9db0e-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
- <span data-ttu-id="9db0e-112">Configurare un servizio per l'uso di un'associazione fornita dal sistema che supporta la protezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9db0e-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="9db0e-113">Ad eccezione dell'associazione [ \<> BasicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) , quando le associazioni fornite dal sistema sono configurate per l'utilizzo della sicurezza dei messaggi, WCF utilizza automaticamente le sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="9db0e-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="9db0e-114">Nella tabella seguente vengono elencate le associazioni fornite dal sistema che supportano la protezione dei messaggi e viene indicato se la protezione del messaggio è il meccanismo di sicurezza predefinito.</span><span class="sxs-lookup"><span data-stu-id="9db0e-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="9db0e-115">Associazione fornita dal sistema</span><span class="sxs-lookup"><span data-stu-id="9db0e-115">System-provided binding</span></span>|<span data-ttu-id="9db0e-116">Elemento Configuration</span><span class="sxs-lookup"><span data-stu-id="9db0e-116">Configuration element</span></span>|<span data-ttu-id="9db0e-117">Sicurezza dei messaggi attivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="9db0e-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="9db0e-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9db0e-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="9db0e-119">No</span><span class="sxs-lookup"><span data-stu-id="9db0e-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="9db0e-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9db0e-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="9db0e-121">Sì</span><span class="sxs-lookup"><span data-stu-id="9db0e-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="9db0e-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9db0e-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="9db0e-123">Sì</span><span class="sxs-lookup"><span data-stu-id="9db0e-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="9db0e-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9db0e-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="9db0e-125">Sì</span><span class="sxs-lookup"><span data-stu-id="9db0e-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="9db0e-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="9db0e-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="9db0e-127">No</span><span class="sxs-lookup"><span data-stu-id="9db0e-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="9db0e-128">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="9db0e-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="9db0e-129">No</span><span class="sxs-lookup"><span data-stu-id="9db0e-129">No</span></span>|  
  
     <span data-ttu-id="9db0e-130">Nell'esempio di codice seguente viene utilizzata la configurazione per specificare `wsHttpBinding_Calculator` un'associazione denominata che utilizza il [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), la sicurezza dei messaggi e le sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="9db0e-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
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
  
     <span data-ttu-id="9db0e-131">Nell'esempio di codice seguente viene specificato che la [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), la sicurezza dei messaggi e le sessioni protette vengono utilizzate `secureCalculator` per proteggere il servizio.</span><span class="sxs-lookup"><span data-stu-id="9db0e-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > <span data-ttu-id="9db0e-132">Le sessioni protette possono essere disattivate per il [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) impostando `establishSecurityContext` l'attributo `false`su.</span><span class="sxs-lookup"><span data-stu-id="9db0e-132">Secure sessions can be turned off for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="9db0e-133">Per le altre associazioni fornite dal sistema, è possibile disattivare le sessioni protette solo creando un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9db0e-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="9db0e-134">Per specificare che un servizio usa sessioni protette mediante un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="9db0e-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
- <span data-ttu-id="9db0e-135">Creare un'associazione personalizzata che specifica che i messaggi SOAP sono protetti mediante una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="9db0e-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="9db0e-136">Per ulteriori informazioni sulla creazione di un'associazione personalizzata, [vedere Procedura: Personalizzare un'associazione](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="9db0e-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="9db0e-137">Nell'esempio di codice seguente viene usata la configurazione per specificare un'associazione personalizzata che protegge i messaggi mediante una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="9db0e-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
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
  
     <span data-ttu-id="9db0e-138">Nell'esempio di codice seguente viene creata un'associazione personalizzata che usa la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> per l'avvio automatico di una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="9db0e-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9db0e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9db0e-139">See also</span></span>

- [<span data-ttu-id="9db0e-140">Panoramica delle associazioni WCF</span><span class="sxs-lookup"><span data-stu-id="9db0e-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
