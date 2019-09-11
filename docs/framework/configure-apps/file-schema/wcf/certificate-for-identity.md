---
title: <certificate> per <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850011"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="a7936-102">\<> del certificato \<per l'identità ></span><span class="sxs-lookup"><span data-stu-id="a7936-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="a7936-103">Specifica un certificato X.509 usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="a7936-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="a7936-104">Per ulteriori informazioni sull'impostazione del valore dell'elemento, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a7936-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="a7936-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a7936-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a7936-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a7936-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a7936-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="a7936-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="a7936-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpoint**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="a7936-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="a7936-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identità**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="a7936-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="a7936-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificato**</span><span class="sxs-lookup"><span data-stu-id="a7936-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7936-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7936-111">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7936-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a7936-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a7936-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a7936-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7936-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="a7936-114">Attributes</span></span>  
  
|<span data-ttu-id="a7936-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="a7936-115">Attribute</span></span>|<span data-ttu-id="a7936-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7936-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7936-117">encodedValue</span><span class="sxs-lookup"><span data-stu-id="a7936-117">encodedValue</span></span>|<span data-ttu-id="a7936-118">Codifica Base64 del certificato.</span><span class="sxs-lookup"><span data-stu-id="a7936-118">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7936-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a7936-119">Child Elements</span></span>  
 <span data-ttu-id="a7936-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a7936-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7936-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a7936-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a7936-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7936-122">Element</span></span>|<span data-ttu-id="a7936-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7936-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7936-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="a7936-124">\<identity></span></span>](identity.md)|<span data-ttu-id="a7936-125">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="a7936-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a7936-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7936-126">Example</span></span>  
 <span data-ttu-id="a7936-127">Nel codice seguente viene specificata la rappresentazione codificata di un certificato usato per convalidare un server presso un client.</span><span class="sxs-lookup"><span data-stu-id="a7936-127">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="a7936-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7936-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="a7936-129">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="a7936-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a7936-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="a7936-130">\<identity></span></span>](identity.md)
