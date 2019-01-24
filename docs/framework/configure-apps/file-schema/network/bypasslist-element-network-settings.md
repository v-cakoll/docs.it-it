---
title: '&lt;BypassList&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 82a9a3e6362538fc62b4afdb010ca784590b9db9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746338"
---
# <a name="ltbypasslistgt-element-network-settings"></a><span data-ttu-id="3d7f8-102">&lt;BypassList&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="3d7f8-102">&lt;bypasslist&gt; Element (Network Settings)</span></span>
<span data-ttu-id="3d7f8-103">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="3d7f8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3d7f8-104">\<configuration></span></span>  
<span data-ttu-id="3d7f8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3d7f8-105">\<system.net></span></span>  
<span data-ttu-id="3d7f8-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="3d7f8-106">\<defaultProxy></span></span>  
<span data-ttu-id="3d7f8-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="3d7f8-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d7f8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d7f8-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d7f8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3d7f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3d7f8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d7f8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="3d7f8-111">Attributes</span></span>  
 <span data-ttu-id="3d7f8-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d7f8-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3d7f8-113">Child Elements</span></span>  
  
|<span data-ttu-id="3d7f8-114">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3d7f8-114">**Element**</span></span>|<span data-ttu-id="3d7f8-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3d7f8-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3d7f8-116">add</span><span class="sxs-lookup"><span data-stu-id="3d7f8-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="3d7f8-117">Aggiunge un indirizzo IP o nome DNS per l'elenco proxy da ignorare.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="3d7f8-118">clear</span><span class="sxs-lookup"><span data-stu-id="3d7f8-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="3d7f8-119">Cancella l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="3d7f8-120">remove</span><span class="sxs-lookup"><span data-stu-id="3d7f8-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="3d7f8-121">Rimuove un indirizzo IP o nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d7f8-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3d7f8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3d7f8-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3d7f8-123">**Element**</span></span>|<span data-ttu-id="3d7f8-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3d7f8-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3d7f8-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="3d7f8-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="3d7f8-126">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="3d7f8-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d7f8-127">Note</span><span class="sxs-lookup"><span data-stu-id="3d7f8-127">Remarks</span></span>  
 <span data-ttu-id="3d7f8-128">Elenco di esclusione contiene espressioni regolari che descrivono gli URI che <xref:System.Net.WebRequest> istanze accedere direttamente anziché tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="3d7f8-129">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="3d7f8-130">L'espressione regolare "[a-z] +\\.contoso\\. com" corrisponde a qualsiasi host nel dominio contoso.com, che corrisponde anche a qualsiasi host nel dominio cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="3d7f8-131">In modo che corrisponda solo un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] +\\.contoso\\$. com".</span><span class="sxs-lookup"><span data-stu-id="3d7f8-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="3d7f8-132">Per altre informazioni sulle espressioni regolari, vedere. [Espressioni regolari di .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3d7f8-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3d7f8-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3d7f8-133">Configuration Files</span></span>  
 <span data-ttu-id="3d7f8-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3d7f8-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d7f8-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d7f8-135">Example</span></span>  
 <span data-ttu-id="3d7f8-136">L'esempio seguente aggiunge due indirizzi all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="3d7f8-137">Il primo consente di ignorare il proxy per tutti i server nel dominio contoso.com. il secondo consente di ignorare il proxy per tutti i server iniziano con indirizzi IP 192.168.</span><span class="sxs-lookup"><span data-stu-id="3d7f8-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d7f8-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d7f8-138">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3d7f8-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="3d7f8-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
