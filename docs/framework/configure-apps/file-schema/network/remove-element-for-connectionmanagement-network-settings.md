---
title: Elemento <remove> per connectionManagement (impostazioni di rete)
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
ms.openlocfilehash: 8ab7a43fbb3e8df5bb0c99b5947f2fafb362399a
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664036"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="054a0-102">\<rimuovere > elemento per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="054a0-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="054a0-103">Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="054a0-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="054a0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="054a0-104">\<configuration></span></span>  
<span data-ttu-id="054a0-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="054a0-105">\<system.net></span></span>  
<span data-ttu-id="054a0-106">\<> connectionManagement</span><span class="sxs-lookup"><span data-stu-id="054a0-106">\<connectionManagement></span></span>  
<span data-ttu-id="054a0-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="054a0-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="054a0-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="054a0-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="054a0-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="054a0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="054a0-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="054a0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="054a0-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="054a0-111">Attributes</span></span>  
  
|<span data-ttu-id="054a0-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="054a0-112">**Attribute**</span></span>|<span data-ttu-id="054a0-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="054a0-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="054a0-114">Un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="054a0-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="054a0-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="054a0-115">Child Elements</span></span>  
 <span data-ttu-id="054a0-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="054a0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="054a0-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="054a0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="054a0-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="054a0-118">**Element**</span></span>|<span data-ttu-id="054a0-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="054a0-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="054a0-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="054a0-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="054a0-121">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="054a0-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="054a0-122">Note</span><span class="sxs-lookup"><span data-stu-id="054a0-122">Remarks</span></span>  
 <span data-ttu-id="054a0-123">L' `remove` elemento rimuove la voce dell'elenco di gestione connessione per il server specificato.</span><span class="sxs-lookup"><span data-stu-id="054a0-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="054a0-124">Il valore dell' `address` attributo deve essere un indirizzo IP o un nome host valido.</span><span class="sxs-lookup"><span data-stu-id="054a0-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="054a0-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="054a0-125">Configuration Files</span></span>  
 <span data-ttu-id="054a0-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="054a0-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="054a0-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="054a0-127">Example</span></span>  
 <span data-ttu-id="054a0-128">Nell'esempio seguente vengono rimosse tutte le voci dell'elenco di `www.adventure-works.com` gestione connessione per il server e quindi viene configurata un'applicazione `www.contoso.com` per l'utilizzo di quattro connessioni al server e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="054a0-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="054a0-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="054a0-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="054a0-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="054a0-130">Network Settings Schema</span></span>](index.md)
