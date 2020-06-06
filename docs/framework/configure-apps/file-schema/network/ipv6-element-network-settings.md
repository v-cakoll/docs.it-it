---
title: Elemento <ipv6> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088128"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="86f3f-102">Elemento \<ipv6> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="86f3f-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="86f3f-103">Abilita le risposte protocollo Internet versione 6 (IPv6) dai membri obsoleti della <xref:System.Net.Dns> classe.</span><span class="sxs-lookup"><span data-stu-id="86f3f-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="86f3f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86f3f-104">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86f3f-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="86f3f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="86f3f-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="86f3f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86f3f-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="86f3f-107">Attributes</span></span>  
  
|<span data-ttu-id="86f3f-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="86f3f-108">**Attribute**</span></span>|<span data-ttu-id="86f3f-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="86f3f-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="86f3f-110">Specifica se i membri della <xref:System.Net.Dns> classe restituiscono indirizzi IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="86f3f-110">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="86f3f-111">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="86f3f-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86f3f-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="86f3f-112">Child Elements</span></span>  
 <span data-ttu-id="86f3f-113">No.</span><span class="sxs-lookup"><span data-stu-id="86f3f-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86f3f-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="86f3f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="86f3f-115">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="86f3f-115">**Element**</span></span>|<span data-ttu-id="86f3f-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="86f3f-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="86f3f-117">impostazioni</span><span class="sxs-lookup"><span data-stu-id="86f3f-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="86f3f-118">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="86f3f-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86f3f-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="86f3f-119">Remarks</span></span>  
 <span data-ttu-id="86f3f-120">Questa impostazione Abilita il supporto IPv6 per i membri obsoleti della <xref:System.Net.Dns> classe: <xref:System.Net.Dns.BeginGetHostByName%2A> ,, <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndGetHostByName%2A> , <xref:System.Net.Dns.EndResolve%2A> , <xref:System.Net.Dns.GetHostByAddress%2A> , <xref:System.Net.Dns.GetHostByName%2A> e <xref:System.Net.Dns.Resolve%2A> .</span><span class="sxs-lookup"><span data-stu-id="86f3f-120">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="86f3f-121">Per gli altri membri dello <xref:System.Net?displayProperty=nameWithType> spazio dei nomi, è possibile che vengano restituiti indirizzi IPv6 se IPv6 è abilitato nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="86f3f-121">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="86f3f-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="86f3f-122">Configuration Files</span></span>  
 <span data-ttu-id="86f3f-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="86f3f-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="86f3f-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="86f3f-124">Example</span></span>  
 <span data-ttu-id="86f3f-125">Nell'esempio seguente viene illustrato come abilitare il supporto IPv6 per la <xref:System.Net.Dns> classe.</span><span class="sxs-lookup"><span data-stu-id="86f3f-125">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86f3f-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="86f3f-126">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="86f3f-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="86f3f-127">Network Settings Schema</span></span>](index.md)
