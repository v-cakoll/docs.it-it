---
title: '&lt;system.Net&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 6140a5a66d39cbee3c2a8477dcab88aaa717e745
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemnetgt-element-network-settings"></a><span data-ttu-id="1c539-102">&lt;system.Net&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="1c539-102">&lt;system.Net&gt; Element (Network Settings)</span></span>
<span data-ttu-id="1c539-103">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c539-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="1c539-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1c539-104">\<configuration></span></span>  
<span data-ttu-id="1c539-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="1c539-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c539-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c539-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c539-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1c539-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1c539-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1c539-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c539-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="1c539-109">Attributes</span></span>  
 <span data-ttu-id="1c539-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1c539-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c539-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1c539-111">Child Elements</span></span>  
  
|<span data-ttu-id="1c539-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1c539-112">**Element**</span></span>|<span data-ttu-id="1c539-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1c539-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1c539-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="1c539-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="1c539-115">Specifica i moduli utilizzati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="1c539-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="1c539-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="1c539-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="1c539-117">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="1c539-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="1c539-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="1c539-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="1c539-119">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="1c539-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="1c539-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="1c539-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="1c539-121">Configura posta elettronica SMTP Simple Mail Transport Protocol (), le opzioni di invio.</span><span class="sxs-lookup"><span data-stu-id="1c539-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="1c539-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="1c539-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="1c539-123">Controlla il meccanismo di memorizzazione nella cache delle richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="1c539-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="1c539-124">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="1c539-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="1c539-125">Configura opzioni di rete di base per le classi di <xref:System.Net> e spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="1c539-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="1c539-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="1c539-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="1c539-127">Specifica i moduli da utilizzare per richiedere informazioni dagli host Internet.</span><span class="sxs-lookup"><span data-stu-id="1c539-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c539-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1c539-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1c539-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1c539-129">**Element**</span></span>|<span data-ttu-id="1c539-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1c539-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1c539-131">configurazione</span><span class="sxs-lookup"><span data-stu-id="1c539-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="1c539-132">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c539-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c539-133">Note</span><span class="sxs-lookup"><span data-stu-id="1c539-133">Remarks</span></span>  
 <span data-ttu-id="1c539-134">Il [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) elemento contiene impostazioni per le classi di <xref:System.Net> e spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="1c539-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="1c539-135">Le impostazioni di configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, server proxy e i moduli di richiesta Internet per ricevere informazioni dagli host Internet.</span><span class="sxs-lookup"><span data-stu-id="1c539-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c539-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c539-136">Example</span></span>  
 <span data-ttu-id="1c539-137">Nell'esempio seguente viene illustrata una configurazione tipica utilizzata da <xref:System.Net> classi.</span><span class="sxs-lookup"><span data-stu-id="1c539-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1c539-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c539-138">See Also</span></span>  
 [<span data-ttu-id="1c539-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="1c539-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
