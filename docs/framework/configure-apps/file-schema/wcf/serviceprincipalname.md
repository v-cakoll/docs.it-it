---
title: '&lt;servicePrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 5d65b5956491e30066ece54a48374f1d7014552e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657590"
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="ef0fa-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="ef0fa-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="ef0fa-103">Specifica l'identità di un servizio in base al relativo nome dell'entità servizio (SPN, Service Principal Name).</span><span class="sxs-lookup"><span data-stu-id="ef0fa-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="ef0fa-104">Per altre informazioni sull'impostazione del nome SPN, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="ef0fa-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="ef0fa-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="ef0fa-105">\<identity></span></span>  
<span data-ttu-id="ef0fa-106">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="ef0fa-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef0fa-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef0fa-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef0fa-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef0fa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ef0fa-109">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef0fa-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef0fa-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef0fa-110">Attributes</span></span>  
  
|<span data-ttu-id="ef0fa-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ef0fa-111">Attribute</span></span>|<span data-ttu-id="ef0fa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef0fa-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef0fa-113">predefinito</span><span class="sxs-lookup"><span data-stu-id="ef0fa-113">value</span></span>|<span data-ttu-id="ef0fa-114">Nome in base al quale un client identifica in modo univoco un'istanza di un servizio.</span><span class="sxs-lookup"><span data-stu-id="ef0fa-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="ef0fa-115">Se si installano più istanze di un servizio in computer distribuiti in una foresta, a ogni istanza deve essere associato un nome SPN distinto.</span><span class="sxs-lookup"><span data-stu-id="ef0fa-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="ef0fa-116">Se i client possono usare più nomi per l'autenticazione, una determinata istanza di servizio può presentare più SPN.</span><span class="sxs-lookup"><span data-stu-id="ef0fa-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef0fa-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef0fa-117">Child Elements</span></span>  
 <span data-ttu-id="ef0fa-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ef0fa-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef0fa-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef0fa-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ef0fa-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef0fa-120">Element</span></span>|<span data-ttu-id="ef0fa-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef0fa-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef0fa-122">\<identity></span><span class="sxs-lookup"><span data-stu-id="ef0fa-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ef0fa-123">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="ef0fa-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef0fa-124">Note</span><span class="sxs-lookup"><span data-stu-id="ef0fa-124">Remarks</span></span>  
 <span data-ttu-id="ef0fa-125">Un client Windows Communication Foundation (WCF) sicuro che si connette a un endpoint con questa identità usa il nome SPN quando si esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ef0fa-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0fa-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef0fa-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="ef0fa-127">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="ef0fa-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ef0fa-128">\<identity></span><span class="sxs-lookup"><span data-stu-id="ef0fa-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
