---
title: Elemento <connectionManagement> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 9f1e382bbbaad2cb95e2c33bbbdfb4c505378c9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154894"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="d197a-102">\<Elemento connectionManagement> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d197a-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="d197a-103">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="d197a-103">Specifies the maximum number of connections to a network host.</span></span>  

<span data-ttu-id="d197a-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d197a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d197a-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d197a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d197a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>connectionManagement**</span><span class="sxs-lookup"><span data-stu-id="d197a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d197a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d197a-107">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d197a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d197a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d197a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d197a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d197a-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="d197a-110">Attributes</span></span>  
 <span data-ttu-id="d197a-111">No.</span><span class="sxs-lookup"><span data-stu-id="d197a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d197a-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d197a-112">Child Elements</span></span>  
  
|<span data-ttu-id="d197a-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d197a-113">**Element**</span></span>|<span data-ttu-id="d197a-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d197a-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d197a-115">aggiungi</span><span class="sxs-lookup"><span data-stu-id="d197a-115">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="d197a-116">Aggiunge un indirizzo IP o nome DNS all'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="d197a-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="d197a-117">Chiaro</span><span class="sxs-lookup"><span data-stu-id="d197a-117">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="d197a-118">Cancella l'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="d197a-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="d197a-119">rimozione</span><span class="sxs-lookup"><span data-stu-id="d197a-119">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="d197a-120">Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="d197a-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d197a-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d197a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d197a-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d197a-122">**Element**</span></span>|<span data-ttu-id="d197a-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d197a-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d197a-124">system.net</span><span class="sxs-lookup"><span data-stu-id="d197a-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d197a-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d197a-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d197a-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d197a-126">Remarks</span></span>  
 <span data-ttu-id="d197a-127">L'elemento `connectionManagement` definisce il numero massimo di connessioni a un server o a un gruppo di server.</span><span class="sxs-lookup"><span data-stu-id="d197a-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d197a-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d197a-128">Configuration Files</span></span>  
 <span data-ttu-id="d197a-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d197a-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d197a-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="d197a-130">Example</span></span>  
 <span data-ttu-id="d197a-131">Nell'esempio seguente un'applicazione viene configurata `www.contoso.com` per l'utilizzo di quattro connessioni al server e di due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="d197a-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d197a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d197a-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="d197a-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d197a-133">Network Settings Schema</span></span>](index.md)
