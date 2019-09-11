---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854830"
---
# <a name="userprincipalname"></a><span data-ttu-id="d31a4-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="d31a4-101">\<userPrincipalName></span></span>
<span data-ttu-id="d31a4-102">Specifica il nome principale dell'utente (UPN, User Principal Name) di un servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="d31a4-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="d31a4-103">Per ulteriori informazioni sull'impostazione dell'UPN, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d31a4-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="d31a4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d31a4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d31a4-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d31a4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d31a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="d31a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="d31a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpoint**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="d31a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="d31a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identità**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="d31a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="d31a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="d31a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31a4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d31a4-110">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d31a4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d31a4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d31a4-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d31a4-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d31a4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="d31a4-113">Attributes</span></span>  
  
|<span data-ttu-id="d31a4-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="d31a4-114">Attribute</span></span>|<span data-ttu-id="d31a4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d31a4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d31a4-116">value</span><span class="sxs-lookup"><span data-stu-id="d31a4-116">value</span></span>|<span data-ttu-id="d31a4-117">Nome costituito dal nome dell'account utente (talvolta detto nome di accesso utente) e dal nome del dominio in cui tale account si trova.</span><span class="sxs-lookup"><span data-stu-id="d31a4-117">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="d31a4-118">Questo nome rappresenta il formato standard dei nomi di accesso a un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d31a4-118">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="d31a4-119">Il formato è: someone@example.com (come per un indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="d31a4-119">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d31a4-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d31a4-120">Child Elements</span></span>  
 <span data-ttu-id="d31a4-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d31a4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d31a4-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d31a4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d31a4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d31a4-123">Element</span></span>|<span data-ttu-id="d31a4-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d31a4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d31a4-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="d31a4-125">\<identity></span></span>](identity.md)|<span data-ttu-id="d31a4-126">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="d31a4-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d31a4-127">Note</span><span class="sxs-lookup"><span data-stu-id="d31a4-127">Remarks</span></span>  
 <span data-ttu-id="d31a4-128">Un client Windows Communication Foundation protetto (WCF) che si connette a un endpoint con questa identità usa l'UPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d31a4-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d31a4-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="d31a4-129">Example</span></span>  
 <span data-ttu-id="d31a4-130">Il codice di configurazione seguente specifica il nome UPN del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="d31a4-130">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="d31a4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d31a4-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="d31a4-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="d31a4-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d31a4-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="d31a4-133">\<identity></span></span>](identity.md)
