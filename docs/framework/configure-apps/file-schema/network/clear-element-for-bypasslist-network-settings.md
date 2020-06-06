---
title: Elemento <clear> per bypasslist (impostazioni di rete)
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
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154933"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="89b36-102">Elemento \<clear> per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="89b36-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="89b36-103">Cancella l'elenco di bypass del proxy.</span><span class="sxs-lookup"><span data-stu-id="89b36-103">Clears the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="89b36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89b36-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89b36-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89b36-105">Attributes and Elements</span></span>  
 <span data-ttu-id="89b36-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89b36-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89b36-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="89b36-107">Attributes</span></span>  
 <span data-ttu-id="89b36-108">No.</span><span class="sxs-lookup"><span data-stu-id="89b36-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89b36-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89b36-109">Child Elements</span></span>  
 <span data-ttu-id="89b36-110">No.</span><span class="sxs-lookup"><span data-stu-id="89b36-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89b36-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89b36-111">Parent Elements</span></span>  
  
|<span data-ttu-id="89b36-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="89b36-112">**Element**</span></span>|<span data-ttu-id="89b36-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="89b36-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="89b36-114">BypassList</span><span class="sxs-lookup"><span data-stu-id="89b36-114">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="89b36-115">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.</span><span class="sxs-lookup"><span data-stu-id="89b36-115">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89b36-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="89b36-116">Remarks</span></span>  
 <span data-ttu-id="89b36-117">L' `clear` elemento Cancella tutte le voci dall'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="89b36-117">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="89b36-118">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="89b36-118">Configuration Files</span></span>  
 <span data-ttu-id="89b36-119">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="89b36-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89b36-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="89b36-120">Example</span></span>  
 <span data-ttu-id="89b36-121">Nell'esempio seguente viene cancellato l'elenco di bypass, quindi vengono aggiunti due indirizzi all'elenco di bypass.</span><span class="sxs-lookup"><span data-stu-id="89b36-121">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="89b36-122">Il primo ignora il proxy per tutti i server nel dominio contoso.com. il secondo ignora il proxy per tutti i server il cui indirizzo IP inizia con 192,168.</span><span class="sxs-lookup"><span data-stu-id="89b36-122">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="89b36-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="89b36-123">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="89b36-124">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="89b36-124">Network Settings Schema</span></span>](index.md)
