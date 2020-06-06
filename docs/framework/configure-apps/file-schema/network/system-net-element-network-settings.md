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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154556"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="95cd9-102">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="95cd9-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="95cd9-103">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95cd9-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="95cd9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95cd9-104">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95cd9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="95cd9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="95cd9-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="95cd9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95cd9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="95cd9-107">Attributes</span></span>  
 <span data-ttu-id="95cd9-108">No.</span><span class="sxs-lookup"><span data-stu-id="95cd9-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95cd9-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="95cd9-109">Child Elements</span></span>  
  
|<span data-ttu-id="95cd9-110">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="95cd9-110">**Element**</span></span>|<span data-ttu-id="95cd9-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="95cd9-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="95cd9-112">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="95cd9-112">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="95cd9-113">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="95cd9-113">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="95cd9-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="95cd9-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="95cd9-115">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="95cd9-115">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="95cd9-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="95cd9-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="95cd9-117">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="95cd9-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="95cd9-118">mailSettings</span><span class="sxs-lookup"><span data-stu-id="95cd9-118">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="95cd9-119">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="95cd9-119">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="95cd9-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="95cd9-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="95cd9-121">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="95cd9-121">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="95cd9-122">impostazioni</span><span class="sxs-lookup"><span data-stu-id="95cd9-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="95cd9-123">Configura le opzioni di rete di base per le classi in <xref:System.Net> e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="95cd9-123">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="95cd9-124">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="95cd9-124">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="95cd9-125">Specifica i moduli da usare per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="95cd9-125">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95cd9-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="95cd9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="95cd9-127">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="95cd9-127">**Element**</span></span>|<span data-ttu-id="95cd9-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="95cd9-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="95cd9-129">configurazione</span><span class="sxs-lookup"><span data-stu-id="95cd9-129">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="95cd9-130">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="95cd9-130">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95cd9-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="95cd9-131">Remarks</span></span>  
 <span data-ttu-id="95cd9-132">L' [\<system.net>](system-net-element-network-settings.md) elemento contiene le impostazioni per le classi in <xref:System.Net> e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="95cd9-132">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="95cd9-133">Le impostazioni configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, il server proxy e i moduli di richiesta Internet per ricevere informazioni dagli host Internet.</span><span class="sxs-lookup"><span data-stu-id="95cd9-133">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95cd9-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="95cd9-134">Example</span></span>  
 <span data-ttu-id="95cd9-135">Nell'esempio seguente viene illustrata una configurazione tipica utilizzata dalle <xref:System.Net> classi.</span><span class="sxs-lookup"><span data-stu-id="95cd9-135">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="95cd9-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="95cd9-136">See also</span></span>

- [<span data-ttu-id="95cd9-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="95cd9-137">Network Settings Schema</span></span>](index.md)
