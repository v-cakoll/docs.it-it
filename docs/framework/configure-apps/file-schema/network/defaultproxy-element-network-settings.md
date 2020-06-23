---
title: Elemento <defaultProxy> (impostazioni di rete)
description: L' <defaultProxy> elemento impostazioni di rete configura il server proxy Hypertext Transfer Protocol (http) nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 85004d49ce7605b050709a3019592ec696a7bada
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141631"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="87bd2-103">Elemento \<defaultProxy> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="87bd2-103">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="87bd2-104">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="87bd2-104">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="87bd2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87bd2-105">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="True|False"  
  useDefaultCredentials="True|False">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87bd2-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="87bd2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="87bd2-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="87bd2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87bd2-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="87bd2-108">Attributes</span></span>  
  
|<span data-ttu-id="87bd2-109">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="87bd2-109">**Element**</span></span>|<span data-ttu-id="87bd2-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="87bd2-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="87bd2-111">Specifica se viene usato un proxy Web.</span><span class="sxs-lookup"><span data-stu-id="87bd2-111">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="87bd2-112">Il valore predefinito è `True`.</span><span class="sxs-lookup"><span data-stu-id="87bd2-112">The default value is `True`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="87bd2-113">Specifica se vengono usate le credenziali predefinite per questo host per accedere al proxy Web.</span><span class="sxs-lookup"><span data-stu-id="87bd2-113">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="87bd2-114">Il valore predefinito è `False`.</span><span class="sxs-lookup"><span data-stu-id="87bd2-114">The default value is `False`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87bd2-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="87bd2-115">Child Elements</span></span>  
  
|<span data-ttu-id="87bd2-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="87bd2-116">**Element**</span></span>|<span data-ttu-id="87bd2-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="87bd2-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="87bd2-118">BypassList</span><span class="sxs-lookup"><span data-stu-id="87bd2-118">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="87bd2-119">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano il proxy.</span><span class="sxs-lookup"><span data-stu-id="87bd2-119">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="87bd2-120">modulo</span><span class="sxs-lookup"><span data-stu-id="87bd2-120">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="87bd2-121">Aggiunge un nuovo modulo proxy all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87bd2-121">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="87bd2-122">proxy</span><span class="sxs-lookup"><span data-stu-id="87bd2-122">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="87bd2-123">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="87bd2-123">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87bd2-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="87bd2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="87bd2-125">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="87bd2-125">**Element**</span></span>|<span data-ttu-id="87bd2-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="87bd2-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="87bd2-127">system.net</span><span class="sxs-lookup"><span data-stu-id="87bd2-127">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="87bd2-128">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87bd2-128">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87bd2-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="87bd2-129">Remarks</span></span>  
 <span data-ttu-id="87bd2-130">Se l'elemento defaultProxy è vuoto, verranno usate le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="87bd2-130">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="87bd2-131">Questo comportamento è diverso da quello di .NET Framework versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="87bd2-131">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="87bd2-132">Viene generata un'eccezione se l'elemento [modulo](module-element-network-settings.md) specifica un tipo non pubblico, il tipo non deriva dalla <xref:System.Net.IWebProxy> classe, un'eccezione dal costruttore senza parametri di questo oggetto o si è verificata un'eccezione durante il recupero del proxy predefinito specificato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="87bd2-132">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="87bd2-133">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="87bd2-133">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="87bd2-134">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="87bd2-134">Configuration Files</span></span>  
 <span data-ttu-id="87bd2-135">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="87bd2-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87bd2-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="87bd2-136">Example</span></span>  
 <span data-ttu-id="87bd2-137">Nell'esempio seguente vengono utilizzate le impostazioni predefinite del proxy di Internet Explorer, viene specificato l'indirizzo proxy e viene ignorato il proxy per l'accesso locale e contoso.com.</span><span class="sxs-lookup"><span data-stu-id="87bd2-137">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87bd2-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87bd2-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="87bd2-139">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="87bd2-139">Network Settings Schema</span></span>](index.md)
