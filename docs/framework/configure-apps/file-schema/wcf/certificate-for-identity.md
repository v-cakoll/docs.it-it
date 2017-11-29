---
title: '&lt;certificate&gt; di &lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a9eabd25712136ef98f452cc15470bce1893527e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="66bbe-102">&lt;certificate&gt; di &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="66bbe-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="66bbe-103">Specifica un certificato X.509 usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="66bbe-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="66bbe-104">Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [autenticazione e identità del servizio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="66bbe-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="66bbe-105">\<identità ></span><span class="sxs-lookup"><span data-stu-id="66bbe-105">\<identity></span></span>  
<span data-ttu-id="66bbe-106">\<certificato ></span><span class="sxs-lookup"><span data-stu-id="66bbe-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66bbe-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66bbe-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66bbe-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="66bbe-108">Attributes and Elements</span></span>  
 <span data-ttu-id="66bbe-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="66bbe-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66bbe-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="66bbe-110">Attributes</span></span>  
  
|<span data-ttu-id="66bbe-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="66bbe-111">Attribute</span></span>|<span data-ttu-id="66bbe-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66bbe-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66bbe-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="66bbe-113">encodedValue</span></span>|<span data-ttu-id="66bbe-114">Codifica Base64 del certificato.</span><span class="sxs-lookup"><span data-stu-id="66bbe-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66bbe-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="66bbe-115">Child Elements</span></span>  
 <span data-ttu-id="66bbe-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="66bbe-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66bbe-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="66bbe-117">Parent Elements</span></span>  
  
|<span data-ttu-id="66bbe-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="66bbe-118">Element</span></span>|<span data-ttu-id="66bbe-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66bbe-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66bbe-120">\<identità ></span><span class="sxs-lookup"><span data-stu-id="66bbe-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="66bbe-121">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="66bbe-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="66bbe-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="66bbe-122">Example</span></span>  
 <span data-ttu-id="66bbe-123">Nel codice seguente viene specificata la rappresentazione codificata di un certificato usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="66bbe-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66bbe-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66bbe-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [<span data-ttu-id="66bbe-125">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="66bbe-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="66bbe-126">\<identità ></span><span class="sxs-lookup"><span data-stu-id="66bbe-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
