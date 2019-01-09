---
title: Elemento &lt;serviceCertificate&gt; di &lt;clientCredentials&gt;
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 82fb39f15ea0dbf38d9c9b41d7fbdd50daebb823
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151982"
---
# <a name="ltservicecertificategt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="45e19-102">Elemento &lt;serviceCertificate&gt; di &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="45e19-102">&lt;serviceCertificate&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="45e19-103">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="45e19-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="45e19-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="45e19-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="45e19-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="45e19-105">\<behaviors></span></span>  
<span data-ttu-id="45e19-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="45e19-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="45e19-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="45e19-107">\<behavior></span></span>  
<span data-ttu-id="45e19-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="45e19-108">\<clientCredentials></span></span>  
<span data-ttu-id="45e19-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="45e19-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e19-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45e19-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45e19-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="45e19-111">Attributes and Elements</span></span>  
 <span data-ttu-id="45e19-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="45e19-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45e19-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="45e19-113">Attributes</span></span>  
 <span data-ttu-id="45e19-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="45e19-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="45e19-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="45e19-115">Child Elements</span></span>  
  
|<span data-ttu-id="45e19-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="45e19-116">Element</span></span>|<span data-ttu-id="45e19-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45e19-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45e19-118">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="45e19-118">\<defaultCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|<span data-ttu-id="45e19-119">Specifica un certificato X.509 da usare quando un servizio o STS non ne fornisce uno tramite un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="45e19-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="45e19-120">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="45e19-120">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="45e19-121">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="45e19-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="45e19-122">Questa raccolta è usata in genere per specificare i certificati di servizio per i servizi dei token di sicurezza in un scenario federato.</span><span class="sxs-lookup"><span data-stu-id="45e19-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="45e19-123">\<authentication></span><span class="sxs-lookup"><span data-stu-id="45e19-123">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|<span data-ttu-id="45e19-124">Specifica i comportamenti di autenticazione per i certificati di servizio usati da un client.</span><span class="sxs-lookup"><span data-stu-id="45e19-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45e19-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="45e19-125">Parent Elements</span></span>  
  
|<span data-ttu-id="45e19-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="45e19-126">Element</span></span>|<span data-ttu-id="45e19-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45e19-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45e19-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="45e19-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="45e19-129">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="45e19-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45e19-130">Note</span><span class="sxs-lookup"><span data-stu-id="45e19-130">Remarks</span></span>  
 <span data-ttu-id="45e19-131">Questo elemento di configurazione specifica le impostazioni usate dal client per convalidare il certificato presentato dal servizio usando l'autenticazione SSL.</span><span class="sxs-lookup"><span data-stu-id="45e19-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="45e19-132">Contiene inoltre i certificati usati dal servizio configurato in modo esplicito nel client per crittografare i messaggi al servizio usando la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="45e19-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="45e19-133">Gli attributi del `serviceCertificate` sono identici agli attributi dell'elemento di [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="45e19-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e19-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45e19-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 [<span data-ttu-id="45e19-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="45e19-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="45e19-136">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="45e19-136">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="45e19-137">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="45e19-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="45e19-138">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="45e19-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
