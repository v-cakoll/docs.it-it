---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854830"
---
# \<userPrincipalName>
<span data-ttu-id="15cbd-101">Specifica il nome principale dell'utente (UPN, User Principal Name) di un servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="15cbd-101">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="15cbd-102">Per ulteriori informazioni sull'impostazione dell'UPN, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="15cbd-102">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="15cbd-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15cbd-103">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15cbd-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="15cbd-104">Attributes and Elements</span></span>  
 <span data-ttu-id="15cbd-105">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="15cbd-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15cbd-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="15cbd-106">Attributes</span></span>  
  
|<span data-ttu-id="15cbd-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="15cbd-107">Attribute</span></span>|<span data-ttu-id="15cbd-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15cbd-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15cbd-109">Valore</span><span class="sxs-lookup"><span data-stu-id="15cbd-109">value</span></span>|<span data-ttu-id="15cbd-110">Nome costituito dal nome dell'account utente (talvolta detto nome di accesso utente) e dal nome del dominio in cui tale account si trova.</span><span class="sxs-lookup"><span data-stu-id="15cbd-110">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="15cbd-111">Questo nome rappresenta il formato standard dei nomi di accesso a un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="15cbd-111">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="15cbd-112">Il formato è: someone@example.com (come per un indirizzo di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="15cbd-112">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15cbd-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="15cbd-113">Child Elements</span></span>  
 <span data-ttu-id="15cbd-114">No.</span><span class="sxs-lookup"><span data-stu-id="15cbd-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15cbd-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="15cbd-115">Parent Elements</span></span>  
  
|<span data-ttu-id="15cbd-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="15cbd-116">Element</span></span>|<span data-ttu-id="15cbd-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15cbd-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="15cbd-118">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="15cbd-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15cbd-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="15cbd-119">Remarks</span></span>  
 <span data-ttu-id="15cbd-120">Un client Windows Communication Foundation protetto (WCF) che si connette a un endpoint con questa identità usa l'UPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="15cbd-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15cbd-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="15cbd-121">Example</span></span>  
 <span data-ttu-id="15cbd-122">Il codice di configurazione seguente specifica il nome UPN del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="15cbd-122">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="15cbd-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="15cbd-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="15cbd-124">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="15cbd-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
