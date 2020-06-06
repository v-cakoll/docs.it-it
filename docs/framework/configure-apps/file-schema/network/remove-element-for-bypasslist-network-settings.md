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
ms.openlocfilehash: 97b49a8a520d6a4f72945366874991d2deb18710
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697901"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="be904-102">Elemento \<remove> per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="be904-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="be904-103">Rimuove un indirizzo IP o un nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="be904-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  

## <a name="syntax"></a><span data-ttu-id="be904-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be904-104">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="be904-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="be904-105">Attributes and Elements</span></span>

<span data-ttu-id="be904-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="be904-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="be904-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="be904-107">Attributes</span></span>

|<span data-ttu-id="be904-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="be904-108">**Attribute**</span></span>|<span data-ttu-id="be904-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="be904-109">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="be904-110">Espressione regolare che descrive un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="be904-110">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="be904-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="be904-111">Child Elements</span></span>

<span data-ttu-id="be904-112">No.</span><span class="sxs-lookup"><span data-stu-id="be904-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="be904-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="be904-113">Parent Elements</span></span>

|<span data-ttu-id="be904-114">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="be904-114">**Element**</span></span>|<span data-ttu-id="be904-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="be904-115">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="be904-116">BypassList</span><span class="sxs-lookup"><span data-stu-id="be904-116">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="be904-117">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="be904-117">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="be904-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="be904-118">Remarks</span></span>

<span data-ttu-id="be904-119">L' `remove` elemento rimuove le espressioni regolari che descrivono gli indirizzi IP o i nomi dei server DNS dall'elenco di indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="be904-119">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="be904-120">Gli indirizzi sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="be904-120">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="be904-121">Il valore dell' `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="be904-121">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="be904-122">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="be904-122">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="be904-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="be904-123">Configuration Files</span></span>

<span data-ttu-id="be904-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="be904-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="be904-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="be904-125">Example</span></span>

<span data-ttu-id="be904-126">Nell'esempio seguente viene rimossa qualsiasi definizione precedente per il dominio adventure-works.com, quindi viene aggiunto il dominio contoso.com all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="be904-126">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="be904-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="be904-127">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="be904-128">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="be904-128">Network Settings Schema</span></span>](index.md)
