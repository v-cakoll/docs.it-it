---
title: Elemento <bypasslist> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 10d2a025096579c6bed64f82cc955deb0542717c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664198"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="3585e-102">\<Elemento > di bypass (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="3585e-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="3585e-103">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="3585e-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="3585e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3585e-104">\<configuration></span></span>  
<span data-ttu-id="3585e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3585e-105">\<system.net></span></span>  
<span data-ttu-id="3585e-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="3585e-106">\<defaultProxy></span></span>  
<span data-ttu-id="3585e-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="3585e-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3585e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3585e-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3585e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3585e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3585e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3585e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3585e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="3585e-111">Attributes</span></span>  
 <span data-ttu-id="3585e-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3585e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3585e-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3585e-113">Child Elements</span></span>  
  
|<span data-ttu-id="3585e-114">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3585e-114">**Element**</span></span>|<span data-ttu-id="3585e-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3585e-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3585e-116">add</span><span class="sxs-lookup"><span data-stu-id="3585e-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="3585e-117">Aggiunge un indirizzo IP o un nome DNS all'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="3585e-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="3585e-118">clear</span><span class="sxs-lookup"><span data-stu-id="3585e-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="3585e-119">Cancella l'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="3585e-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="3585e-120">remove</span><span class="sxs-lookup"><span data-stu-id="3585e-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="3585e-121">Rimuove un indirizzo IP o un nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="3585e-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3585e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3585e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3585e-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3585e-123">**Element**</span></span>|<span data-ttu-id="3585e-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3585e-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3585e-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="3585e-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="3585e-126">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="3585e-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3585e-127">Note</span><span class="sxs-lookup"><span data-stu-id="3585e-127">Remarks</span></span>  
 <span data-ttu-id="3585e-128">L'elenco di bypass contiene espressioni regolari che descrivono <xref:System.Net.WebRequest> gli URI a cui è possibile accedere direttamente, anziché tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="3585e-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="3585e-129">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="3585e-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="3585e-130">L'espressione regolare "[a-z] +\\. contoso\\. com" corrisponde a qualsiasi host nel dominio contoso.com, ma corrisponde anche a qualsiasi host nel dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="3585e-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="3585e-131">Per trovare la corrispondenza solo con un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z\\] +\\. contoso. com $".</span><span class="sxs-lookup"><span data-stu-id="3585e-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="3585e-132">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3585e-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3585e-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3585e-133">Configuration Files</span></span>  
 <span data-ttu-id="3585e-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3585e-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3585e-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="3585e-135">Example</span></span>  
 <span data-ttu-id="3585e-136">Nell'esempio seguente vengono aggiunti due indirizzi all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="3585e-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="3585e-137">Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server i cui indirizzi IP iniziano con 192,168.</span><span class="sxs-lookup"><span data-stu-id="3585e-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3585e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3585e-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3585e-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="3585e-139">Network Settings Schema</span></span>](index.md)
