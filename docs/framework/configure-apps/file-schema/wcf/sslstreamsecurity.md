---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 5ed87adfb3963513602844fc69afce8f7994fa8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932430"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="c3305-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="c3305-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="c3305-102">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="c3305-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="c3305-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c3305-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c3305-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="c3305-104">\<bindings></span></span>  
<span data-ttu-id="c3305-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c3305-105">\<customBinding></span></span>  
<span data-ttu-id="c3305-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c3305-106">\<binding></span></span>  
<span data-ttu-id="c3305-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="c3305-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3305-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3305-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3305-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c3305-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c3305-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c3305-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3305-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c3305-111">Attributes</span></span>  
  
|<span data-ttu-id="c3305-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="c3305-112">Attribute</span></span>|<span data-ttu-id="c3305-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3305-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3305-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="c3305-114">requireClientCertificate</span></span>|<span data-ttu-id="c3305-115">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="c3305-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="c3305-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="c3305-116">The default is `false`.</span></span>|  
|<span data-ttu-id="c3305-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="c3305-117">sslProtocols</span></span>|<span data-ttu-id="c3305-118">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="c3305-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="c3305-119">Il valore predefinito è&#124;Ssl3&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="c3305-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3305-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c3305-120">Child Elements</span></span>  
 <span data-ttu-id="c3305-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c3305-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3305-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c3305-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c3305-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3305-123">Element</span></span>|<span data-ttu-id="c3305-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c3305-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3305-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="c3305-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c3305-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c3305-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3305-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3305-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="c3305-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c3305-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c3305-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="c3305-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c3305-130">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c3305-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c3305-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c3305-131">\<customBinding></span></span>](custombinding.md)
