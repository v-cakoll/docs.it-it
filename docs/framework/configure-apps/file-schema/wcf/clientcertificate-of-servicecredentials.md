---
title: <clientCertificate> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: a8a78bbfcd9dfbf6975503a845d5bb4e2d24b13d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398130"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="2f6f2-102">\<clientCertificate> di \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="2f6f2-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="2f6f2-103">Definisce un certificato X.509 usato per firmare e crittografare i messaggi da un client a un servizio in un modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="2f6f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f6f2-104">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f6f2-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2f6f2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2f6f2-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f6f2-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f6f2-107">Attributes</span></span>  
 <span data-ttu-id="2f6f2-108">No.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f6f2-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2f6f2-109">Child Elements</span></span>  
  
|<span data-ttu-id="2f6f2-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f6f2-110">Element</span></span>|<span data-ttu-id="2f6f2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f6f2-111">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="2f6f2-112">Specifica le opzioni di autenticazione del certificato client.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-112">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="2f6f2-113">Specifica il certificato da usare.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-113">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f6f2-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2f6f2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="2f6f2-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f6f2-115">Element</span></span>|<span data-ttu-id="2f6f2-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f6f2-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="2f6f2-117">Specifica le credenziali da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-117">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f6f2-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="2f6f2-118">Remarks</span></span>  
 <span data-ttu-id="2f6f2-119">Questo elemento viene usato quando il servizio deve disporre in anticipo del certificato del client per poter comunicare in modo sicuro con il client.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-119">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="2f6f2-120">Questa esigenza si presenta quando si usa il modello di comunicazione duplex.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-120">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="2f6f2-121">Nel modello più comune di comunicazione richiesta/risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per crittografare e firmare la risposta che invia al client.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-121">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="2f6f2-122">Nel modello di comunicazione duplex, tuttavia, il servizio non riceve alcuna richiesta dal client e pertanto deve disporre in anticipo del certificato del client per proteggere il messaggio da inviare al client.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-122">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="2f6f2-123">Questo certificato deve quindi essere ottenuto mediante una negoziazione fuori banda e deve essere specificato tramite questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-123">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="2f6f2-124">Per ulteriori informazioni sui servizi duplex, vedere [procedura: creare un contratto duplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="2f6f2-124">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="2f6f2-125">Il certificato impostato in questo elemento viene usato per crittografare i messaggi indirizzati al client solo per le associazioni configurate con la modalità di autenticazione di sicurezza dei messaggi `MutualCertificateDuplex`.</span><span class="sxs-lookup"><span data-stu-id="2f6f2-125">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6f2-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2f6f2-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="2f6f2-127">Procedura: creare un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="2f6f2-127">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="2f6f2-128">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f6f2-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2f6f2-129">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="2f6f2-129">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
