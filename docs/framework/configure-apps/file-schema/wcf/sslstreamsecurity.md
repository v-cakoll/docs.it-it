---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738601"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="0e5d9-101">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="0e5d9-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="0e5d9-102">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="0e5d9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e5d9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0e5d9-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0e5d9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0e5d9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="0e5d9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="0e5d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="0e5d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="0e5d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="0e5d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0e5d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sslStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="0e5d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e5d9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e5d9-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e5d9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e5d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0e5d9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e5d9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e5d9-112">Attributes</span></span>  
  
|<span data-ttu-id="0e5d9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="0e5d9-113">Attribute</span></span>|<span data-ttu-id="0e5d9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e5d9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e5d9-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="0e5d9-115">requireClientCertificate</span></span>|<span data-ttu-id="0e5d9-116">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="0e5d9-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-117">The default is `false`.</span></span>|  
|<span data-ttu-id="0e5d9-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="0e5d9-118">sslProtocols</span></span>|<span data-ttu-id="0e5d9-119">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="0e5d9-120">Il valore predefinito è&#124;Ssl3&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e5d9-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e5d9-121">Child Elements</span></span>  
 <span data-ttu-id="0e5d9-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e5d9-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e5d9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0e5d9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e5d9-124">Element</span></span>|<span data-ttu-id="0e5d9-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e5d9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e5d9-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="0e5d9-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="0e5d9-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0e5d9-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e5d9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e5d9-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="0e5d9-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="0e5d9-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0e5d9-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="0e5d9-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0e5d9-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="0e5d9-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0e5d9-132">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="0e5d9-132">\<customBinding></span></span>](custombinding.md)
