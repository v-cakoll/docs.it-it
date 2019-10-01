---
title: Elemento <clear> per connectionManagement (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: 17b380b12977423669fd413132d69a3082daca41
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698366"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="07052-102">Elemento > \<clear per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="07052-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="07052-103">Cancella l'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="07052-103">Clears the connection management list.</span></span>  
  
[<span data-ttu-id="07052-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="07052-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="07052-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="07052-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="07052-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="07052-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="07052-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="07052-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07052-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07052-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07052-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="07052-109">Attributes and Elements</span></span>  
 <span data-ttu-id="07052-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="07052-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07052-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="07052-111">Attributes</span></span>  
 <span data-ttu-id="07052-112">No.</span><span class="sxs-lookup"><span data-stu-id="07052-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07052-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="07052-113">Child Elements</span></span>  
 <span data-ttu-id="07052-114">No.</span><span class="sxs-lookup"><span data-stu-id="07052-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07052-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="07052-115">Parent Elements</span></span>  
  
|<span data-ttu-id="07052-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="07052-116">**Element**</span></span>|<span data-ttu-id="07052-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="07052-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="07052-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="07052-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="07052-119">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="07052-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07052-120">Note</span><span class="sxs-lookup"><span data-stu-id="07052-120">Remarks</span></span>  
 <span data-ttu-id="07052-121">L'elemento `clear` cancella tutte le voci dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="07052-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="07052-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="07052-122">Configuration Files</span></span>  
 <span data-ttu-id="07052-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="07052-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07052-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="07052-124">Example</span></span>  
 <span data-ttu-id="07052-125">Nell'esempio seguente viene cancellato l'elenco di gestione connessione, quindi vengono aggiunte nuove voci di gestione connessione per il server `www.contoso.com` e tutti gli altri host di rete.</span><span class="sxs-lookup"><span data-stu-id="07052-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="07052-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07052-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="07052-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="07052-127">Network Settings Schema</span></span>](index.md)
