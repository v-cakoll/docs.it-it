---
title: Elemento <system.Net> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 810e942394c75c192e4423afe4c674ef3a2b9900
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697498"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="0edf6-102">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0edf6-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="0edf6-103">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0edf6-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="0edf6-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0edf6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="0edf6-105">&nbsp; @ no__t-1 **@no__t -3System. net >**</span><span class="sxs-lookup"><span data-stu-id="0edf6-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0edf6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0edf6-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0edf6-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0edf6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0edf6-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0edf6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0edf6-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="0edf6-109">Attributes</span></span>  
 <span data-ttu-id="0edf6-110">No.</span><span class="sxs-lookup"><span data-stu-id="0edf6-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0edf6-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0edf6-111">Child Elements</span></span>  
  
|<span data-ttu-id="0edf6-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0edf6-112">**Element**</span></span>|<span data-ttu-id="0edf6-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0edf6-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0edf6-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="0edf6-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="0edf6-115">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="0edf6-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="0edf6-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="0edf6-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="0edf6-117">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="0edf6-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="0edf6-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="0edf6-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="0edf6-119">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="0edf6-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="0edf6-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="0edf6-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="0edf6-121">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="0edf6-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="0edf6-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="0edf6-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="0edf6-123">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="0edf6-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="0edf6-124">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="0edf6-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="0edf6-125">Configura le opzioni di rete di base per le classi in <xref:System.Net> e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="0edf6-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="0edf6-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="0edf6-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="0edf6-127">Specifica i moduli da usare per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="0edf6-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0edf6-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0edf6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="0edf6-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0edf6-129">**Element**</span></span>|<span data-ttu-id="0edf6-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0edf6-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0edf6-131">configuration</span><span class="sxs-lookup"><span data-stu-id="0edf6-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="0edf6-132">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0edf6-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0edf6-133">Note</span><span class="sxs-lookup"><span data-stu-id="0edf6-133">Remarks</span></span>  
 <span data-ttu-id="0edf6-134">L'elemento [@no__t -1system. net >](system-net-element-network-settings.md) contiene le impostazioni per le classi in <xref:System.Net> e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="0edf6-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="0edf6-135">Le impostazioni configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, il server proxy e i moduli di richiesta Internet per ricevere informazioni dagli host Internet.</span><span class="sxs-lookup"><span data-stu-id="0edf6-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0edf6-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="0edf6-136">Example</span></span>  
 <span data-ttu-id="0edf6-137">Nell'esempio seguente viene illustrata una configurazione tipica utilizzata dalle classi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="0edf6-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0edf6-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0edf6-138">See also</span></span>

- [<span data-ttu-id="0edf6-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0edf6-139">Network Settings Schema</span></span>](index.md)
