---
title: Elemento <add> per connectionManagement (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 608c591b910252dd60950bf2aa7565d6df04d5fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664222"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="ec7e3-102">\<aggiungere > elemento per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ec7e3-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="ec7e3-103">Aggiunge un indirizzo IP o nome DNS all'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-103">Adds an IP address or DNS name to the connection management list.</span></span>  
  
 <span data-ttu-id="ec7e3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ec7e3-104">\<configuration></span></span>  
<span data-ttu-id="ec7e3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ec7e3-105">\<system.net></span></span>  
<span data-ttu-id="ec7e3-106">\<> connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ec7e3-106">\<connectionManagement></span></span>  
<span data-ttu-id="ec7e3-107">\<add></span><span class="sxs-lookup"><span data-stu-id="ec7e3-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7e3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec7e3-108">Syntax</span></span>  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec7e3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ec7e3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ec7e3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec7e3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ec7e3-111">Attributes</span></span>  
  
|<span data-ttu-id="ec7e3-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="ec7e3-112">**Attribute**</span></span>|<span data-ttu-id="ec7e3-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ec7e3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="ec7e3-114">Stringa che descrive un indirizzo IP o un nome DNS.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="ec7e3-115">Numero massimo di connessioni consentite verso un server.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="ec7e3-116">Se non impostato, il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec7e3-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ec7e3-117">Child Elements</span></span>  
 <span data-ttu-id="ec7e3-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec7e3-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ec7e3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ec7e3-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ec7e3-120">**Element**</span></span>|<span data-ttu-id="ec7e3-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ec7e3-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ec7e3-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ec7e3-122">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="ec7e3-123">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec7e3-124">Note</span><span class="sxs-lookup"><span data-stu-id="ec7e3-124">Remarks</span></span>  
 <span data-ttu-id="ec7e3-125">Il valore dell'attributo `address` deve essere un'espressione regolare valida o un asterisco per indicare tutte le connessioni oppure una stringa nel formato `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="ec7e3-126">Se l'URI passato a qualsiasi API HTTP contiene Unicode, il nome verrà convertito internamente usando <xref:System.Uri.DnsSafeHost%2A>, il che potrebbe restituire una stringa Unicode (il comportamento dipende dalla configurazione IDN corrente).</span><span class="sxs-lookup"><span data-stu-id="ec7e3-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ec7e3-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ec7e3-127">Configuration Files</span></span>  
 <span data-ttu-id="ec7e3-128">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ec7e3-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec7e3-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec7e3-129">Example</span></span>  
 <span data-ttu-id="ec7e3-130">Nell'esempio seguente viene configurata un'applicazione per l'utilizzo di quattro `www.contoso.com` connessioni al server e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="ec7e3-130">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec7e3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec7e3-131">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="ec7e3-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ec7e3-132">Network Settings Schema</span></span>](index.md)
