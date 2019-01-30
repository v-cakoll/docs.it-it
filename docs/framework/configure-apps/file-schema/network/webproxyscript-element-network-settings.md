---
title: Elemento <webProxyScript> (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: e823d6065ea23f3a47dad6853a1b9e1237a616c9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257824"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="65576-102">\<webProxyScript > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="65576-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="65576-103">Consente di configurare le caratteristiche dello script utilizzato per individuare i proxy Web.</span><span class="sxs-lookup"><span data-stu-id="65576-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="65576-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="65576-104">\<configuration></span></span>  
<span data-ttu-id="65576-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="65576-105">\<system.net></span></span>  
<span data-ttu-id="65576-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="65576-106">\<settings></span></span>  
<span data-ttu-id="65576-107">\<webProxyScript></span><span class="sxs-lookup"><span data-stu-id="65576-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65576-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65576-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65576-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="65576-109">Attributes and Elements</span></span>  
 <span data-ttu-id="65576-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="65576-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65576-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="65576-111">Attributes</span></span>  
  
|<span data-ttu-id="65576-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="65576-112">Attribute</span></span>|<span data-ttu-id="65576-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65576-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="65576-114">Specifica il tempo massimo per scaricare lo script in ore, minuti e secondi.</span><span class="sxs-lookup"><span data-stu-id="65576-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="65576-115">Il valore predefinito è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="65576-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65576-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="65576-116">Child Elements</span></span>  
 <span data-ttu-id="65576-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="65576-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65576-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="65576-118">Parent Elements</span></span>  
  
|<span data-ttu-id="65576-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="65576-119">Element</span></span>|<span data-ttu-id="65576-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65576-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65576-121">settings</span><span class="sxs-lookup"><span data-stu-id="65576-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="65576-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="65576-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65576-123">Note</span><span class="sxs-lookup"><span data-stu-id="65576-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="65576-124">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="65576-124">Configuration Files</span></span>  
 <span data-ttu-id="65576-125">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="65576-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65576-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65576-126">See also</span></span>
- [<span data-ttu-id="65576-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="65576-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
