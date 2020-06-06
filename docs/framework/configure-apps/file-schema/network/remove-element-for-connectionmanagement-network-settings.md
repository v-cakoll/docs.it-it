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
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154738"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="2b550-102">Elemento \<remove> per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2b550-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="2b550-103">Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="2b550-103">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="2b550-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b550-104">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b550-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b550-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2b550-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b550-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b550-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b550-107">Attributes</span></span>  
  
|<span data-ttu-id="2b550-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="2b550-108">**Attribute**</span></span>|<span data-ttu-id="2b550-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2b550-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="2b550-110">Un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="2b550-110">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b550-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b550-111">Child Elements</span></span>  
 <span data-ttu-id="2b550-112">No.</span><span class="sxs-lookup"><span data-stu-id="2b550-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b550-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b550-113">Parent Elements</span></span>  
  
|<span data-ttu-id="2b550-114">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="2b550-114">**Element**</span></span>|<span data-ttu-id="2b550-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2b550-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b550-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="2b550-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="2b550-117">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="2b550-117">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b550-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="2b550-118">Remarks</span></span>  
 <span data-ttu-id="2b550-119">L' `remove` elemento rimuove la voce dell'elenco di gestione connessione per il server specificato.</span><span class="sxs-lookup"><span data-stu-id="2b550-119">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="2b550-120">Il valore dell' `address` attributo deve essere un indirizzo IP o un nome host valido.</span><span class="sxs-lookup"><span data-stu-id="2b550-120">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2b550-121">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="2b550-121">Configuration Files</span></span>  
 <span data-ttu-id="2b550-122">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2b550-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b550-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b550-123">Example</span></span>  
 <span data-ttu-id="2b550-124">Nell'esempio seguente vengono rimosse tutte le voci dell'elenco di gestione connessione per il server `www.adventure-works.com` e quindi viene configurata un'applicazione per l'utilizzo di quattro connessioni al server `www.contoso.com` e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="2b550-124">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b550-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2b550-125">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="2b550-126">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="2b550-126">Network Settings Schema</span></span>](index.md)
