---
title: '&lt;aggiungere&gt; (elemento) per bypasslist (impostazioni di rete)'
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
ms.openlocfilehash: 3be617d53ba87c35ae44f143da15a6b647eaa0d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680780"
---
# <a name="ltaddgt-element-for-bypasslist-network-settings"></a><span data-ttu-id="46093-102">&lt;aggiungere&gt; (elemento) per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="46093-102">&lt;add&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="46093-103">Aggiunge un indirizzo IP o nome DNS per l'elenco proxy da ignorare.</span><span class="sxs-lookup"><span data-stu-id="46093-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="46093-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="46093-104">\<configuration></span></span>  
<span data-ttu-id="46093-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="46093-105">\<system.net></span></span>  
<span data-ttu-id="46093-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="46093-106">\<defaultProxy></span></span>  
<span data-ttu-id="46093-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="46093-107">\<bypasslist></span></span>  
<span data-ttu-id="46093-108">\<add></span><span class="sxs-lookup"><span data-stu-id="46093-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46093-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46093-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46093-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="46093-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46093-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="46093-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46093-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="46093-112">Attributes</span></span>  
  
|<span data-ttu-id="46093-113">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="46093-113">**Attribute**</span></span>|<span data-ttu-id="46093-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="46093-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="46093-115">**address**</span><span class="sxs-lookup"><span data-stu-id="46093-115">**address**</span></span>|<span data-ttu-id="46093-116">Un'espressione regolare che descrive un indirizzo IP o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="46093-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46093-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="46093-117">Child Elements</span></span>  
 <span data-ttu-id="46093-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="46093-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46093-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="46093-119">Parent Elements</span></span>  
  
|<span data-ttu-id="46093-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="46093-120">**Element**</span></span>|<span data-ttu-id="46093-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="46093-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="46093-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="46093-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="46093-123">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.</span><span class="sxs-lookup"><span data-stu-id="46093-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46093-124">Note</span><span class="sxs-lookup"><span data-stu-id="46093-124">Remarks</span></span>  
 <span data-ttu-id="46093-125">Il `add` elemento consente di inserire le espressioni regolari che descrivono gli indirizzi IP o nomi di server DNS all'elenco di indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="46093-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="46093-126">Il valore della `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="46093-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="46093-127">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="46093-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="46093-128">L'espressione regolare "[a-z] +\\.contoso\\. com" corrisponde a qualsiasi host nel dominio contoso.com, che corrisponde anche a qualsiasi host nel dominio cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="46093-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="46093-129">In modo che corrisponda solo un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] +\\.contoso\\$. com".</span><span class="sxs-lookup"><span data-stu-id="46093-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="46093-130">Per altre informazioni sulle espressioni regolari, vedere. [Espressioni regolari di .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="46093-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="46093-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="46093-131">Configuration Files</span></span>  
 <span data-ttu-id="46093-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="46093-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46093-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="46093-133">Example</span></span>  
 <span data-ttu-id="46093-134">L'esempio seguente aggiunge due indirizzi all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="46093-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="46093-135">Il primo consente di ignorare il proxy per tutti i server nel dominio contoso.com. il secondo consente di ignorare il proxy per tutti i server il cui indirizzo IP inizia con 192.168.</span><span class="sxs-lookup"><span data-stu-id="46093-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="46093-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46093-136">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="46093-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="46093-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
