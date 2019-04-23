---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 9e7b845d39495dba1d1a19af95faf308b8b8c0fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188246"
---
# <a name="userprincipalname"></a><span data-ttu-id="e3291-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="e3291-101">\<userPrincipalName></span></span>
<span data-ttu-id="e3291-102">Specifica il nome principale dell'utente (UPN, User Principal Name) di un servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="e3291-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="e3291-103">Per altre informazioni sull'impostazione del nome UPN, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e3291-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="e3291-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="e3291-104">\<identity></span></span>  
<span data-ttu-id="e3291-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="e3291-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3291-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3291-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3291-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e3291-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e3291-108">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e3291-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3291-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="e3291-109">Attributes</span></span>  
  
|<span data-ttu-id="e3291-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="e3291-110">Attribute</span></span>|<span data-ttu-id="e3291-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3291-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3291-112">predefinito</span><span class="sxs-lookup"><span data-stu-id="e3291-112">value</span></span>|<span data-ttu-id="e3291-113">Nome costituito dal nome dell'account utente (talvolta detto nome di accesso utente) e dal nome del dominio in cui tale account si trova.</span><span class="sxs-lookup"><span data-stu-id="e3291-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="e3291-114">Questo nome rappresenta il formato standard dei nomi di accesso a un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="e3291-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="e3291-115">Il formato è: someone@example.com (per un indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="e3291-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3291-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e3291-116">Child Elements</span></span>  
 <span data-ttu-id="e3291-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e3291-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3291-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e3291-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e3291-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3291-119">Element</span></span>|<span data-ttu-id="e3291-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3291-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3291-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="e3291-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e3291-122">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="e3291-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3291-123">Note</span><span class="sxs-lookup"><span data-stu-id="e3291-123">Remarks</span></span>  
 <span data-ttu-id="e3291-124">Un client Windows Communication Foundation (WCF) sicuro che si connette a un endpoint con questa identità usa il nome UPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e3291-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3291-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3291-125">Example</span></span>  
 <span data-ttu-id="e3291-126">Il codice di configurazione seguente specifica il nome UPN del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="e3291-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="e3291-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3291-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="e3291-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="e3291-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e3291-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="e3291-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
