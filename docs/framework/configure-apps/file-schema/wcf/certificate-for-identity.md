---
title: '&lt;certificate&gt; di &lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 28a1b992a70986652030ad42d4d4a5738350ae1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676159"
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="e8301-102">&lt;certificate&gt; di &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="e8301-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="e8301-103">Specifica un certificato X.509 usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="e8301-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="e8301-104">Per altre informazioni sull'impostazione del valore dell'elemento, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e8301-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="e8301-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="e8301-105">\<identity></span></span>  
<span data-ttu-id="e8301-106">\<certificate></span><span class="sxs-lookup"><span data-stu-id="e8301-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8301-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8301-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8301-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8301-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e8301-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8301-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8301-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8301-110">Attributes</span></span>  
  
|<span data-ttu-id="e8301-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8301-111">Attribute</span></span>|<span data-ttu-id="e8301-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8301-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8301-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="e8301-113">encodedValue</span></span>|<span data-ttu-id="e8301-114">Codifica Base64 del certificato.</span><span class="sxs-lookup"><span data-stu-id="e8301-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8301-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8301-115">Child Elements</span></span>  
 <span data-ttu-id="e8301-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e8301-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8301-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8301-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e8301-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8301-118">Element</span></span>|<span data-ttu-id="e8301-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8301-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8301-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="e8301-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e8301-121">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="e8301-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8301-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8301-122">Example</span></span>  
 <span data-ttu-id="e8301-123">Nel codice seguente viene specificata la rappresentazione codificata di un certificato usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="e8301-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="e8301-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8301-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="e8301-125">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="e8301-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e8301-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="e8301-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
