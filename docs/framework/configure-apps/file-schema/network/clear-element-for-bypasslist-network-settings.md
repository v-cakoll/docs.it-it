---
title: Elemento <clear> per bypasslist (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154933"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="e2ec4-102">\<clear> elemento per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e2ec4-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="e2ec4-103">Cancella l'elenco di esclusione proxy.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-103">Clears the proxy bypass list.</span></span>  
  
<span data-ttu-id="e2ec4-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2ec4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e2ec4-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e2ec4-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e2ec4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>defaultProxy**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e2ec4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="e2ec4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<elenco di>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e2ec4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>\
<span data-ttu-id="e2ec4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>chiari**</span><span class="sxs-lookup"><span data-stu-id="e2ec4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e2ec4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2ec4-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2ec4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e2ec4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e2ec4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2ec4-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="e2ec4-112">Attributes</span></span>  
 <span data-ttu-id="e2ec4-113">No.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2ec4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2ec4-114">Child Elements</span></span>  
 <span data-ttu-id="e2ec4-115">No.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2ec4-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e2ec4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e2ec4-117">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e2ec4-117">**Element**</span></span>|<span data-ttu-id="e2ec4-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e2ec4-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e2ec4-119">elenco di bypass</span><span class="sxs-lookup"><span data-stu-id="e2ec4-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="e2ec4-120">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2ec4-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e2ec4-121">Remarks</span></span>  
 <span data-ttu-id="e2ec4-122">L'elemento `clear` cancella tutte le voci dall'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e2ec4-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e2ec4-123">Configuration Files</span></span>  
 <span data-ttu-id="e2ec4-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e2ec4-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2ec4-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2ec4-125">Example</span></span>  
 <span data-ttu-id="e2ec4-126">Nell'esempio seguente viene cancellato l'elenco di esclusione e quindi vengono aggiunti due indirizzi all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="e2ec4-127">Il primo ignora il proxy per tutti i server nel dominio contoso.com; il secondo ignora il proxy per tutti i server il cui indirizzo IP inizia con 192.168.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="e2ec4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2ec4-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="e2ec4-129">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e2ec4-129">Network Settings Schema</span></span>](index.md)
