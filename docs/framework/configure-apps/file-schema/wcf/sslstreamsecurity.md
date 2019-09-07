---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 9b7092878c604142c29dcd8d27e3c458d203f9fa
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399522"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="7ae55-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="7ae55-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="7ae55-102">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="7ae55-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="7ae55-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7ae55-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7ae55-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7ae55-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7ae55-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7ae55-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7ae55-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="7ae55-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="7ae55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="7ae55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7ae55-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sslStreamSecurity**</span><span class="sxs-lookup"><span data-stu-id="7ae55-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae55-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ae55-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ae55-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7ae55-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ae55-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7ae55-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ae55-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7ae55-112">Attributes</span></span>  
  
|<span data-ttu-id="7ae55-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7ae55-113">Attribute</span></span>|<span data-ttu-id="7ae55-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ae55-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ae55-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="7ae55-115">requireClientCertificate</span></span>|<span data-ttu-id="7ae55-116">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="7ae55-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="7ae55-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="7ae55-117">The default is `false`.</span></span>|  
|<span data-ttu-id="7ae55-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="7ae55-118">sslProtocols</span></span>|<span data-ttu-id="7ae55-119">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="7ae55-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="7ae55-120">Il valore predefinito è&#124;Ssl3&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="7ae55-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ae55-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7ae55-121">Child Elements</span></span>  
 <span data-ttu-id="7ae55-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7ae55-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ae55-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7ae55-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7ae55-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ae55-124">Element</span></span>|<span data-ttu-id="7ae55-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ae55-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ae55-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ae55-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="7ae55-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7ae55-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ae55-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ae55-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="7ae55-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="7ae55-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7ae55-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="7ae55-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7ae55-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="7ae55-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7ae55-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7ae55-132">\<customBinding></span></span>](custombinding.md)
