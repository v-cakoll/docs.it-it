---
title: <clear> Elemento per bypasslist (impostazioni di rete)
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
ms.openlocfilehash: 7499d15f1d57887ffc3e78b83ed686c0c0f46cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203522"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="ce787-102">\<Cancella > (elemento) per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ce787-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="ce787-103">Cancella l'elenco proxy da ignorare.</span><span class="sxs-lookup"><span data-stu-id="ce787-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="ce787-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce787-104">\<configuration></span></span>  
<span data-ttu-id="ce787-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ce787-105">\<system.net></span></span>  
<span data-ttu-id="ce787-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="ce787-106">\<defaultProxy></span></span>  
<span data-ttu-id="ce787-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="ce787-107">\<bypasslist></span></span>  
<span data-ttu-id="ce787-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="ce787-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce787-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce787-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce787-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ce787-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ce787-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ce787-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce787-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ce787-112">Attributes</span></span>  
 <span data-ttu-id="ce787-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ce787-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce787-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ce787-114">Child Elements</span></span>  
 <span data-ttu-id="ce787-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ce787-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce787-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ce787-116">Parent Elements</span></span>  
  
|**<span data-ttu-id="ce787-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce787-117">Element</span></span>**|**<span data-ttu-id="ce787-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce787-118">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="ce787-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="ce787-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="ce787-120">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.</span><span class="sxs-lookup"><span data-stu-id="ce787-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce787-121">Note</span><span class="sxs-lookup"><span data-stu-id="ce787-121">Remarks</span></span>  
 <span data-ttu-id="ce787-122">Il `clear` elemento cancella tutte le voci dell'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="ce787-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ce787-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ce787-123">Configuration Files</span></span>  
 <span data-ttu-id="ce787-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ce787-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce787-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce787-125">Example</span></span>  
 <span data-ttu-id="ce787-126">Nell'esempio seguente cancella l'elenco di esclusione e quindi aggiunge due indirizzi all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="ce787-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="ce787-127">Il primo consente di ignorare il proxy per tutti i server nel dominio contoso.com. il secondo consente di ignorare il proxy per tutti i server il cui indirizzo IP inizia con 192.168.</span><span class="sxs-lookup"><span data-stu-id="ce787-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce787-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce787-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ce787-129">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ce787-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
