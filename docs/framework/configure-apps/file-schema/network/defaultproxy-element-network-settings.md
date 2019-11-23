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
ms.openlocfilehash: 0945629c1395917bc1cf825f2ba84d20afa99957
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698201"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="70f10-102">\<elemento > defaultProxy (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="70f10-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="70f10-103">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="70f10-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[<span data-ttu-id="70f10-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="70f10-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="70f10-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="70f10-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="70f10-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultProxy >**</span><span class="sxs-lookup"><span data-stu-id="70f10-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f10-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70f10-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70f10-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="70f10-108">Attributes and Elements</span></span>  
 <span data-ttu-id="70f10-109">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="70f10-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70f10-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="70f10-110">Attributes</span></span>  
  
|<span data-ttu-id="70f10-111">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="70f10-111">**Element**</span></span>|<span data-ttu-id="70f10-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="70f10-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="70f10-113">Specifica se viene usato un proxy Web.</span><span class="sxs-lookup"><span data-stu-id="70f10-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="70f10-114">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="70f10-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="70f10-115">Specifica se vengono usate le credenziali predefinite per questo host per accedere al proxy Web.</span><span class="sxs-lookup"><span data-stu-id="70f10-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="70f10-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="70f10-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70f10-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="70f10-117">Child Elements</span></span>  
  
|<span data-ttu-id="70f10-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="70f10-118">**Element**</span></span>|<span data-ttu-id="70f10-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="70f10-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="70f10-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="70f10-120">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="70f10-121">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano il proxy.</span><span class="sxs-lookup"><span data-stu-id="70f10-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="70f10-122">module</span><span class="sxs-lookup"><span data-stu-id="70f10-122">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="70f10-123">Aggiunge un nuovo modulo proxy all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70f10-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="70f10-124">proxy</span><span class="sxs-lookup"><span data-stu-id="70f10-124">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="70f10-125">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="70f10-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70f10-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="70f10-126">Parent Elements</span></span>  
  
|<span data-ttu-id="70f10-127">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="70f10-127">**Element**</span></span>|<span data-ttu-id="70f10-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="70f10-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="70f10-129">system.net</span><span class="sxs-lookup"><span data-stu-id="70f10-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="70f10-130">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70f10-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70f10-131">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="70f10-131">Remarks</span></span>  
 <span data-ttu-id="70f10-132">Se l'elemento defaultProxy è vuoto, verranno usate le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="70f10-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="70f10-133">Questo comportamento è diverso da quello di .NET Framework versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="70f10-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="70f10-134">Viene generata un'eccezione se l'elemento [modulo](module-element-network-settings.md) specifica un tipo non pubblico, il tipo non deriva dalla classe <xref:System.Net.IWebProxy>, un'eccezione dal costruttore senza parametri di questo oggetto o si è verificata un'eccezione durante il recupero del proxy predefinito specificato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="70f10-134">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="70f10-135">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="70f10-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="70f10-136">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="70f10-136">Configuration Files</span></span>  
 <span data-ttu-id="70f10-137">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="70f10-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70f10-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="70f10-138">Example</span></span>  
 <span data-ttu-id="70f10-139">Nell'esempio seguente vengono utilizzate le impostazioni predefinite del proxy di Internet Explorer, viene specificato l'indirizzo proxy e viene ignorato il proxy per l'accesso locale e contoso.com.</span><span class="sxs-lookup"><span data-stu-id="70f10-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="70f10-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70f10-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="70f10-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="70f10-141">Network Settings Schema</span></span>](index.md)
