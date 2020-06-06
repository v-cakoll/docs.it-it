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
ms.openlocfilehash: a76df48a9de084e1121a5e96b22edf7aa3acba23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088477"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="4ee32-102">Elemento \<clear> per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="4ee32-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="4ee32-103">Cancella l'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="4ee32-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="4ee32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ee32-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ee32-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ee32-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4ee32-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ee32-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ee32-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ee32-107">Attributes</span></span>  
 <span data-ttu-id="4ee32-108">No.</span><span class="sxs-lookup"><span data-stu-id="4ee32-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4ee32-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ee32-109">Child Elements</span></span>  
 <span data-ttu-id="4ee32-110">No.</span><span class="sxs-lookup"><span data-stu-id="4ee32-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ee32-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ee32-111">Parent Elements</span></span>  
  
|<span data-ttu-id="4ee32-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="4ee32-112">**Element**</span></span>|<span data-ttu-id="4ee32-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4ee32-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4ee32-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="4ee32-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="4ee32-115">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="4ee32-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ee32-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="4ee32-116">Remarks</span></span>  
 <span data-ttu-id="4ee32-117">L' `clear` elemento Cancella tutte le voci dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="4ee32-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4ee32-118">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4ee32-118">Configuration Files</span></span>  
 <span data-ttu-id="4ee32-119">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4ee32-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ee32-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ee32-120">Example</span></span>  
 <span data-ttu-id="4ee32-121">Nell'esempio seguente viene cancellato l'elenco di gestione connessione, quindi vengono aggiunte nuove voci di gestione connessione per il server `www.contoso.com` e tutti gli altri host di rete.</span><span class="sxs-lookup"><span data-stu-id="4ee32-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ee32-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4ee32-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="4ee32-123">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="4ee32-123">Network Settings Schema</span></span>](index.md)
