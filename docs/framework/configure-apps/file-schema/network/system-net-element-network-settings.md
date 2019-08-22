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
ms.openlocfilehash: 449146612938700f59f5e2ec761526d1dc66a3fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663953"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="d9cbc-102">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d9cbc-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="d9cbc-103">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="d9cbc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d9cbc-104">\<configuration></span></span>  
<span data-ttu-id="d9cbc-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d9cbc-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9cbc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9cbc-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9cbc-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d9cbc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d9cbc-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9cbc-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="d9cbc-109">Attributes</span></span>  
 <span data-ttu-id="d9cbc-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9cbc-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d9cbc-111">Child Elements</span></span>  
  
|<span data-ttu-id="d9cbc-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d9cbc-112">**Element**</span></span>|<span data-ttu-id="d9cbc-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d9cbc-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d9cbc-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="d9cbc-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="d9cbc-115">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="d9cbc-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="d9cbc-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="d9cbc-117">Specifica il numero massimo di connessioni a un host Internet.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="d9cbc-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="d9cbc-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="d9cbc-119">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="d9cbc-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="d9cbc-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="d9cbc-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="d9cbc-121">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="d9cbc-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="d9cbc-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="d9cbc-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="d9cbc-123">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="d9cbc-124">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="d9cbc-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="d9cbc-125">Configura le opzioni di rete di base per le <xref:System.Net> classi in e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="d9cbc-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d9cbc-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="d9cbc-127">Specifica i moduli da usare per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9cbc-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d9cbc-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d9cbc-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d9cbc-129">**Element**</span></span>|<span data-ttu-id="d9cbc-130">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d9cbc-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d9cbc-131">configuration</span><span class="sxs-lookup"><span data-stu-id="d9cbc-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="d9cbc-132">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9cbc-133">Note</span><span class="sxs-lookup"><span data-stu-id="d9cbc-133">Remarks</span></span>  
 <span data-ttu-id="d9cbc-134"><xref:System.Net> L' [ \<elemento System. net >](system-net-element-network-settings.md) contiene le impostazioni per le classi in e gli spazi dei nomi figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="d9cbc-135">Le impostazioni configurano i moduli di autenticazione, la gestione della connessione, le impostazioni di posta elettronica, il server proxy e i moduli di richiesta Internet per ricevere informazioni dagli host Internet.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9cbc-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9cbc-136">Example</span></span>  
 <span data-ttu-id="d9cbc-137">Nell'esempio seguente viene illustrata una configurazione tipica <xref:System.Net> utilizzata dalle classi.</span><span class="sxs-lookup"><span data-stu-id="d9cbc-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9cbc-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9cbc-138">See also</span></span>

- [<span data-ttu-id="d9cbc-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d9cbc-139">Network Settings Schema</span></span>](index.md)
