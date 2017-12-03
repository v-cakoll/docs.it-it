---
title: '&lt;servicePrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b734a095f0c9ea9ad1bd6e78f3ef4264f4f2317e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="f86bb-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="f86bb-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="f86bb-103">Specifica l'identità di un servizio in base al relativo nome dell'entità servizio (SPN, Service Principal Name).</span><span class="sxs-lookup"><span data-stu-id="f86bb-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="f86bb-104">Per ulteriori informazioni sull'impostazione del nome SPN, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f86bb-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="f86bb-105">\<identità ></span><span class="sxs-lookup"><span data-stu-id="f86bb-105">\<identity></span></span>  
<span data-ttu-id="f86bb-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="f86bb-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f86bb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f86bb-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f86bb-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f86bb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f86bb-109">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f86bb-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f86bb-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f86bb-110">Attributes</span></span>  
  
|<span data-ttu-id="f86bb-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f86bb-111">Attribute</span></span>|<span data-ttu-id="f86bb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f86bb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f86bb-113">predefinito</span><span class="sxs-lookup"><span data-stu-id="f86bb-113">value</span></span>|<span data-ttu-id="f86bb-114">Nome in base al quale un client identifica in modo univoco un'istanza di un servizio.</span><span class="sxs-lookup"><span data-stu-id="f86bb-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="f86bb-115">Se si installano più istanze di un servizio in computer distribuiti in una foresta, a ogni istanza deve essere associato un nome SPN distinto.</span><span class="sxs-lookup"><span data-stu-id="f86bb-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="f86bb-116">Se i client possono usare più nomi per l'autenticazione, una determinata istanza di servizio può presentare più SPN.</span><span class="sxs-lookup"><span data-stu-id="f86bb-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f86bb-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f86bb-117">Child Elements</span></span>  
 <span data-ttu-id="f86bb-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f86bb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f86bb-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f86bb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f86bb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f86bb-120">Element</span></span>|<span data-ttu-id="f86bb-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f86bb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f86bb-122">\<identità ></span><span class="sxs-lookup"><span data-stu-id="f86bb-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f86bb-123">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="f86bb-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f86bb-124">Note</span><span class="sxs-lookup"><span data-stu-id="f86bb-124">Remarks</span></span>  
 <span data-ttu-id="f86bb-125">Un client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] protetto che si connette a un endpoint con questa identità usa l'SPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f86bb-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86bb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f86bb-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="f86bb-127">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="f86bb-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="f86bb-128">\<identità ></span><span class="sxs-lookup"><span data-stu-id="f86bb-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
