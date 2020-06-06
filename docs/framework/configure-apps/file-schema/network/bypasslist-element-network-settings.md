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
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154946"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="edead-102">Elemento \<bypasslist> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="edead-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="edead-103">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="edead-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a><span data-ttu-id="edead-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edead-104">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edead-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="edead-105">Attributes and Elements</span></span>  
 <span data-ttu-id="edead-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="edead-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edead-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="edead-107">Attributes</span></span>  
 <span data-ttu-id="edead-108">No.</span><span class="sxs-lookup"><span data-stu-id="edead-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="edead-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="edead-109">Child Elements</span></span>  
  
|<span data-ttu-id="edead-110">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="edead-110">**Element**</span></span>|<span data-ttu-id="edead-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="edead-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="edead-112">add</span><span class="sxs-lookup"><span data-stu-id="edead-112">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="edead-113">Aggiunge un indirizzo IP o un nome DNS all'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="edead-113">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="edead-114">deselezionare</span><span class="sxs-lookup"><span data-stu-id="edead-114">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="edead-115">Cancella l'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="edead-115">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="edead-116">remove</span><span class="sxs-lookup"><span data-stu-id="edead-116">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="edead-117">Rimuove un indirizzo IP o un nome DNS dall'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="edead-117">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edead-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="edead-118">Parent Elements</span></span>  
  
|<span data-ttu-id="edead-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="edead-119">**Element**</span></span>|<span data-ttu-id="edead-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="edead-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="edead-121">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="edead-121">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="edead-122">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="edead-122">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edead-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="edead-123">Remarks</span></span>  
 <span data-ttu-id="edead-124">L'elenco di bypass contiene espressioni regolari che descrivono gli URI a cui è <xref:System.Net.WebRequest> possibile accedere direttamente, anziché tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="edead-124">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="edead-125">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="edead-125">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="edead-126">L'espressione regolare "[a-z] + \\ . contoso \\ . com" corrisponde a qualsiasi host nel dominio contoso.com, ma corrisponde anche a qualsiasi host nel dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="edead-126">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="edead-127">Per trovare la corrispondenza solo con un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="edead-127">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="edead-128">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="edead-128">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="edead-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="edead-129">Configuration Files</span></span>  
 <span data-ttu-id="edead-130">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="edead-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="edead-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="edead-131">Example</span></span>  
 <span data-ttu-id="edead-132">Nell'esempio seguente vengono aggiunti due indirizzi all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="edead-132">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="edead-133">Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server i cui indirizzi IP iniziano con 192,168.</span><span class="sxs-lookup"><span data-stu-id="edead-133">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="edead-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="edead-134">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="edead-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="edead-135">Network Settings Schema</span></span>](index.md)
