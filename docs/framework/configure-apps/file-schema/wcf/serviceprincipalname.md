---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854998"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="411d4-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="411d4-101">\<servicePrincipalName></span></span>
<span data-ttu-id="411d4-102">Specifica l'identità di un servizio in base al relativo nome dell'entità servizio (SPN, Service Principal Name).</span><span class="sxs-lookup"><span data-stu-id="411d4-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="411d4-103">Per ulteriori informazioni sull'impostazione del nome SPN, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="411d4-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="411d4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="411d4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="411d4-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="411d4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="411d4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="411d4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="411d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpoint**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="411d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="411d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identità**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="411d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="411d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> servicePrincipalName**</span><span class="sxs-lookup"><span data-stu-id="411d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411d4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="411d4-110">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="411d4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="411d4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="411d4-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="411d4-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="411d4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="411d4-113">Attributes</span></span>  
  
|<span data-ttu-id="411d4-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="411d4-114">Attribute</span></span>|<span data-ttu-id="411d4-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="411d4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="411d4-116">value</span><span class="sxs-lookup"><span data-stu-id="411d4-116">value</span></span>|<span data-ttu-id="411d4-117">Nome in base al quale un client identifica in modo univoco un'istanza di un servizio.</span><span class="sxs-lookup"><span data-stu-id="411d4-117">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="411d4-118">Se si installano più istanze di un servizio in computer distribuiti in una foresta, a ogni istanza deve essere associato un nome SPN distinto.</span><span class="sxs-lookup"><span data-stu-id="411d4-118">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="411d4-119">Se i client possono usare più nomi per l'autenticazione, una determinata istanza di servizio può presentare più SPN.</span><span class="sxs-lookup"><span data-stu-id="411d4-119">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="411d4-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="411d4-120">Child Elements</span></span>  
 <span data-ttu-id="411d4-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="411d4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="411d4-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="411d4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="411d4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="411d4-123">Element</span></span>|<span data-ttu-id="411d4-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="411d4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="411d4-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="411d4-125">\<identity></span></span>](identity.md)|<span data-ttu-id="411d4-126">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="411d4-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="411d4-127">Note</span><span class="sxs-lookup"><span data-stu-id="411d4-127">Remarks</span></span>  
 <span data-ttu-id="411d4-128">Un client Windows Communication Foundation protetto (WCF) che si connette a un endpoint con questa identità usa il nome SPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="411d4-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411d4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="411d4-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="411d4-130">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="411d4-130">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="411d4-131">\<identity></span><span class="sxs-lookup"><span data-stu-id="411d4-131">\<identity></span></span>](identity.md)
