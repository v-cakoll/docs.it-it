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
ms.workload: dotnet
ms.openlocfilehash: 7f9b4ec506097cf010af78b3504def08102e0774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="dd797-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="dd797-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="dd797-103">Specifica l'identità di un servizio in base al relativo nome dell'entità servizio (SPN, Service Principal Name).</span><span class="sxs-lookup"><span data-stu-id="dd797-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="dd797-104">Per ulteriori informazioni sull'impostazione del nome SPN, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="dd797-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="dd797-105">\<identità ></span><span class="sxs-lookup"><span data-stu-id="dd797-105">\<identity></span></span>  
<span data-ttu-id="dd797-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="dd797-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd797-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd797-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd797-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd797-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dd797-109">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd797-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd797-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd797-110">Attributes</span></span>  
  
|<span data-ttu-id="dd797-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="dd797-111">Attribute</span></span>|<span data-ttu-id="dd797-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd797-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd797-113">predefinito</span><span class="sxs-lookup"><span data-stu-id="dd797-113">value</span></span>|<span data-ttu-id="dd797-114">Nome in base al quale un client identifica in modo univoco un'istanza di un servizio.</span><span class="sxs-lookup"><span data-stu-id="dd797-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="dd797-115">Se si installano più istanze di un servizio in computer distribuiti in una foresta, a ogni istanza deve essere associato un nome SPN distinto.</span><span class="sxs-lookup"><span data-stu-id="dd797-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="dd797-116">Se i client possono usare più nomi per l'autenticazione, una determinata istanza di servizio può presentare più SPN.</span><span class="sxs-lookup"><span data-stu-id="dd797-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd797-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd797-117">Child Elements</span></span>  
 <span data-ttu-id="dd797-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dd797-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd797-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd797-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dd797-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd797-120">Element</span></span>|<span data-ttu-id="dd797-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd797-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd797-122">\<identità ></span><span class="sxs-lookup"><span data-stu-id="dd797-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="dd797-123">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="dd797-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd797-124">Note</span><span class="sxs-lookup"><span data-stu-id="dd797-124">Remarks</span></span>  
 <span data-ttu-id="dd797-125">Un client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] protetto che si connette a un endpoint con questa identità usa l'SPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dd797-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd797-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd797-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="dd797-127">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="dd797-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="dd797-128">\<identità ></span><span class="sxs-lookup"><span data-stu-id="dd797-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
