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
ms.openlocfilehash: 82e022e28d3559791be3236fb80081807426a456
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192538"
---
# <a name="ltsystemnetgt-element-network-settings"></a><span data-ttu-id="88323-102">&lt;system.Net&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="88323-102">&lt;system.Net&gt; Element (Network Settings)</span></span>
<span data-ttu-id="88323-103">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88323-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="88323-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="88323-104">\<configuration></span></span>  
<span data-ttu-id="88323-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="88323-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88323-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88323-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88323-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="88323-107">Attributes and Elements</span></span>  
 <span data-ttu-id="88323-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="88323-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88323-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="88323-109">Attributes</span></span>  
 <span data-ttu-id="88323-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="88323-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88323-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="88323-111">Child Elements</span></span>  
  
|<span data-ttu-id="88323-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="88323-112">**Element**</span></span>|<span data-ttu-id="88323-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="88323-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="88323-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="88323-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="88323-115">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="88323-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="88323-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="88323-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="88323-117">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="88323-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="88323-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="88323-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="88323-119">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="88323-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="88323-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="88323-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="88323-121">Consente di configurare le opzioni di invio della posta elettronica SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="88323-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="88323-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="88323-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="88323-123">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="88323-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="88323-124">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="88323-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="88323-125">Configura le opzioni di rete di base per le classi di <xref:System.Net> e relativi spazi dei nomi figlio.</span><span class="sxs-lookup"><span data-stu-id="88323-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="88323-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="88323-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="88323-127">Specifica i moduli da utilizzare per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="88323-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88323-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="88323-128">Parent Elements</span></span>  
  
|<span data-ttu-id="88323-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="88323-129">**Element**</span></span>|<span data-ttu-id="88323-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="88323-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="88323-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="88323-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="88323-132">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="88323-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88323-133">Note</span><span class="sxs-lookup"><span data-stu-id="88323-133">Remarks</span></span>  
 <span data-ttu-id="88323-134">Il [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) elemento contiene impostazioni per le classi di <xref:System.Net> e relativi spazi dei nomi figlio.</span><span class="sxs-lookup"><span data-stu-id="88323-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="88323-135">Le impostazioni di configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, il server proxy e i moduli di richiesta di Internet per la ricezione di informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="88323-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88323-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="88323-136">Example</span></span>  
 <span data-ttu-id="88323-137">Nell'esempio seguente mostra una configurazione tipica usata da <xref:System.Net> classi.</span><span class="sxs-lookup"><span data-stu-id="88323-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88323-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88323-138">See Also</span></span>  
- [<span data-ttu-id="88323-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="88323-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
