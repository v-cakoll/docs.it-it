---
title: '&lt;system.Net&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 25663774c639e9fea13ced54a9aa7f456922fa1a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47209938"
---
# <a name="ltsystemnetgt-element-network-settings"></a><span data-ttu-id="9678b-102">&lt;system.Net&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9678b-102">&lt;system.Net&gt; Element (Network Settings)</span></span>
<span data-ttu-id="9678b-103">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9678b-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="9678b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9678b-104">\<configuration></span></span>  
<span data-ttu-id="9678b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9678b-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9678b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9678b-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9678b-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9678b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9678b-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9678b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9678b-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="9678b-109">Attributes</span></span>  
 <span data-ttu-id="9678b-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9678b-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9678b-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9678b-111">Child Elements</span></span>  
  
|<span data-ttu-id="9678b-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="9678b-112">**Element**</span></span>|<span data-ttu-id="9678b-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9678b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9678b-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="9678b-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="9678b-115">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="9678b-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="9678b-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="9678b-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="9678b-117">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="9678b-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="9678b-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="9678b-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="9678b-119">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="9678b-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="9678b-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="9678b-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="9678b-121">Consente di configurare le opzioni di invio della posta elettronica SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="9678b-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="9678b-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="9678b-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="9678b-123">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="9678b-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="9678b-124">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="9678b-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="9678b-125">Configura le opzioni di rete di base per le classi di <xref:System.Net> e relativi spazi dei nomi figlio.</span><span class="sxs-lookup"><span data-stu-id="9678b-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="9678b-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="9678b-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="9678b-127">Specifica i moduli da utilizzare per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="9678b-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9678b-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9678b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="9678b-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="9678b-129">**Element**</span></span>|<span data-ttu-id="9678b-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9678b-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9678b-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="9678b-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="9678b-132">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9678b-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9678b-133">Note</span><span class="sxs-lookup"><span data-stu-id="9678b-133">Remarks</span></span>  
 <span data-ttu-id="9678b-134">Il [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) elemento contiene impostazioni per le classi di <xref:System.Net> e relativi spazi dei nomi figlio.</span><span class="sxs-lookup"><span data-stu-id="9678b-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="9678b-135">Le impostazioni di configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, il server proxy e i moduli di richiesta di Internet per la ricezione di informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="9678b-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9678b-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="9678b-136">Example</span></span>  
 <span data-ttu-id="9678b-137">Nell'esempio seguente mostra una configurazione tipica usata da <xref:System.Net> classi.</span><span class="sxs-lookup"><span data-stu-id="9678b-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9678b-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9678b-138">See Also</span></span>  
 [<span data-ttu-id="9678b-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9678b-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
