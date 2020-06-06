---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854998"
---
# \<servicePrincipalName>
<span data-ttu-id="2b1d8-101">Specifica l'identità di un servizio in base al relativo nome dell'entità servizio (SPN, Service Principal Name).</span><span class="sxs-lookup"><span data-stu-id="2b1d8-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="2b1d8-102">Per ulteriori informazioni sull'impostazione del nome SPN, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2b1d8-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="2b1d8-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b1d8-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b1d8-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b1d8-104">Attributes and Elements</span></span>  
 <span data-ttu-id="2b1d8-105">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b1d8-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b1d8-106">Attributes</span></span>  
  
|<span data-ttu-id="2b1d8-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="2b1d8-107">Attribute</span></span>|<span data-ttu-id="2b1d8-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b1d8-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b1d8-109">Valore</span><span class="sxs-lookup"><span data-stu-id="2b1d8-109">value</span></span>|<span data-ttu-id="2b1d8-110">Nome con cui un client identifica in modo univoco un'istanza di un servizio.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="2b1d8-111">Se si installano più istanze di un servizio in computer distribuiti in una foresta, a ogni istanza deve essere associato un nome SPN distinto.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="2b1d8-112">Se i client possono usare più nomi per l'autenticazione, una determinata istanza di servizio può presentare più SPN.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b1d8-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b1d8-113">Child Elements</span></span>  
 <span data-ttu-id="2b1d8-114">No.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b1d8-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b1d8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2b1d8-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b1d8-116">Element</span></span>|<span data-ttu-id="2b1d8-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b1d8-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="2b1d8-118">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b1d8-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="2b1d8-119">Remarks</span></span>  
 <span data-ttu-id="2b1d8-120">Un client Windows Communication Foundation protetto (WCF) che si connette a un endpoint con questa identità usa il nome SPN quando esegue l'autenticazione SSPI con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b1d8-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2b1d8-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="2b1d8-122">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="2b1d8-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
