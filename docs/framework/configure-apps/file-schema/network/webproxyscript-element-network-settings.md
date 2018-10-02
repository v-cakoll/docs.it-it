---
title: '&lt;webProxyScript&gt; (impostazioni di rete)'
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
ms.openlocfilehash: 1e1450d2df424b32aacc5c113b5936001f65915a
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862737"
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="c0c84-102">&lt;webProxyScript&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c0c84-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="c0c84-103">Consente di configurare le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="c0c84-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="c0c84-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c0c84-104">\<configuration></span></span>  
<span data-ttu-id="c0c84-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c0c84-105">\<system.net></span></span>  
<span data-ttu-id="c0c84-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="c0c84-106">\<settings></span></span>  
<span data-ttu-id="c0c84-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="c0c84-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c84-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0c84-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0c84-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c0c84-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c0c84-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c0c84-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0c84-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c0c84-111">Attributes</span></span>  
  
|<span data-ttu-id="c0c84-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="c0c84-112">Attribute</span></span>|<span data-ttu-id="c0c84-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0c84-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="c0c84-114">Specifica il tempo massimo per scaricare lo script in ore, minuti e secondi.</span><span class="sxs-lookup"><span data-stu-id="c0c84-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="c0c84-115">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="c0c84-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0c84-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c0c84-116">Child Elements</span></span>  
 <span data-ttu-id="c0c84-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c0c84-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0c84-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c0c84-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c0c84-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0c84-119">Element</span></span>|<span data-ttu-id="c0c84-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0c84-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0c84-121">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="c0c84-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="c0c84-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c0c84-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0c84-123">Note</span><span class="sxs-lookup"><span data-stu-id="c0c84-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c0c84-124">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c0c84-124">Configuration Files</span></span>  
 <span data-ttu-id="c0c84-125">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c0c84-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c84-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0c84-126">See Also</span></span>  
 [<span data-ttu-id="c0c84-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c0c84-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
