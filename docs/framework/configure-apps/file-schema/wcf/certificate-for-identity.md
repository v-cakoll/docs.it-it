---
title: <certificate> per <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 804600e4eb1612cd8654fc58ec3df28596c1e84d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265038"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="eed2b-102">\<certificato > per \<identità ></span><span class="sxs-lookup"><span data-stu-id="eed2b-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="eed2b-103">Specifica un certificato X.509 usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="eed2b-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="eed2b-104">Per altre informazioni sull'impostazione del valore dell'elemento, vedere [identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="eed2b-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="eed2b-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="eed2b-105">\<identity></span></span>  
<span data-ttu-id="eed2b-106">\<certificate></span><span class="sxs-lookup"><span data-stu-id="eed2b-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed2b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eed2b-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eed2b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eed2b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eed2b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eed2b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eed2b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="eed2b-110">Attributes</span></span>  
  
|<span data-ttu-id="eed2b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="eed2b-111">Attribute</span></span>|<span data-ttu-id="eed2b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eed2b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eed2b-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="eed2b-113">encodedValue</span></span>|<span data-ttu-id="eed2b-114">Codifica Base64 del certificato.</span><span class="sxs-lookup"><span data-stu-id="eed2b-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eed2b-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eed2b-115">Child Elements</span></span>  
 <span data-ttu-id="eed2b-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eed2b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eed2b-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eed2b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="eed2b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="eed2b-118">Element</span></span>|<span data-ttu-id="eed2b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eed2b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eed2b-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="eed2b-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="eed2b-121">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="eed2b-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eed2b-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="eed2b-122">Example</span></span>  
 <span data-ttu-id="eed2b-123">Nel codice seguente viene specificata la rappresentazione codificata di un certificato usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="eed2b-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="eed2b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed2b-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="eed2b-125">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="eed2b-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="eed2b-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="eed2b-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
