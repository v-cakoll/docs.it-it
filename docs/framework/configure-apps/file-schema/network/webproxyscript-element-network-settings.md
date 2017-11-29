---
title: '&lt;webProxyScript&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d1258301af903ef5c36df854c7c6dd504d6eef15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="8e328-102">&lt;webProxyScript&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8e328-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8e328-103">Consente di configurare le caratteristiche dello script utilizzato per individuare il proxy Web.</span><span class="sxs-lookup"><span data-stu-id="8e328-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="8e328-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8e328-104">\<configuration></span></span>  
<span data-ttu-id="8e328-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="8e328-105">\<system.net></span></span>  
<span data-ttu-id="8e328-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="8e328-106">\<settings></span></span>  
<span data-ttu-id="8e328-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="8e328-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e328-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e328-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e328-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8e328-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8e328-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8e328-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e328-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8e328-111">Attributes</span></span>  
  
|<span data-ttu-id="8e328-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8e328-112">Attribute</span></span>|<span data-ttu-id="8e328-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e328-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="8e328-114">Specifica il tempo massimo per scaricare lo script in ore, minuti e secondi.</span><span class="sxs-lookup"><span data-stu-id="8e328-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="8e328-115">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="8e328-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e328-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8e328-116">Child Elements</span></span>  
 <span data-ttu-id="8e328-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8e328-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e328-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8e328-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8e328-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e328-119">Element</span></span>|<span data-ttu-id="8e328-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e328-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e328-121">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="8e328-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="8e328-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="8e328-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e328-123">Note</span><span class="sxs-lookup"><span data-stu-id="8e328-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8e328-124">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="8e328-124">Configuration Files</span></span>  
 <span data-ttu-id="8e328-125">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8e328-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e328-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e328-126">See Also</span></span>  
 [<span data-ttu-id="8e328-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="8e328-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
