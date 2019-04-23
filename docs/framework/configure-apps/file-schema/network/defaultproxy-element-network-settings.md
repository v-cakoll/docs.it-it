---
title: Elemento <defaultProxy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: ce08dadb0fb7b986c0573b1514f9ecbbe2961c3a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228347"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="5db9b-102">\<defaultProxy > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="5db9b-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="5db9b-103">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="5db9b-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="5db9b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5db9b-104">\<configuration></span></span>  
<span data-ttu-id="5db9b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="5db9b-105">\<system.net></span></span>  
<span data-ttu-id="5db9b-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="5db9b-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db9b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5db9b-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5db9b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5db9b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5db9b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5db9b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5db9b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="5db9b-110">Attributes</span></span>  
  
|<span data-ttu-id="5db9b-111">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="5db9b-111">**Element**</span></span>|<span data-ttu-id="5db9b-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5db9b-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="5db9b-113">Specifica se viene usato un proxy Web.</span><span class="sxs-lookup"><span data-stu-id="5db9b-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="5db9b-114">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="5db9b-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="5db9b-115">Specifica se vengono usate le credenziali predefinite per questo host per accedere al proxy Web.</span><span class="sxs-lookup"><span data-stu-id="5db9b-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="5db9b-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="5db9b-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5db9b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5db9b-117">Child Elements</span></span>  
  
|<span data-ttu-id="5db9b-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="5db9b-118">**Element**</span></span>|<span data-ttu-id="5db9b-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5db9b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5db9b-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="5db9b-120">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="5db9b-121">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano il proxy.</span><span class="sxs-lookup"><span data-stu-id="5db9b-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="5db9b-122">module</span><span class="sxs-lookup"><span data-stu-id="5db9b-122">module</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|<span data-ttu-id="5db9b-123">Aggiunge un nuovo modulo proxy all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5db9b-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="5db9b-124">proxy</span><span class="sxs-lookup"><span data-stu-id="5db9b-124">proxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|<span data-ttu-id="5db9b-125">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="5db9b-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5db9b-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5db9b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="5db9b-127">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="5db9b-127">**Element**</span></span>|<span data-ttu-id="5db9b-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5db9b-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5db9b-129">system.net</span><span class="sxs-lookup"><span data-stu-id="5db9b-129">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="5db9b-130">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5db9b-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5db9b-131">Note</span><span class="sxs-lookup"><span data-stu-id="5db9b-131">Remarks</span></span>  
 <span data-ttu-id="5db9b-132">Se l'elemento defaultProxy è vuoto, verranno usate le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5db9b-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="5db9b-133">Questo comportamento è diverso da quello di .NET Framework versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="5db9b-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="5db9b-134">Viene generata un'eccezione se il [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) elemento specifica un tipo non pubblico, il tipo non deriva dal <xref:System.Net.IWebProxy> (classe), si è verificata un'eccezione dal costruttore predefinito di questo oggetto, o si è verificata un'eccezione mentre il recupero del proxy predefinito specificato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5db9b-134">An exception is thrown if the [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the default constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="5db9b-135">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="5db9b-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5db9b-136">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="5db9b-136">Configuration Files</span></span>  
 <span data-ttu-id="5db9b-137">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5db9b-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5db9b-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="5db9b-138">Example</span></span>  
 <span data-ttu-id="5db9b-139">Nell'esempio seguente usa le impostazioni predefinite del proxy di Internet Explorer, specifica l'indirizzo del proxy e ignora il proxy per l'accesso locale e contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5db9b-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5db9b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5db9b-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="5db9b-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="5db9b-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
