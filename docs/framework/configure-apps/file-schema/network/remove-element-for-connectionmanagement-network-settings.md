---
title: '&lt;rimuovere&gt; (elemento) per connectionManagement (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d249cc412a1638e62b57b4976adc23fdf8f36e80
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085537"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="ef4cd-102">&lt;rimuovere&gt; (elemento) per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ef4cd-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="ef4cd-103">Rimuove un indirizzo IP o nome DNS dall'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="ef4cd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ef4cd-104">\<configuration></span></span>  
<span data-ttu-id="ef4cd-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ef4cd-105">\<system.net></span></span>  
<span data-ttu-id="ef4cd-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="ef4cd-106">\<connectionManagement></span></span>  
<span data-ttu-id="ef4cd-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="ef4cd-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef4cd-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef4cd-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef4cd-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef4cd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ef4cd-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef4cd-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef4cd-111">Attributes</span></span>  
  
|<span data-ttu-id="ef4cd-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="ef4cd-112">**Attribute**</span></span>|<span data-ttu-id="ef4cd-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ef4cd-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="ef4cd-114">Un indirizzo IP o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef4cd-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef4cd-115">Child Elements</span></span>  
 <span data-ttu-id="ef4cd-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef4cd-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef4cd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ef4cd-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ef4cd-118">**Element**</span></span>|<span data-ttu-id="ef4cd-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ef4cd-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ef4cd-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ef4cd-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="ef4cd-121">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef4cd-122">Note</span><span class="sxs-lookup"><span data-stu-id="ef4cd-122">Remarks</span></span>  
 <span data-ttu-id="ef4cd-123">Il `remove` elemento rimuove la voce di elenco di gestione connessione per il server specificato.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="ef4cd-124">Il valore della `address` attributo deve essere un nome host o indirizzo IP valido.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ef4cd-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ef4cd-125">Configuration Files</span></span>  
 <span data-ttu-id="ef4cd-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ef4cd-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef4cd-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef4cd-127">Example</span></span>  
 <span data-ttu-id="ef4cd-128">Nell'esempio seguente rimuove tutte le voci di elenco di gestione connessione per www.adventure-works.com il server e quindi configura un'applicazione per usare quattro connessioni al server www.contoso.com e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef4cd-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef4cd-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="ef4cd-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ef4cd-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
