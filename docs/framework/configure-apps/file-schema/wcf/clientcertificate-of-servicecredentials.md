---
title: '&lt;clientCertificate&gt; di &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc2dfd94ffbf8ce08dee9c14421f389861e99e77
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="bfe00-102">&lt;clientCertificate&gt; di &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="bfe00-102">&lt;clientCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="bfe00-103">Definisce un certificato X.509 usato per firmare e crittografare i messaggi da un client a un servizio in un modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="bfe00-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="bfe00-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bfe00-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bfe00-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="bfe00-105">\<behaviors></span></span>  
<span data-ttu-id="bfe00-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bfe00-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bfe00-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bfe00-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="bfe00-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="bfe00-108">\<behavior></span></span>  
<span data-ttu-id="bfe00-109">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="bfe00-109">\<serviceCredentials></span></span>  
<span data-ttu-id="bfe00-110">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="bfe00-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe00-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfe00-111">Syntax</span></span>  
  
```xml  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfe00-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bfe00-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bfe00-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bfe00-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfe00-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="bfe00-114">Attributes</span></span>  
 <span data-ttu-id="bfe00-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bfe00-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bfe00-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bfe00-116">Child Elements</span></span>  
  
|<span data-ttu-id="bfe00-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfe00-117">Element</span></span>|<span data-ttu-id="bfe00-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfe00-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfe00-119">\<autenticazione ></span><span class="sxs-lookup"><span data-stu-id="bfe00-119">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|<span data-ttu-id="bfe00-120">Specifica le opzioni di autenticazione del certificato client.</span><span class="sxs-lookup"><span data-stu-id="bfe00-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="bfe00-121">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="bfe00-121">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|<span data-ttu-id="bfe00-122">Specifica il certificato da usare.</span><span class="sxs-lookup"><span data-stu-id="bfe00-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bfe00-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bfe00-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bfe00-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfe00-124">Element</span></span>|<span data-ttu-id="bfe00-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfe00-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfe00-126">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="bfe00-126">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="bfe00-127">Specifica le credenziali da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="bfe00-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfe00-128">Note</span><span class="sxs-lookup"><span data-stu-id="bfe00-128">Remarks</span></span>  
 <span data-ttu-id="bfe00-129">Questo elemento viene usato quando il servizio deve disporre in anticipo del certificato del client per poter comunicare in modo sicuro con il client.</span><span class="sxs-lookup"><span data-stu-id="bfe00-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="bfe00-130">Questa esigenza si presenta quando si usa il modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="bfe00-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="bfe00-131">Nel modello più comune di comunicazione richiesta/risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per crittografare e firmare la risposta che invia al client.</span><span class="sxs-lookup"><span data-stu-id="bfe00-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="bfe00-132">Nel modello di comunicazione duplex, tuttavia, il servizio non riceve alcuna richiesta dal client e pertanto deve disporre in anticipo del certificato del client per proteggere il messaggio da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="bfe00-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="bfe00-133">Questo certificato deve quindi essere ottenuto mediante una negoziazione fuori banda e deve essere specificato tramite questo elemento.</span><span class="sxs-lookup"><span data-stu-id="bfe00-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="bfe00-134">Per ulteriori informazioni sui servizi duplex, vedere [procedura: creare un contratto Duplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="bfe00-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="bfe00-135">Il certificato impostato in questo elemento viene usato per crittografare i messaggi indirizzati al client solo per le associazioni configurate con la modalità di autenticazione di sicurezza dei messaggi `MutualCertificateDuplex`.</span><span class="sxs-lookup"><span data-stu-id="bfe00-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe00-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe00-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [<span data-ttu-id="bfe00-137">Procedura: creare un contratto Duplex</span><span class="sxs-lookup"><span data-stu-id="bfe00-137">How to: Create a Duplex Contract</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="bfe00-138">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="bfe00-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="bfe00-139">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="bfe00-139">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
