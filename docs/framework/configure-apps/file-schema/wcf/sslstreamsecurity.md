---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: b081a577280f4f2a52ef3b5ece76f519f9701faa
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145107"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="cd70b-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="cd70b-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="cd70b-103">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="cd70b-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="cd70b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cd70b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="cd70b-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="cd70b-105">\<bindings></span></span>  
<span data-ttu-id="cd70b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cd70b-106">\<customBinding></span></span>  
<span data-ttu-id="cd70b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="cd70b-107">\<binding></span></span>  
<span data-ttu-id="cd70b-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="cd70b-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd70b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd70b-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd70b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cd70b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cd70b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cd70b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd70b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cd70b-112">Attributes</span></span>  
  
|<span data-ttu-id="cd70b-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="cd70b-113">Attribute</span></span>|<span data-ttu-id="cd70b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd70b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd70b-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="cd70b-115">requireClientCertificate</span></span>|<span data-ttu-id="cd70b-116">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="cd70b-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="cd70b-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cd70b-117">The default is `false`.</span></span>|  
|<span data-ttu-id="cd70b-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="cd70b-118">sslProtocols</span></span>|<span data-ttu-id="cd70b-119">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="cd70b-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="cd70b-120">Il valore predefinito è Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="cd70b-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd70b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cd70b-121">Child Elements</span></span>  
 <span data-ttu-id="cd70b-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cd70b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd70b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cd70b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cd70b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd70b-124">Element</span></span>|<span data-ttu-id="cd70b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd70b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd70b-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="cd70b-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cd70b-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cd70b-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd70b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd70b-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="cd70b-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="cd70b-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cd70b-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="cd70b-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="cd70b-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cd70b-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="cd70b-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cd70b-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
