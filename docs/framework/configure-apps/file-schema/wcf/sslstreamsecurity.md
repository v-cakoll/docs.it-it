---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738601"
---
# \<sslStreamSecurity>
<span data-ttu-id="b8b7b-101">Rappresenta un elemento di associazione personalizzato che supporta la sicurezza del canale mediante un flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="b8b7b-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8b7b-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8b7b-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b8b7b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b8b7b-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8b7b-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="b8b7b-105">Attributes</span></span>  
  
|<span data-ttu-id="b8b7b-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="b8b7b-106">Attribute</span></span>|<span data-ttu-id="b8b7b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8b7b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8b7b-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="b8b7b-108">requireClientCertificate</span></span>|<span data-ttu-id="b8b7b-109">Valore booleano che specifica se per questa associazione è necessario un certificato client.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="b8b7b-110">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-110">The default is `false`.</span></span>|  
|<span data-ttu-id="b8b7b-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="b8b7b-111">sslProtocols</span></span>|<span data-ttu-id="b8b7b-112">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="b8b7b-113">Il valore predefinito è Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8b7b-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b8b7b-114">Child Elements</span></span>  
 <span data-ttu-id="b8b7b-115">No.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8b7b-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b8b7b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b8b7b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8b7b-117">Element</span></span>|<span data-ttu-id="b8b7b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8b7b-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b8b7b-119">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8b7b-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b8b7b-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="b8b7b-121">Binding</span><span class="sxs-lookup"><span data-stu-id="b8b7b-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b8b7b-122">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="b8b7b-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b8b7b-123">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b8b7b-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
