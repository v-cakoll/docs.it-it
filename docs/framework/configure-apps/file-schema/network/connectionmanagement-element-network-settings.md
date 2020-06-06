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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154894"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="c2e20-102">Elemento \<connectionManagement> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c2e20-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="c2e20-103">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="c2e20-103">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="c2e20-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2e20-104">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2e20-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c2e20-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c2e20-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c2e20-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2e20-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c2e20-107">Attributes</span></span>  
 <span data-ttu-id="c2e20-108">No.</span><span class="sxs-lookup"><span data-stu-id="c2e20-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c2e20-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c2e20-109">Child Elements</span></span>  
  
|<span data-ttu-id="c2e20-110">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c2e20-110">**Element**</span></span>|<span data-ttu-id="c2e20-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c2e20-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c2e20-112">add</span><span class="sxs-lookup"><span data-stu-id="c2e20-112">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="c2e20-113">Aggiunge un indirizzo IP o nome DNS all'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="c2e20-113">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="c2e20-114">deselezionare</span><span class="sxs-lookup"><span data-stu-id="c2e20-114">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="c2e20-115">Cancella l'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="c2e20-115">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="c2e20-116">remove</span><span class="sxs-lookup"><span data-stu-id="c2e20-116">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="c2e20-117">Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="c2e20-117">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2e20-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c2e20-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c2e20-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c2e20-119">**Element**</span></span>|<span data-ttu-id="c2e20-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c2e20-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c2e20-121">system.net</span><span class="sxs-lookup"><span data-stu-id="c2e20-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="c2e20-122">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2e20-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2e20-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="c2e20-123">Remarks</span></span>  
 <span data-ttu-id="c2e20-124">L' `connectionManagement` elemento definisce il numero massimo di connessioni a un server o a un gruppo di server.</span><span class="sxs-lookup"><span data-stu-id="c2e20-124">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c2e20-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c2e20-125">Configuration Files</span></span>  
 <span data-ttu-id="c2e20-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c2e20-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2e20-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2e20-127">Example</span></span>  
 <span data-ttu-id="c2e20-128">Nell'esempio seguente viene configurata un'applicazione per l'utilizzo di quattro connessioni al server `www.contoso.com` e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="c2e20-128">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c2e20-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c2e20-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="c2e20-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c2e20-130">Network Settings Schema</span></span>](index.md)
