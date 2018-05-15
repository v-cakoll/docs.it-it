---
title: '&lt;webProxyScript&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6843662b73f6b7d45dd12616f5118569a2d19975
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="96e40-102">&lt;webProxyScript&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="96e40-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="96e40-103">Consente di configurare le caratteristiche dello script utilizzato per individuare il proxy Web.</span><span class="sxs-lookup"><span data-stu-id="96e40-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="96e40-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="96e40-104">\<configuration></span></span>  
<span data-ttu-id="96e40-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="96e40-105">\<system.net></span></span>  
<span data-ttu-id="96e40-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="96e40-106">\<settings></span></span>  
<span data-ttu-id="96e40-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="96e40-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e40-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96e40-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96e40-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="96e40-109">Attributes and Elements</span></span>  
 <span data-ttu-id="96e40-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="96e40-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96e40-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="96e40-111">Attributes</span></span>  
  
|<span data-ttu-id="96e40-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="96e40-112">Attribute</span></span>|<span data-ttu-id="96e40-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96e40-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="96e40-114">Specifica il tempo massimo per scaricare lo script in ore, minuti e secondi.</span><span class="sxs-lookup"><span data-stu-id="96e40-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="96e40-115">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="96e40-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96e40-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="96e40-116">Child Elements</span></span>  
 <span data-ttu-id="96e40-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="96e40-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96e40-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="96e40-118">Parent Elements</span></span>  
  
|<span data-ttu-id="96e40-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="96e40-119">Element</span></span>|<span data-ttu-id="96e40-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96e40-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96e40-121">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="96e40-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="96e40-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="96e40-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96e40-123">Note</span><span class="sxs-lookup"><span data-stu-id="96e40-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="96e40-124">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="96e40-124">Configuration Files</span></span>  
 <span data-ttu-id="96e40-125">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="96e40-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e40-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96e40-126">See Also</span></span>  
 [<span data-ttu-id="96e40-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="96e40-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
