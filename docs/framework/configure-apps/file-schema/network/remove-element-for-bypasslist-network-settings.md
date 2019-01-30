---
title: Elemento <remove> per bypasslist (Impostazioni di rete)
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
ms.openlocfilehash: c1e5d9a6726e1ae21d0ab449886b1074e399a655
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256979"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="14bdb-102">\<rimuovere > (elemento) per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="14bdb-102">\<remove> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="14bdb-103">Rimuove un indirizzo IP o nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="14bdb-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="14bdb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="14bdb-104">\<configuration></span></span>  
<span data-ttu-id="14bdb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="14bdb-105">\<system.net></span></span>  
<span data-ttu-id="14bdb-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="14bdb-106">\<defaultProxy></span></span>  
<span data-ttu-id="14bdb-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="14bdb-107">\<bypasslist></span></span>  
<span data-ttu-id="14bdb-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="14bdb-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14bdb-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14bdb-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14bdb-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14bdb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="14bdb-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14bdb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14bdb-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="14bdb-112">Attributes</span></span>  
  
|<span data-ttu-id="14bdb-113">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="14bdb-113">**Attribute**</span></span>|<span data-ttu-id="14bdb-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="14bdb-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="14bdb-115">Un'espressione regolare che descrive un indirizzo IP o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="14bdb-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14bdb-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14bdb-116">Child Elements</span></span>  
 <span data-ttu-id="14bdb-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="14bdb-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14bdb-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14bdb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="14bdb-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="14bdb-119">**Element**</span></span>|<span data-ttu-id="14bdb-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="14bdb-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="14bdb-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="14bdb-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="14bdb-122">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.</span><span class="sxs-lookup"><span data-stu-id="14bdb-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14bdb-123">Note</span><span class="sxs-lookup"><span data-stu-id="14bdb-123">Remarks</span></span>  
 <span data-ttu-id="14bdb-124">Il `remove` elemento rimuove le espressioni regolari che descrivono gli indirizzi IP o nomi di server DNS nell'elenco di indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="14bdb-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="14bdb-125">Gli indirizzi sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="14bdb-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="14bdb-126">Il valore per il `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="14bdb-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="14bdb-127">Per altre informazioni sulle espressioni regolari, vedere. [Espressioni regolari di .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="14bdb-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="14bdb-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="14bdb-128">Configuration Files</span></span>  
 <span data-ttu-id="14bdb-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="14bdb-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14bdb-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="14bdb-130">Example</span></span>  
 <span data-ttu-id="14bdb-131">Nell'esempio seguente rimuove le definizioni precedenti per il dominio Adventure-Works.com e quindi aggiunge il dominio contoso.com all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="14bdb-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14bdb-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14bdb-132">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="14bdb-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="14bdb-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
