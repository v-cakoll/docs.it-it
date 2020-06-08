---
title: Elemento <system.Net> (impostazioni di rete)
description: L'elemento impostazioni di rete <system.Net> contiene le impostazioni che specificano il modo in cui il .NET Framework si connette alle opzioni di rete nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 9f18c7a3586948c03391d609f437e216a91bc27f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504485"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="2554a-103">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2554a-103">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="2554a-104">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2554a-104">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="2554a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2554a-105">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2554a-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2554a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2554a-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2554a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2554a-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="2554a-108">Attributes</span></span>  
 <span data-ttu-id="2554a-109">No.</span><span class="sxs-lookup"><span data-stu-id="2554a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2554a-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2554a-110">Child Elements</span></span>  
  
|<span data-ttu-id="2554a-111">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="2554a-111">**Element**</span></span>|<span data-ttu-id="2554a-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2554a-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2554a-113">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="2554a-113">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="2554a-114">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="2554a-114">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="2554a-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="2554a-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="2554a-116">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="2554a-116">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="2554a-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2554a-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2554a-118">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2554a-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="2554a-119">mailSettings</span><span class="sxs-lookup"><span data-stu-id="2554a-119">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="2554a-120">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="2554a-120">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="2554a-121">requestCaching</span><span class="sxs-lookup"><span data-stu-id="2554a-121">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="2554a-122">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="2554a-122">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="2554a-123">impostazioni</span><span class="sxs-lookup"><span data-stu-id="2554a-123">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="2554a-124">Configura le opzioni di rete di base per le classi in <xref:System.Net> e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="2554a-124">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="2554a-125">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="2554a-125">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="2554a-126">Specifica i moduli da usare per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="2554a-126">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2554a-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2554a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2554a-128">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="2554a-128">**Element**</span></span>|<span data-ttu-id="2554a-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2554a-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2554a-130">configurazione</span><span class="sxs-lookup"><span data-stu-id="2554a-130">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="2554a-131">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2554a-131">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2554a-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2554a-132">Remarks</span></span>  
 <span data-ttu-id="2554a-133">L' [\<system.net>](system-net-element-network-settings.md) elemento contiene le impostazioni per le classi in <xref:System.Net> e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="2554a-133">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="2554a-134">Le impostazioni configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, il server proxy e i moduli di richiesta Internet per ricevere informazioni dagli host Internet.</span><span class="sxs-lookup"><span data-stu-id="2554a-134">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2554a-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="2554a-135">Example</span></span>  
 <span data-ttu-id="2554a-136">Nell'esempio seguente viene illustrata una configurazione tipica utilizzata dalle <xref:System.Net> classi.</span><span class="sxs-lookup"><span data-stu-id="2554a-136">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2554a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2554a-137">See also</span></span>

- [<span data-ttu-id="2554a-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="2554a-138">Network Settings Schema</span></span>](index.md)
