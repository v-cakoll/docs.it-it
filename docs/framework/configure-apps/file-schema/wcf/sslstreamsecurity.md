---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204445"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="316b8-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="316b8-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="316b8-102">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="316b8-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="316b8-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="316b8-103">\<system.serviceModel></span></span>  
<span data-ttu-id="316b8-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="316b8-104">\<bindings></span></span>  
<span data-ttu-id="316b8-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="316b8-105">\<customBinding></span></span>  
<span data-ttu-id="316b8-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="316b8-106">\<binding></span></span>  
<span data-ttu-id="316b8-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="316b8-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="316b8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="316b8-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="316b8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="316b8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="316b8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="316b8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="316b8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="316b8-111">Attributes</span></span>  
  
|<span data-ttu-id="316b8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="316b8-112">Attribute</span></span>|<span data-ttu-id="316b8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="316b8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="316b8-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="316b8-114">requireClientCertificate</span></span>|<span data-ttu-id="316b8-115">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="316b8-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="316b8-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="316b8-116">The default is `false`.</span></span>|  
|<span data-ttu-id="316b8-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="316b8-117">sslProtocols</span></span>|<span data-ttu-id="316b8-118">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="316b8-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="316b8-119">Il valore predefinito è Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="316b8-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="316b8-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="316b8-120">Child Elements</span></span>  
 <span data-ttu-id="316b8-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="316b8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="316b8-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="316b8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="316b8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="316b8-123">Element</span></span>|<span data-ttu-id="316b8-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="316b8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="316b8-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="316b8-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="316b8-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="316b8-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="316b8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="316b8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="316b8-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="316b8-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="316b8-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="316b8-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="316b8-130">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="316b8-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="316b8-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="316b8-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
