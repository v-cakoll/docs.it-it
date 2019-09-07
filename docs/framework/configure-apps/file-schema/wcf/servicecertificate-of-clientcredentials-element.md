---
title: <serviceCertificate>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399677"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="9090f-102">\<ServiceCertificate > dell' \<elemento ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="9090f-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="9090f-103">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="9090f-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
<span data-ttu-id="9090f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9090f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9090f-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9090f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9090f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9090f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9090f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9090f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="9090f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9090f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="9090f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="9090f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="9090f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceCertificate**</span><span class="sxs-lookup"><span data-stu-id="9090f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9090f-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9090f-111">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9090f-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9090f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9090f-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9090f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9090f-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="9090f-114">Attributes</span></span>  
 <span data-ttu-id="9090f-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9090f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9090f-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9090f-116">Child Elements</span></span>  
  
|<span data-ttu-id="9090f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9090f-117">Element</span></span>|<span data-ttu-id="9090f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9090f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9090f-119">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="9090f-119">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="9090f-120">Specifica un certificato X.509 da usare quando un servizio o STS non ne fornisce uno tramite un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="9090f-120">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="9090f-121">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="9090f-121">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="9090f-122">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="9090f-122">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="9090f-123">Questa raccolta è usata in genere per specificare i certificati di servizio per i servizi dei token di sicurezza in un scenario federato.</span><span class="sxs-lookup"><span data-stu-id="9090f-123">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="9090f-124">\<authentication></span><span class="sxs-lookup"><span data-stu-id="9090f-124">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="9090f-125">Specifica i comportamenti di autenticazione per i certificati di servizio usati da un client.</span><span class="sxs-lookup"><span data-stu-id="9090f-125">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9090f-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9090f-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9090f-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="9090f-127">Element</span></span>|<span data-ttu-id="9090f-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9090f-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9090f-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9090f-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="9090f-130">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="9090f-130">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9090f-131">Note</span><span class="sxs-lookup"><span data-stu-id="9090f-131">Remarks</span></span>  
 <span data-ttu-id="9090f-132">Questo elemento di configurazione specifica le impostazioni usate dal client per convalidare il certificato presentato dal servizio usando l'autenticazione SSL.</span><span class="sxs-lookup"><span data-stu-id="9090f-132">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="9090f-133">Contiene inoltre i certificati usati dal servizio configurato in modo esplicito nel client per crittografare i messaggi al servizio usando la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9090f-133">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="9090f-134">Gli attributi dell' `serviceCertificate` elemento sono identici a quelli [ \<del > ClientCertificate](clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="9090f-134">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9090f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9090f-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="9090f-136">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9090f-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9090f-137">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="9090f-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="9090f-138">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="9090f-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9090f-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9090f-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
