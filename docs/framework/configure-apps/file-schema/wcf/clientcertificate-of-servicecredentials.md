---
title: <clientCertificate> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 277e5e33bcc7f9d417da7ce24caa4c6200c23e23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919543"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="bb1cb-102">\<ClientCertificate > di \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="bb1cb-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="bb1cb-103">Definisce un certificato X.509 usato per firmare e crittografare i messaggi da un client a un servizio in un modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="bb1cb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bb1cb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bb1cb-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="bb1cb-105">\<behaviors></span></span>  
<span data-ttu-id="bb1cb-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bb1cb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bb1cb-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bb1cb-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="bb1cb-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="bb1cb-108">\<behavior></span></span>  
<span data-ttu-id="bb1cb-109">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="bb1cb-109">\<serviceCredentials></span></span>  
<span data-ttu-id="bb1cb-110">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="bb1cb-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb1cb-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb1cb-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb1cb-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bb1cb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bb1cb-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb1cb-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="bb1cb-114">Attributes</span></span>  
 <span data-ttu-id="bb1cb-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb1cb-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bb1cb-116">Child Elements</span></span>  
  
|<span data-ttu-id="bb1cb-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb1cb-117">Element</span></span>|<span data-ttu-id="bb1cb-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb1cb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb1cb-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="bb1cb-119">\<authentication></span></span>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="bb1cb-120">Specifica le opzioni di autenticazione del certificato client.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="bb1cb-121">\<> certificato</span><span class="sxs-lookup"><span data-stu-id="bb1cb-121">\<certificate></span></span>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="bb1cb-122">Specifica il certificato da usare.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb1cb-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bb1cb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bb1cb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb1cb-124">Element</span></span>|<span data-ttu-id="bb1cb-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb1cb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb1cb-126">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="bb1cb-126">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="bb1cb-127">Specifica le credenziali da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb1cb-128">Note</span><span class="sxs-lookup"><span data-stu-id="bb1cb-128">Remarks</span></span>  
 <span data-ttu-id="bb1cb-129">Questo elemento viene usato quando il servizio deve disporre in anticipo del certificato del client per poter comunicare in modo sicuro con il client.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="bb1cb-130">Questa esigenza si presenta quando si usa il modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="bb1cb-131">Nel modello più comune di comunicazione richiesta/risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per crittografare e firmare la risposta che invia al client.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="bb1cb-132">Nel modello di comunicazione duplex, tuttavia, il servizio non riceve alcuna richiesta dal client e pertanto deve disporre in anticipo del certificato del client per proteggere il messaggio da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="bb1cb-133">Questo certificato deve quindi essere ottenuto mediante una negoziazione fuori banda e deve essere specificato tramite questo elemento.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="bb1cb-134">Per ulteriori informazioni sui servizi duplex, vedere [procedura: Creazione di un contratto](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)duplex.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="bb1cb-135">Il certificato impostato in questo elemento viene usato per crittografare i messaggi indirizzati al client solo per le associazioni configurate con la modalità di autenticazione di sicurezza dei messaggi `MutualCertificateDuplex`.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1cb-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb1cb-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="bb1cb-137">Procedura: Creazione di un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="bb1cb-137">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="bb1cb-138">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="bb1cb-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="bb1cb-139">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="bb1cb-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
