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
ms.openlocfilehash: cbafd29be6855cbb95d17388791ba152230295cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697848"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="59b1e-102">Elemento > \<remove per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="59b1e-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="59b1e-103">Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="59b1e-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
[<span data-ttu-id="59b1e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="59b1e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="59b1e-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="59b1e-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="59b1e-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="59b1e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="59b1e-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="59b1e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b1e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59b1e-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59b1e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="59b1e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59b1e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="59b1e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59b1e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="59b1e-111">Attributes</span></span>  
  
|<span data-ttu-id="59b1e-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="59b1e-112">**Attribute**</span></span>|<span data-ttu-id="59b1e-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="59b1e-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="59b1e-114">Un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="59b1e-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59b1e-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="59b1e-115">Child Elements</span></span>  
 <span data-ttu-id="59b1e-116">No.</span><span class="sxs-lookup"><span data-stu-id="59b1e-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59b1e-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="59b1e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59b1e-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="59b1e-118">**Element**</span></span>|<span data-ttu-id="59b1e-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="59b1e-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="59b1e-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="59b1e-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="59b1e-121">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="59b1e-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59b1e-122">Note</span><span class="sxs-lookup"><span data-stu-id="59b1e-122">Remarks</span></span>  
 <span data-ttu-id="59b1e-123">L'elemento `remove` rimuove la voce dell'elenco di gestione connessione per il server specificato.</span><span class="sxs-lookup"><span data-stu-id="59b1e-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="59b1e-124">Il valore dell'attributo `address` deve essere un indirizzo IP o un nome host valido.</span><span class="sxs-lookup"><span data-stu-id="59b1e-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="59b1e-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="59b1e-125">Configuration Files</span></span>  
 <span data-ttu-id="59b1e-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="59b1e-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b1e-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="59b1e-127">Example</span></span>  
 <span data-ttu-id="59b1e-128">Nell'esempio seguente vengono rimosse tutte le voci dell'elenco di gestione connessione per il server `www.adventure-works.com` e quindi viene configurata un'applicazione per l'utilizzo di quattro connessioni al server `www.contoso.com` e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="59b1e-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59b1e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59b1e-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="59b1e-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="59b1e-130">Network Settings Schema</span></span>](index.md)
