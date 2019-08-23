---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940518"
---
# <a name="userprincipalname"></a><span data-ttu-id="798c6-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="798c6-101">\<userPrincipalName></span></span>
<span data-ttu-id="798c6-102">Specifica il nome principale dell'utente (UPN, User Principal Name) di un servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="798c6-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="798c6-103">Per ulteriori informazioni sull'impostazione dell'UPN, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="798c6-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="798c6-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="798c6-104">\<identity></span></span>  
<span data-ttu-id="798c6-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="798c6-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="798c6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="798c6-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="798c6-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="798c6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="798c6-108">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="798c6-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="798c6-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="798c6-109">Attributes</span></span>  
  
|<span data-ttu-id="798c6-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="798c6-110">Attribute</span></span>|<span data-ttu-id="798c6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="798c6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="798c6-112">value</span><span class="sxs-lookup"><span data-stu-id="798c6-112">value</span></span>|<span data-ttu-id="798c6-113">Nome costituito dal nome dell'account utente (talvolta detto nome di accesso utente) e dal nome del dominio in cui tale account si trova.</span><span class="sxs-lookup"><span data-stu-id="798c6-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="798c6-114">Questo nome rappresenta il formato standard dei nomi di accesso a un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="798c6-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="798c6-115">Il formato è: someone@example.com (come per un indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="798c6-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="798c6-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="798c6-116">Child Elements</span></span>  
 <span data-ttu-id="798c6-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="798c6-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="798c6-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="798c6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="798c6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="798c6-119">Element</span></span>|<span data-ttu-id="798c6-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="798c6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="798c6-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="798c6-121">\<identity></span></span>](identity.md)|<span data-ttu-id="798c6-122">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="798c6-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="798c6-123">Note</span><span class="sxs-lookup"><span data-stu-id="798c6-123">Remarks</span></span>  
 <span data-ttu-id="798c6-124">Un client Windows Communication Foundation protetto (WCF) che si connette a un endpoint con questa identità usa l'UPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="798c6-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="798c6-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="798c6-125">Example</span></span>  
 <span data-ttu-id="798c6-126">Il codice di configurazione seguente specifica il nome UPN del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="798c6-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="798c6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="798c6-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="798c6-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="798c6-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="798c6-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="798c6-129">\<identity></span></span>](identity.md)
