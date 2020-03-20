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
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154556"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="dc946-102">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="dc946-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="dc946-103">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc946-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="dc946-104">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="dc946-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="dc946-105">&nbsp;&nbsp;**\<>system.net**</span><span class="sxs-lookup"><span data-stu-id="dc946-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc946-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc946-106">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc946-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dc946-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dc946-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dc946-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc946-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="dc946-109">Attributes</span></span>  
 <span data-ttu-id="dc946-110">No.</span><span class="sxs-lookup"><span data-stu-id="dc946-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc946-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dc946-111">Child Elements</span></span>  
  
|<span data-ttu-id="dc946-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="dc946-112">**Element**</span></span>|<span data-ttu-id="dc946-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dc946-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dc946-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="dc946-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="dc946-115">Specifica i moduli utilizzati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="dc946-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="dc946-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="dc946-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="dc946-117">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="dc946-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="dc946-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="dc946-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="dc946-119">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="dc946-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="dc946-120">MailImpostazioni</span><span class="sxs-lookup"><span data-stu-id="dc946-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="dc946-121">Configura le opzioni di invio della posta SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="dc946-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="dc946-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="dc946-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="dc946-123">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="dc946-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="dc946-124">impostazioni</span><span class="sxs-lookup"><span data-stu-id="dc946-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="dc946-125">Configura le opzioni di rete <xref:System.Net> di base per le classi negli spazi dei nomi figlio correlati e correlati.</span><span class="sxs-lookup"><span data-stu-id="dc946-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="dc946-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="dc946-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="dc946-127">Specifica i moduli da utilizzare per richiedere informazioni agli host Internet.</span><span class="sxs-lookup"><span data-stu-id="dc946-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc946-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dc946-128">Parent Elements</span></span>  
  
|<span data-ttu-id="dc946-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="dc946-129">**Element**</span></span>|<span data-ttu-id="dc946-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dc946-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dc946-131">configurazione</span><span class="sxs-lookup"><span data-stu-id="dc946-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="dc946-132">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dc946-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc946-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dc946-133">Remarks</span></span>  
 <span data-ttu-id="dc946-134">L'elemento [ \<system.net>](system-net-element-network-settings.md) contiene <xref:System.Net> le impostazioni per le classi negli spazi dei nomi figlio e correlati.</span><span class="sxs-lookup"><span data-stu-id="dc946-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="dc946-135">Le impostazioni configurano i moduli di autenticazione, la gestione delle connessioni, le impostazioni di posta, il server proxy e i moduli di richiesta Internet per la ricezione di informazioni dagli host Internet.</span><span class="sxs-lookup"><span data-stu-id="dc946-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc946-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc946-136">Example</span></span>  
 <span data-ttu-id="dc946-137">Nell'esempio seguente viene illustrata una configurazione tipica utilizzata dalle <xref:System.Net> classi.</span><span class="sxs-lookup"><span data-stu-id="dc946-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc946-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc946-138">See also</span></span>

- [<span data-ttu-id="dc946-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="dc946-139">Network Settings Schema</span></span>](index.md)
