---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: ecc67c2b3972ccb5bc8a1fe9ae9b400292642d53
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184491"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="560fd-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="560fd-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="560fd-103">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="560fd-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="560fd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="560fd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="560fd-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="560fd-105">\<bindings></span></span>  
<span data-ttu-id="560fd-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="560fd-106">\<customBinding></span></span>  
<span data-ttu-id="560fd-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="560fd-107">\<binding></span></span>  
<span data-ttu-id="560fd-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="560fd-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="560fd-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="560fd-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="560fd-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="560fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="560fd-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="560fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="560fd-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="560fd-112">Attributes</span></span>  
  
|<span data-ttu-id="560fd-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="560fd-113">Attribute</span></span>|<span data-ttu-id="560fd-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="560fd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="560fd-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="560fd-115">requireClientCertificate</span></span>|<span data-ttu-id="560fd-116">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="560fd-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="560fd-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="560fd-117">The default is `false`.</span></span>|  
|<span data-ttu-id="560fd-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="560fd-118">sslProtocols</span></span>|<span data-ttu-id="560fd-119">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="560fd-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="560fd-120">Il valore predefinito è Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="560fd-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="560fd-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="560fd-121">Child Elements</span></span>  
 <span data-ttu-id="560fd-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="560fd-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="560fd-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="560fd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="560fd-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="560fd-124">Element</span></span>|<span data-ttu-id="560fd-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="560fd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="560fd-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="560fd-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="560fd-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="560fd-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="560fd-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="560fd-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="560fd-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="560fd-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="560fd-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="560fd-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="560fd-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="560fd-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="560fd-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="560fd-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
