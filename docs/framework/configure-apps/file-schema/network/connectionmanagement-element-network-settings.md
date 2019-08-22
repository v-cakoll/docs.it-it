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
ms.openlocfilehash: faaba1b9de302ed916ad1a81c7e80b3fb5a67170
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664163"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="0c8ac-102">\<Elemento > connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0c8ac-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="0c8ac-103">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="0c8ac-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0c8ac-104">\<configuration></span></span>  
<span data-ttu-id="0c8ac-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0c8ac-105">\<system.net></span></span>  
<span data-ttu-id="0c8ac-106">\<> connectionManagement</span><span class="sxs-lookup"><span data-stu-id="0c8ac-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8ac-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c8ac-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c8ac-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0c8ac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0c8ac-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c8ac-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0c8ac-110">Attributes</span></span>  
 <span data-ttu-id="0c8ac-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c8ac-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0c8ac-112">Child Elements</span></span>  
  
|<span data-ttu-id="0c8ac-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0c8ac-113">**Element**</span></span>|<span data-ttu-id="0c8ac-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0c8ac-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0c8ac-115">add</span><span class="sxs-lookup"><span data-stu-id="0c8ac-115">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="0c8ac-116">Aggiunge un indirizzo IP o nome DNS all'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="0c8ac-117">clear</span><span class="sxs-lookup"><span data-stu-id="0c8ac-117">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="0c8ac-118">Cancella l'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="0c8ac-119">remove</span><span class="sxs-lookup"><span data-stu-id="0c8ac-119">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="0c8ac-120">Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c8ac-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0c8ac-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0c8ac-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0c8ac-122">**Element**</span></span>|<span data-ttu-id="0c8ac-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0c8ac-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0c8ac-124">system.net</span><span class="sxs-lookup"><span data-stu-id="0c8ac-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="0c8ac-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c8ac-126">Note</span><span class="sxs-lookup"><span data-stu-id="0c8ac-126">Remarks</span></span>  
 <span data-ttu-id="0c8ac-127">L' `connectionManagement` elemento definisce il numero massimo di connessioni a un server o a un gruppo di server.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0c8ac-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0c8ac-128">Configuration Files</span></span>  
 <span data-ttu-id="0c8ac-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0c8ac-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c8ac-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c8ac-130">Example</span></span>  
 <span data-ttu-id="0c8ac-131">Nell'esempio seguente viene configurata un'applicazione per l'utilizzo di quattro `www.contoso.com` connessioni al server e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="0c8ac-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c8ac-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c8ac-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="0c8ac-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0c8ac-133">Network Settings Schema</span></span>](index.md)
