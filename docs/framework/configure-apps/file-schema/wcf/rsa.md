---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855049"
---
# <a name="rsa"></a><span data-ttu-id="14dfc-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="14dfc-101">\<rsa></span></span>
<span data-ttu-id="14dfc-102">Un client WCF protetto che si connette a un endpoint con questa identità verifica che le attestazioni presentate dal server contengano un'attestazione contenente a sua volta la chiave pubblica RSA usata per costruire tale identità.</span><span class="sxs-lookup"><span data-stu-id="14dfc-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
<span data-ttu-id="14dfc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14dfc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14dfc-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="14dfc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="14dfc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="14dfc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="14dfc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpoint**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="14dfc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="14dfc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identità**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="14dfc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="14dfc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> RSA**</span><span class="sxs-lookup"><span data-stu-id="14dfc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14dfc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14dfc-109">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14dfc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14dfc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="14dfc-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14dfc-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14dfc-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="14dfc-112">Attributes</span></span>  
  
|<span data-ttu-id="14dfc-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="14dfc-113">Attribute</span></span>|<span data-ttu-id="14dfc-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="14dfc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14dfc-115">value</span><span class="sxs-lookup"><span data-stu-id="14dfc-115">value</span></span>|<span data-ttu-id="14dfc-116">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="14dfc-116">Optional String.</span></span> <span data-ttu-id="14dfc-117">Valore della chiave pubblica RSA con cui eseguire il confronto nel client.</span><span class="sxs-lookup"><span data-stu-id="14dfc-117">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14dfc-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14dfc-118">Child Elements</span></span>  
 <span data-ttu-id="14dfc-119">Nessuna</span><span class="sxs-lookup"><span data-stu-id="14dfc-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14dfc-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14dfc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="14dfc-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="14dfc-121">Element</span></span>|<span data-ttu-id="14dfc-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="14dfc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14dfc-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="14dfc-123">\<identity></span></span>](identity.md)|<span data-ttu-id="14dfc-124">Specifica l'identità del servizio da autenticare presso il client.</span><span class="sxs-lookup"><span data-stu-id="14dfc-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14dfc-125">Note</span><span class="sxs-lookup"><span data-stu-id="14dfc-125">Remarks</span></span>  
 <span data-ttu-id="14dfc-126">Un controllo RSA consente di restringere specificamente l'autenticazione a un solo certificato in base alla relativa chiave RSA o in base a un valore di chiave RSA generato manualmente.</span><span class="sxs-lookup"><span data-stu-id="14dfc-126">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="14dfc-127">Ciò consente l'autenticazione più restrittiva di una chiave RSA specifica a spese del servizio, che non funziona più con i client esistenti se il valore della chiave RSA viene modificato.</span><span class="sxs-lookup"><span data-stu-id="14dfc-127">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="14dfc-128">Per ulteriori informazioni sull'utilizzo di Identity per convalidare un servizio a un client, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="14dfc-128">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14dfc-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="14dfc-129">Example</span></span>  
 <span data-ttu-id="14dfc-130">Nel codice di configurazione seguente viene specificato il valore della chiave pubblica di un certificato X.509 usato per autenticare un server.</span><span class="sxs-lookup"><span data-stu-id="14dfc-130">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="14dfc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14dfc-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="14dfc-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="14dfc-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="14dfc-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="14dfc-133">\<identity></span></span>](identity.md)
