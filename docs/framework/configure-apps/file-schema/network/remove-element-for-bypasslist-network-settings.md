---
title: Elemento <remove> per bypasslist (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 0fd8de9af00aa861d92c8c201ef89545e108c790
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659231"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="5ecb1-102">\<Rimuovi elemento > per l'elemento bypass (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="5ecb1-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="5ecb1-103">Rimuove un indirizzo IP o un nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

<span data-ttu-id="5ecb1-104">\<> di configurazione </span><span class="sxs-lookup"><span data-stu-id="5ecb1-104">\<configuration></span></span>\
<span data-ttu-id="5ecb1-105">\<System. net > </span><span class="sxs-lookup"><span data-stu-id="5ecb1-105">\<system.net></span></span>\
<span data-ttu-id="5ecb1-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="5ecb1-106">\<defaultProxy></span></span>\
<span data-ttu-id="5ecb1-107">\<> di bypass </span><span class="sxs-lookup"><span data-stu-id="5ecb1-107">\<bypasslist></span></span>\
<span data-ttu-id="5ecb1-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="5ecb1-108">\<remove></span></span>

## <a name="syntax"></a><span data-ttu-id="5ecb1-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ecb1-109">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5ecb1-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5ecb1-110">Attributes and Elements</span></span>

<span data-ttu-id="5ecb1-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ecb1-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5ecb1-112">Attributes</span></span>

|<span data-ttu-id="5ecb1-113">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="5ecb1-113">**Attribute**</span></span>|<span data-ttu-id="5ecb1-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5ecb1-114">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="5ecb1-115">Espressione regolare che descrive un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-115">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5ecb1-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5ecb1-116">Child Elements</span></span>

<span data-ttu-id="5ecb1-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5ecb1-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5ecb1-118">Parent Elements</span></span>

|<span data-ttu-id="5ecb1-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="5ecb1-119">**Element**</span></span>|<span data-ttu-id="5ecb1-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5ecb1-120">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="5ecb1-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="5ecb1-121">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="5ecb1-122">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5ecb1-123">Note</span><span class="sxs-lookup"><span data-stu-id="5ecb1-123">Remarks</span></span>

<span data-ttu-id="5ecb1-124">L' `remove` elemento rimuove le espressioni regolari che descrivono gli indirizzi IP o i nomi dei server DNS dall'elenco di indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="5ecb1-125">Gli indirizzi sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="5ecb1-126">Il valore `address` dell'attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="5ecb1-127">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5ecb1-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="5ecb1-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="5ecb1-128">Configuration Files</span></span>

<span data-ttu-id="5ecb1-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5ecb1-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="5ecb1-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ecb1-130">Example</span></span>

<span data-ttu-id="5ecb1-131">Nell'esempio seguente viene rimossa qualsiasi definizione precedente per il dominio adventure-works.com, quindi viene aggiunto il dominio contoso.com all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="5ecb1-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5ecb1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ecb1-132">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="5ecb1-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="5ecb1-133">Network Settings Schema</span></span>](index.md)
