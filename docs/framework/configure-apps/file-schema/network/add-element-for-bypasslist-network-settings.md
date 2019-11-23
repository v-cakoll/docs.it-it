---
title: Elemento <add> per bypasslist (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 1db0ba3b0a213de1175e6e0cee347753d2a413b7
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699606"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="6f696-102">\<aggiungere > elemento per l'elemento bypass (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6f696-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="6f696-103">Aggiunge un indirizzo IP o un nome DNS all'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="6f696-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="6f696-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="6f696-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6f696-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f696-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="6f696-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f696-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="6f696-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<di [ **bypass** >](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f696-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="6f696-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="6f696-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f696-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f696-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f696-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6f696-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6f696-111">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6f696-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f696-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="6f696-112">Attributes</span></span>  
  
|<span data-ttu-id="6f696-113">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="6f696-113">**Attribute**</span></span>|<span data-ttu-id="6f696-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6f696-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="6f696-115">**address**</span><span class="sxs-lookup"><span data-stu-id="6f696-115">**address**</span></span>|<span data-ttu-id="6f696-116">Espressione regolare che descrive un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="6f696-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f696-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6f696-117">Child Elements</span></span>  
 <span data-ttu-id="6f696-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6f696-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f696-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6f696-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6f696-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="6f696-120">**Element**</span></span>|<span data-ttu-id="6f696-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6f696-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6f696-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="6f696-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="6f696-123">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="6f696-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f696-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6f696-124">Remarks</span></span>  
 <span data-ttu-id="6f696-125">L'elemento `add` inserisce le espressioni regolari che descrivono gli indirizzi IP o i nomi dei server DNS nell'elenco di indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="6f696-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="6f696-126">Il valore dell'attributo `address` deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="6f696-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="6f696-127">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="6f696-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="6f696-128">L'espressione regolare "[a-z] +\\. contoso\\. com" corrisponde a qualsiasi host nel dominio contoso.com, ma corrisponde anche a qualsiasi host nel dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="6f696-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="6f696-129">Per trovare la corrispondenza con un solo host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] +\\. contoso\\. com $".</span><span class="sxs-lookup"><span data-stu-id="6f696-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="6f696-130">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6f696-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6f696-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="6f696-131">Configuration Files</span></span>  
 <span data-ttu-id="6f696-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6f696-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f696-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f696-133">Example</span></span>  
 <span data-ttu-id="6f696-134">Nell'esempio seguente vengono aggiunti due indirizzi all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="6f696-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="6f696-135">Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server il cui indirizzo IP inizia con 192,168.</span><span class="sxs-lookup"><span data-stu-id="6f696-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f696-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f696-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="6f696-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="6f696-137">Network Settings Schema</span></span>](index.md)
