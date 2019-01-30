---
title: Elemento <remove> per connectionManagement (Impostazioni di rete)
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
ms.openlocfilehash: 62f7793c8f25f4803e881e2f183c99c62000ca23
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270514"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="e9074-102">\<rimuovere > (elemento) per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e9074-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="e9074-103">Rimuove un indirizzo IP o nome DNS dall'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="e9074-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="e9074-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9074-104">\<configuration></span></span>  
<span data-ttu-id="e9074-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e9074-105">\<system.net></span></span>  
<span data-ttu-id="e9074-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="e9074-106">\<connectionManagement></span></span>  
<span data-ttu-id="e9074-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="e9074-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9074-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9074-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9074-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9074-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9074-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9074-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9074-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9074-111">Attributes</span></span>  
  
|<span data-ttu-id="e9074-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="e9074-112">**Attribute**</span></span>|<span data-ttu-id="e9074-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e9074-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="e9074-114">Un indirizzo IP o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="e9074-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9074-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9074-115">Child Elements</span></span>  
 <span data-ttu-id="e9074-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e9074-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9074-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9074-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e9074-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e9074-118">**Element**</span></span>|<span data-ttu-id="e9074-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e9074-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e9074-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="e9074-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="e9074-121">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="e9074-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9074-122">Note</span><span class="sxs-lookup"><span data-stu-id="e9074-122">Remarks</span></span>  
 <span data-ttu-id="e9074-123">Il `remove` elemento rimuove la voce di elenco di gestione connessione per il server specificato.</span><span class="sxs-lookup"><span data-stu-id="e9074-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="e9074-124">Il valore della `address` attributo deve essere un nome host o indirizzo IP valido.</span><span class="sxs-lookup"><span data-stu-id="e9074-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e9074-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e9074-125">Configuration Files</span></span>  
 <span data-ttu-id="e9074-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e9074-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9074-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9074-127">Example</span></span>  
 <span data-ttu-id="e9074-128">L'esempio seguente rimuove tutte le voci di elenco di gestione connessione per il server `www.adventure-works.com` e quindi configura un'applicazione di usare quattro connessioni al server `www.contoso.com` e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="e9074-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9074-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9074-129">See also</span></span>
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="e9074-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e9074-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
