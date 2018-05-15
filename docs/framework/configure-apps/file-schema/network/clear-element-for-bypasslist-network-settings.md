---
title: '&lt;deselezionare&gt; elemento per bypasslist (impostazioni di rete)'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 9297b68a31117aabfa45328954ccb9c7cdac66c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a><span data-ttu-id="1dfe0-102">&lt;deselezionare&gt; elemento per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="1dfe0-102">&lt;clear&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="1dfe0-103">Cancella l'elenco proxy da ignorare.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="1dfe0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1dfe0-104">\<configuration></span></span>  
<span data-ttu-id="1dfe0-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1dfe0-105">\<system.net></span></span>  
<span data-ttu-id="1dfe0-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="1dfe0-106">\<defaultProxy></span></span>  
<span data-ttu-id="1dfe0-107">\<BypassList ></span><span class="sxs-lookup"><span data-stu-id="1dfe0-107">\<bypasslist></span></span>  
<span data-ttu-id="1dfe0-108">\<cancellare ></span><span class="sxs-lookup"><span data-stu-id="1dfe0-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dfe0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1dfe0-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dfe0-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1dfe0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1dfe0-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dfe0-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1dfe0-112">Attributes</span></span>  
 <span data-ttu-id="1dfe0-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1dfe0-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1dfe0-114">Child Elements</span></span>  
 <span data-ttu-id="1dfe0-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dfe0-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1dfe0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1dfe0-117">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1dfe0-117">**Element**</span></span>|<span data-ttu-id="1dfe0-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1dfe0-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1dfe0-119">BypassList</span><span class="sxs-lookup"><span data-stu-id="1dfe0-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="1dfe0-120">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dfe0-121">Note</span><span class="sxs-lookup"><span data-stu-id="1dfe0-121">Remarks</span></span>  
 <span data-ttu-id="1dfe0-122">Il `clear` elemento cancella tutte le voci dell'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1dfe0-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1dfe0-123">Configuration Files</span></span>  
 <span data-ttu-id="1dfe0-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1dfe0-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dfe0-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="1dfe0-125">Example</span></span>  
 <span data-ttu-id="1dfe0-126">Nell'esempio seguente consente di cancellare l'elenco di esclusione e quindi aggiunge due indirizzi all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="1dfe0-127">Il primo viene ignorato il proxy per tutti i server nel dominio contoso.com. il secondo consente di ignorare il proxy per tutti i server il cui indirizzo IP inizia con 192.168.</span><span class="sxs-lookup"><span data-stu-id="1dfe0-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1dfe0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dfe0-128">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="1dfe0-129">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="1dfe0-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
