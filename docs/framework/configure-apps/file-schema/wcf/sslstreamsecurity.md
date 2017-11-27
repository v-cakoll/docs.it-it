---
title: '&lt;sslStreamSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 5c801562339f02ff983bb5a755fda6718185ba5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="64d92-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="64d92-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="64d92-103">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="64d92-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="64d92-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="64d92-104">\<system.serviceModel></span></span>  
<span data-ttu-id="64d92-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="64d92-105">\<bindings></span></span>  
<span data-ttu-id="64d92-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="64d92-106">\<customBinding></span></span>  
<span data-ttu-id="64d92-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="64d92-107">\<binding></span></span>  
<span data-ttu-id="64d92-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="64d92-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d92-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64d92-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64d92-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="64d92-110">Attributes and Elements</span></span>  
 <span data-ttu-id="64d92-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="64d92-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64d92-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="64d92-112">Attributes</span></span>  
  
|<span data-ttu-id="64d92-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="64d92-113">Attribute</span></span>|<span data-ttu-id="64d92-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64d92-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64d92-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="64d92-115">requireClientCertificate</span></span>|<span data-ttu-id="64d92-116">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="64d92-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="64d92-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="64d92-117">The default is `false`.</span></span>|  
|<span data-ttu-id="64d92-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="64d92-118">sslProtocols</span></span>|<span data-ttu-id="64d92-119">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="64d92-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="64d92-120">Il valore predefinito è Ssl3 &#124; TLS &#124; Tls11 &#124; Tls12.</span><span class="sxs-lookup"><span data-stu-id="64d92-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64d92-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="64d92-121">Child Elements</span></span>  
 <span data-ttu-id="64d92-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="64d92-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64d92-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="64d92-123">Parent Elements</span></span>  
  
|<span data-ttu-id="64d92-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="64d92-124">Element</span></span>|<span data-ttu-id="64d92-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64d92-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64d92-126">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="64d92-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="64d92-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="64d92-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64d92-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64d92-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="64d92-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="64d92-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="64d92-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="64d92-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="64d92-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="64d92-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="64d92-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="64d92-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
