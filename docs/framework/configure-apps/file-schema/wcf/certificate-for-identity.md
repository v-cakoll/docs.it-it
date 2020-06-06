---
title: <certificate> per <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850011"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="15d60-102">\<certificate> per \<identity></span><span class="sxs-lookup"><span data-stu-id="15d60-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="15d60-103">Specifica un certificato X.509 usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="15d60-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="15d60-104">Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="15d60-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="15d60-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15d60-105">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15d60-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="15d60-106">Attributes and Elements</span></span>  
 <span data-ttu-id="15d60-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="15d60-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15d60-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="15d60-108">Attributes</span></span>  
  
|<span data-ttu-id="15d60-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="15d60-109">Attribute</span></span>|<span data-ttu-id="15d60-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15d60-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15d60-111">encodedValue</span><span class="sxs-lookup"><span data-stu-id="15d60-111">encodedValue</span></span>|<span data-ttu-id="15d60-112">Codifica Base64 del certificato.</span><span class="sxs-lookup"><span data-stu-id="15d60-112">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15d60-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="15d60-113">Child Elements</span></span>  
 <span data-ttu-id="15d60-114">No.</span><span class="sxs-lookup"><span data-stu-id="15d60-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15d60-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="15d60-115">Parent Elements</span></span>  
  
|<span data-ttu-id="15d60-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="15d60-116">Element</span></span>|<span data-ttu-id="15d60-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15d60-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="15d60-118">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="15d60-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="15d60-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="15d60-119">Example</span></span>  
 <span data-ttu-id="15d60-120">Nel codice seguente viene specificata la rappresentazione codificata di un certificato usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="15d60-120">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="15d60-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="15d60-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="15d60-122">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="15d60-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
