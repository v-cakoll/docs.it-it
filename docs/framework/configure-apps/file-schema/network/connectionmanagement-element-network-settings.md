---
title: Elemento <connectionManagement> (impostazioni di rete)
description: L' <connectionManagement> elemento impostazioni di rete specifica il numero massimo di connessioni a un host di rete nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 4ceec06fb0e21bfae67038efe0ce758d3d5b708f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504615"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="fb5cd-103">Elemento \<connectionManagement> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="fb5cd-103">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="fb5cd-104">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-104">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="fb5cd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb5cd-105">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb5cd-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fb5cd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fb5cd-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb5cd-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="fb5cd-108">Attributes</span></span>  
 <span data-ttu-id="fb5cd-109">No.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb5cd-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fb5cd-110">Child Elements</span></span>  
  
|<span data-ttu-id="fb5cd-111">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fb5cd-111">**Element**</span></span>|<span data-ttu-id="fb5cd-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fb5cd-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fb5cd-113">add</span><span class="sxs-lookup"><span data-stu-id="fb5cd-113">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="fb5cd-114">Aggiunge un indirizzo IP o nome DNS all'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-114">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="fb5cd-115">deselezionare</span><span class="sxs-lookup"><span data-stu-id="fb5cd-115">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="fb5cd-116">Cancella l'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-116">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="fb5cd-117">remove</span><span class="sxs-lookup"><span data-stu-id="fb5cd-117">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="fb5cd-118">Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-118">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb5cd-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fb5cd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fb5cd-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fb5cd-120">**Element**</span></span>|<span data-ttu-id="fb5cd-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fb5cd-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fb5cd-122">system.net</span><span class="sxs-lookup"><span data-stu-id="fb5cd-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="fb5cd-123">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb5cd-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fb5cd-124">Remarks</span></span>  
 <span data-ttu-id="fb5cd-125">L' `connectionManagement` elemento definisce il numero massimo di connessioni a un server o a un gruppo di server.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-125">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fb5cd-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="fb5cd-126">Configuration Files</span></span>  
 <span data-ttu-id="fb5cd-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fb5cd-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb5cd-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb5cd-128">Example</span></span>  
 <span data-ttu-id="fb5cd-129">Nell'esempio seguente viene configurata un'applicazione per l'utilizzo di quattro connessioni al server `www.contoso.com` e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="fb5cd-129">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb5cd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb5cd-130">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="fb5cd-131">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="fb5cd-131">Network Settings Schema</span></span>](index.md)
