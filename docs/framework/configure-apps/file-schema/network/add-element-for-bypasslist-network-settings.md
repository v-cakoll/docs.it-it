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
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155077"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="34fa1-102">Elemento \<add> per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="34fa1-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="34fa1-103">Aggiunge un indirizzo IP o un nome DNS all'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="34fa1-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="34fa1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34fa1-104">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34fa1-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="34fa1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="34fa1-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="34fa1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34fa1-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="34fa1-107">Attributes</span></span>  
  
|<span data-ttu-id="34fa1-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="34fa1-108">**Attribute**</span></span>|<span data-ttu-id="34fa1-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="34fa1-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="34fa1-110">**address**</span><span class="sxs-lookup"><span data-stu-id="34fa1-110">**address**</span></span>|<span data-ttu-id="34fa1-111">Espressione regolare che descrive un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="34fa1-111">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34fa1-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="34fa1-112">Child Elements</span></span>  
 <span data-ttu-id="34fa1-113">No.</span><span class="sxs-lookup"><span data-stu-id="34fa1-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34fa1-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="34fa1-114">Parent Elements</span></span>  
  
|<span data-ttu-id="34fa1-115">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="34fa1-115">**Element**</span></span>|<span data-ttu-id="34fa1-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="34fa1-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="34fa1-117">BypassList</span><span class="sxs-lookup"><span data-stu-id="34fa1-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="34fa1-118">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="34fa1-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34fa1-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="34fa1-119">Remarks</span></span>  
 <span data-ttu-id="34fa1-120">L' `add` elemento inserisce le espressioni regolari che descrivono gli indirizzi IP o i nomi dei server DNS nell'elenco degli indirizzi che ignorano un server proxy.</span><span class="sxs-lookup"><span data-stu-id="34fa1-120">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="34fa1-121">Il valore dell' `address` attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.</span><span class="sxs-lookup"><span data-stu-id="34fa1-121">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="34fa1-122">È necessario prestare attenzione quando si specifica un'espressione regolare per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="34fa1-122">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="34fa1-123">L'espressione regolare "[a-z] + \\ . contoso \\ . com" corrisponde a qualsiasi host nel dominio contoso.com, ma corrisponde anche a qualsiasi host nel dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="34fa1-123">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="34fa1-124">Per trovare la corrispondenza solo con un host nel dominio contoso.com, usare un ancoraggio ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="34fa1-124">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="34fa1-125">Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="34fa1-125">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="34fa1-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="34fa1-126">Configuration Files</span></span>  
 <span data-ttu-id="34fa1-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="34fa1-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34fa1-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="34fa1-128">Example</span></span>  
 <span data-ttu-id="34fa1-129">Nell'esempio seguente vengono aggiunti due indirizzi all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="34fa1-129">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="34fa1-130">Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server il cui indirizzo IP inizia con 192,168.</span><span class="sxs-lookup"><span data-stu-id="34fa1-130">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34fa1-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="34fa1-131">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="34fa1-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="34fa1-132">Network Settings Schema</span></span>](index.md)
