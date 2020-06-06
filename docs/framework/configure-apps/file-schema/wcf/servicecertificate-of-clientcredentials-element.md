---
title: <serviceCertificate>dell' <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399677"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="b8ea8-102">\<serviceCertificate>dell' \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="b8ea8-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="b8ea8-103">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="b8ea8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8ea8-104">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8ea8-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b8ea8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b8ea8-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8ea8-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b8ea8-107">Attributes</span></span>  
 <span data-ttu-id="b8ea8-108">No.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8ea8-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b8ea8-109">Child Elements</span></span>  
  
|<span data-ttu-id="b8ea8-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8ea8-110">Element</span></span>|<span data-ttu-id="b8ea8-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8ea8-111">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="b8ea8-112">Specifica un certificato X.509 da usare quando un servizio o STS non ne fornisce uno tramite un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-112">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="b8ea8-113">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-113">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="b8ea8-114">Questa raccolta è usata in genere per specificare i certificati di servizio per i servizi dei token di sicurezza in un scenario federato.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-114">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="b8ea8-115">Specifica i comportamenti di autenticazione per i certificati di servizio usati da un client.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-115">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8ea8-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b8ea8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b8ea8-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8ea8-117">Element</span></span>|<span data-ttu-id="b8ea8-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8ea8-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="b8ea8-119">Specifica le credenziali usate per autenticare il client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-119">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8ea8-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="b8ea8-120">Remarks</span></span>  
 <span data-ttu-id="b8ea8-121">Questo elemento di configurazione specifica le impostazioni usate dal client per convalidare il certificato presentato dal servizio usando l'autenticazione SSL.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-121">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="b8ea8-122">Contiene inoltre i certificati usati dal servizio configurato in modo esplicito nel client per crittografare i messaggi al servizio usando la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b8ea8-122">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="b8ea8-123">Gli attributi dell' `serviceCertificate` elemento sono identici agli attributi di [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="b8ea8-123">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ea8-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b8ea8-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="b8ea8-125">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b8ea8-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b8ea8-126">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="b8ea8-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="b8ea8-127">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="b8ea8-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b8ea8-128">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="b8ea8-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
