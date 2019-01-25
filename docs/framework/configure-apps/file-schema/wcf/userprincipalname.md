---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 8ba961e060e12801395a0ad0bd02aebda35655c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656557"
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="69d59-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="69d59-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="69d59-103">Specifica il nome principale dell'utente (UPN, User Principal Name) di un servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="69d59-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="69d59-104">Per altre informazioni sull'impostazione del nome UPN, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="69d59-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="69d59-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="69d59-105">\<identity></span></span>  
<span data-ttu-id="69d59-106">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="69d59-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69d59-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69d59-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69d59-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="69d59-108">Attributes and Elements</span></span>  
 <span data-ttu-id="69d59-109">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="69d59-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69d59-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="69d59-110">Attributes</span></span>  
  
|<span data-ttu-id="69d59-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="69d59-111">Attribute</span></span>|<span data-ttu-id="69d59-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69d59-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69d59-113">predefinito</span><span class="sxs-lookup"><span data-stu-id="69d59-113">value</span></span>|<span data-ttu-id="69d59-114">Nome costituito dal nome dell'account utente (talvolta detto nome di accesso utente) e dal nome del dominio in cui tale account si trova.</span><span class="sxs-lookup"><span data-stu-id="69d59-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="69d59-115">Questo nome rappresenta il formato standard dei nomi di accesso a un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="69d59-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="69d59-116">Il formato è: someone@example.com (per un indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="69d59-116">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69d59-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="69d59-117">Child Elements</span></span>  
 <span data-ttu-id="69d59-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="69d59-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69d59-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="69d59-119">Parent Elements</span></span>  
  
|<span data-ttu-id="69d59-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="69d59-120">Element</span></span>|<span data-ttu-id="69d59-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69d59-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69d59-122">\<identity></span><span class="sxs-lookup"><span data-stu-id="69d59-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="69d59-123">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="69d59-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69d59-124">Note</span><span class="sxs-lookup"><span data-stu-id="69d59-124">Remarks</span></span>  
 <span data-ttu-id="69d59-125">Un client Windows Communication Foundation (WCF) sicuro che si connette a un endpoint con questa identità usa il nome UPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="69d59-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69d59-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="69d59-126">Example</span></span>  
 <span data-ttu-id="69d59-127">Il codice di configurazione seguente specifica il nome UPN del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="69d59-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="69d59-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69d59-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="69d59-129">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="69d59-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="69d59-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="69d59-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
