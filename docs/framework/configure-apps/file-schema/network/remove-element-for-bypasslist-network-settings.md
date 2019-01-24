---
title: '&lt;rimuovere&gt; (elemento) per bypasslist (impostazioni di rete)'
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
ms.openlocfilehash: c9db8cc2cf05987db97f28d7f97967f5bb52404e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625666"
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="fb1b5-102">&lt;rimuovere&gt; (elemento) per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="fb1b5-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="fb1b5-103">Rimuove un indirizzo IP o nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="fb1b5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fb1b5-104">\<configuration></span></span>  
<span data-ttu-id="fb1b5-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="fb1b5-105">\<system.net></span></span>  
<span data-ttu-id="fb1b5-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="fb1b5-106">\<defaultProxy></span></span>  
<span data-ttu-id="fb1b5-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="fb1b5-107">\<bypasslist></span></span>  
<span data-ttu-id="fb1b5-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="fb1b5-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb1b5-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb1b5-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb1b5-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fb1b5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fb1b5-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb1b5-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fb1b5-112">Attributes</span></span>  
  
|<span data-ttu-id="fb1b5-113">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="fb1b5-113">**Attribute**</span></span>|<span data-ttu-id="fb1b5-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fb1b5-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="fb1b5-115">Un'espressione regolare che descrive un indirizzo IP o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb1b5-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fb1b5-116">Child Elements</span></span>  
 <span data-ttu-id="fb1b5-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb1b5-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fb1b5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fb1b5-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fb1b5-119">**Element**</span></span>|<span data-ttu-id="fb1b5-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fb1b5-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fb1b5-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="fb1b5-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="fb1b5-122">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb1b5-123">Note</span><span class="sxs-lookup"><span data-stu-id="fb1b5-123">Remarks</span></span>  
 <span data-ttu-id="fb1b5-124">Il `remove` elemento rimuove le espressioni regolari che descrivono gli indirizzi IP o nomi di server DNS nell'elenco di indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="fb1b5-125">Gli indirizzi sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="fb1b5-126">Il valore per il `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="fb1b5-127">Per altre informazioni sulle espressioni regolari, vedere. [Espressioni regolari di .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="fb1b5-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fb1b5-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="fb1b5-128">Configuration Files</span></span>  
 <span data-ttu-id="fb1b5-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fb1b5-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb1b5-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb1b5-130">Example</span></span>  
 <span data-ttu-id="fb1b5-131">Nell'esempio seguente rimuove le definizioni precedenti per il dominio Adventure-Works.com e quindi aggiunge il dominio contoso.com all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="fb1b5-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb1b5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb1b5-132">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="fb1b5-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="fb1b5-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
