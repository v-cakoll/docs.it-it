---
title: '&lt;rimuovere&gt; elemento per bypasslist (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5c7918048743d53d8523ec399d1a11c67152a2bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742949"
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="f0517-102">&lt;rimuovere&gt; elemento per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f0517-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="f0517-103">Rimuove l'elenco proxy da ignorare un indirizzo IP o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="f0517-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="f0517-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f0517-104">\<configuration></span></span>  
<span data-ttu-id="f0517-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="f0517-105">\<system.net></span></span>  
<span data-ttu-id="f0517-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="f0517-106">\<defaultProxy></span></span>  
<span data-ttu-id="f0517-107">\<BypassList ></span><span class="sxs-lookup"><span data-stu-id="f0517-107">\<bypasslist></span></span>  
<span data-ttu-id="f0517-108">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="f0517-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0517-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0517-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0517-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f0517-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f0517-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f0517-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0517-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f0517-112">Attributes</span></span>  
  
|<span data-ttu-id="f0517-113">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="f0517-113">**Attribute**</span></span>|<span data-ttu-id="f0517-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f0517-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="f0517-115">Un'espressione regolare che descrive un indirizzo IP o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="f0517-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0517-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f0517-116">Child Elements</span></span>  
 <span data-ttu-id="f0517-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f0517-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0517-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f0517-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f0517-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="f0517-119">**Element**</span></span>|<span data-ttu-id="f0517-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f0517-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f0517-121">BypassList</span><span class="sxs-lookup"><span data-stu-id="f0517-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="f0517-122">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="f0517-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0517-123">Note</span><span class="sxs-lookup"><span data-stu-id="f0517-123">Remarks</span></span>  
 <span data-ttu-id="f0517-124">Il `remove` elemento rimuove espressioni regolari che descrivono gli indirizzi IP o nomi di server DNS nell'elenco di indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="f0517-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="f0517-125">Gli indirizzi sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f0517-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="f0517-126">Il valore per il `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="f0517-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="f0517-127">Per ulteriori informazioni sulle espressioni regolari, vedere. [Espressioni regolari di .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f0517-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f0517-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="f0517-128">Configuration Files</span></span>  
 <span data-ttu-id="f0517-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f0517-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0517-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0517-130">Example</span></span>  
 <span data-ttu-id="f0517-131">Nell'esempio seguente rimuove qualsiasi definizione precedente per il dominio adventure-works.com e quindi aggiunge il dominio contoso.com all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="f0517-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0517-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0517-132">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="f0517-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f0517-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
