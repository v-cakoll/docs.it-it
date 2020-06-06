---
title: Elemento <webProxyScript> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089065"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="c08c4-102">Elemento \<webProxyScript> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c08c4-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="c08c4-103">Configura le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="c08c4-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="c08c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c08c4-104">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c08c4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c08c4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c08c4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c08c4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c08c4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c08c4-107">Attributes</span></span>  
  
|<span data-ttu-id="c08c4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="c08c4-108">Attribute</span></span>|<span data-ttu-id="c08c4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c08c4-109">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="c08c4-110">Specifica il tempo massimo per il download dello script in ore, minuti e secondi.</span><span class="sxs-lookup"><span data-stu-id="c08c4-110">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="c08c4-111">Il valore predefinito è un minuto.</span><span class="sxs-lookup"><span data-stu-id="c08c4-111">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c08c4-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c08c4-112">Child Elements</span></span>  
 <span data-ttu-id="c08c4-113">No.</span><span class="sxs-lookup"><span data-stu-id="c08c4-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c08c4-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c08c4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c08c4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c08c4-115">Element</span></span>|<span data-ttu-id="c08c4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c08c4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c08c4-117">impostazioni</span><span class="sxs-lookup"><span data-stu-id="c08c4-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="c08c4-118">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c08c4-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c08c4-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="c08c4-119">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c08c4-120">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c08c4-120">Configuration Files</span></span>  
 <span data-ttu-id="c08c4-121">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c08c4-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08c4-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c08c4-122">See also</span></span>

- [<span data-ttu-id="c08c4-123">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c08c4-123">Network Settings Schema</span></span>](index.md)
