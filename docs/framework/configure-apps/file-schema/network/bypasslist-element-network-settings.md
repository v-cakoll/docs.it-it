---
title: Elemento <bypasslist> (impostazioni di rete)
description: L' <bypasslist> elemento impostazioni di rete fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 42b6ddf4c3d09bcf8ef0ada105cefedccc63b505
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504628"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="e33ea-103">Elemento \<bypasslist> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e33ea-103">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="e33ea-104">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="e33ea-104">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a><span data-ttu-id="e33ea-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e33ea-105">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e33ea-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e33ea-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e33ea-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e33ea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e33ea-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="e33ea-108">Attributes</span></span>  
 <span data-ttu-id="e33ea-109">No.</span><span class="sxs-lookup"><span data-stu-id="e33ea-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e33ea-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e33ea-110">Child Elements</span></span>  
  
|<span data-ttu-id="e33ea-111">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e33ea-111">**Element**</span></span>|<span data-ttu-id="e33ea-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e33ea-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e33ea-113">add</span><span class="sxs-lookup"><span data-stu-id="e33ea-113">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e33ea-114">Aggiunge un indirizzo IP o un nome DNS all'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="e33ea-114">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="e33ea-115">deselezionare</span><span class="sxs-lookup"><span data-stu-id="e33ea-115">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e33ea-116">Cancella l'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="e33ea-116">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="e33ea-117">remove</span><span class="sxs-lookup"><span data-stu-id="e33ea-117">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e33ea-118">Rimuove un indirizzo IP o un nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="e33ea-118">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e33ea-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e33ea-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e33ea-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e33ea-120">**Element**</span></span>|<span data-ttu-id="e33ea-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e33ea-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e33ea-122">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="e33ea-122">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="e33ea-123">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="e33ea-123">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e33ea-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e33ea-124">Remarks</span></span>  
 <span data-ttu-id="e33ea-125">L'elenco di bypass contiene espressioni regolari che descrivono gli URI a cui è <xref:System.Net.WebRequest> possibile accedere direttamente, anziché tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="e33ea-125">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="e33ea-126">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="e33ea-126">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="e33ea-127">L'espressione regolare "[a-z] + \\ . contoso \\ . com" corrisponde a qualsiasi host nel dominio contoso.com, ma corrisponde anche a qualsiasi host nel dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="e33ea-127">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="e33ea-128">Per trovare la corrispondenza solo con un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="e33ea-128">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="e33ea-129">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e33ea-129">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e33ea-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e33ea-130">Configuration Files</span></span>  
 <span data-ttu-id="e33ea-131">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e33ea-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e33ea-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="e33ea-132">Example</span></span>  
 <span data-ttu-id="e33ea-133">Nell'esempio seguente vengono aggiunti due indirizzi all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="e33ea-133">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="e33ea-134">Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server i cui indirizzi IP iniziano con 192,168.</span><span class="sxs-lookup"><span data-stu-id="e33ea-134">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e33ea-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e33ea-135">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="e33ea-136">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e33ea-136">Network Settings Schema</span></span>](index.md)
