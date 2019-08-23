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
ms.openlocfilehash: da234402c6ec7e2c1f85e4bd674517b1147f0d18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927487"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="8192d-102">\<Aggiungi elemento > per l'elemento bypass (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8192d-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="8192d-103">Aggiunge un indirizzo IP o un nome DNS all'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="8192d-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="8192d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8192d-104">\<configuration></span></span>  
<span data-ttu-id="8192d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8192d-105">\<system.net></span></span>  
<span data-ttu-id="8192d-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="8192d-106">\<defaultProxy></span></span>  
<span data-ttu-id="8192d-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="8192d-107">\<bypasslist></span></span>  
<span data-ttu-id="8192d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="8192d-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8192d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8192d-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8192d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8192d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8192d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8192d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8192d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8192d-112">Attributes</span></span>  
  
|<span data-ttu-id="8192d-113">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="8192d-113">**Attribute**</span></span>|<span data-ttu-id="8192d-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8192d-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="8192d-115">**address**</span><span class="sxs-lookup"><span data-stu-id="8192d-115">**address**</span></span>|<span data-ttu-id="8192d-116">Espressione regolare che descrive un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="8192d-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8192d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8192d-117">Child Elements</span></span>  
 <span data-ttu-id="8192d-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8192d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8192d-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8192d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8192d-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="8192d-120">**Element**</span></span>|<span data-ttu-id="8192d-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8192d-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8192d-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="8192d-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="8192d-123">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="8192d-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8192d-124">Note</span><span class="sxs-lookup"><span data-stu-id="8192d-124">Remarks</span></span>  
 <span data-ttu-id="8192d-125">L' `add` elemento inserisce le espressioni regolari che descrivono gli indirizzi IP o i nomi dei server DNS nell'elenco degli indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="8192d-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="8192d-126">Il valore dell' `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="8192d-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="8192d-127">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="8192d-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="8192d-128">L'espressione regolare "[a-z] +\\. contoso\\. com" corrisponde a qualsiasi host nel dominio contoso.com, ma corrisponde anche a qualsiasi host nel dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="8192d-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="8192d-129">Per trovare la corrispondenza solo con un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z\\] +\\. contoso. com $".</span><span class="sxs-lookup"><span data-stu-id="8192d-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="8192d-130">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8192d-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8192d-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="8192d-131">Configuration Files</span></span>  
 <span data-ttu-id="8192d-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8192d-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8192d-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="8192d-133">Example</span></span>  
 <span data-ttu-id="8192d-134">Nell'esempio seguente vengono aggiunti due indirizzi all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="8192d-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="8192d-135">Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server il cui indirizzo IP inizia con 192,168.</span><span class="sxs-lookup"><span data-stu-id="8192d-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8192d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8192d-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="8192d-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="8192d-137">Network Settings Schema</span></span>](index.md)
