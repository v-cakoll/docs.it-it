---
title: Elemento <remove> per schemeSettings (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: faf254174527ea74638442a139841eb2365d1e5d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089158"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="799fb-102">\<rimuovere > elemento per schemeSettings (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="799fb-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="799fb-103">Rimuove un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="799fb-103">Removes a scheme setting for a scheme name.</span></span>  

<span data-ttu-id="799fb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="799fb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="799fb-105">&nbsp;&nbsp;[**uri\<** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="799fb-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="799fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<SchemeSettings**](schemesettings-element-uri-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="799fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="799fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**rimuovere >**</span><span class="sxs-lookup"><span data-stu-id="799fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="799fb-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="799fb-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="799fb-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="799fb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="799fb-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="799fb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="799fb-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="799fb-111">Attributes</span></span>  
  
|<span data-ttu-id="799fb-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="799fb-112">Attribute</span></span>|<span data-ttu-id="799fb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="799fb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="799fb-114">name</span><span class="sxs-lookup"><span data-stu-id="799fb-114">name</span></span>|<span data-ttu-id="799fb-115">Nome dello schema a cui si applica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="799fb-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="799fb-116">Gli unici valori supportati sono Name = "http" e Name = "https".</span><span class="sxs-lookup"><span data-stu-id="799fb-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="799fb-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="799fb-117">Child Elements</span></span>  
 <span data-ttu-id="799fb-118">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="799fb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="799fb-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="799fb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="799fb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="799fb-120">Element</span></span>|<span data-ttu-id="799fb-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="799fb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="799fb-122">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="799fb-122">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="799fb-123">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="799fb-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="799fb-124">Note</span><span class="sxs-lookup"><span data-stu-id="799fb-124">Remarks</span></span>  
 <span data-ttu-id="799fb-125">Per impostazione predefinita, la classe <xref:System.Uri?displayProperty=nameWithType> Annulla il carattere di escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="799fb-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="799fb-126">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="799fb-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="799fb-127">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="799fb-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="799fb-128">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> classe First Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="799fb-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="799fb-129">Il risultato del passaggio dell'URL dannoso precedente a <xref:System.Uri?displayProperty=nameWithType> costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="799fb-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="799fb-130">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="799fb-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="799fb-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="799fb-131">Configuration Files</span></span>  
 <span data-ttu-id="799fb-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="799fb-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="799fb-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="799fb-133">Example</span></span>  
 <span data-ttu-id="799fb-134">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe <xref:System.Uri> che rimuove qualsiasi impostazione dello schema per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="799fb-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="799fb-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="799fb-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="799fb-136">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="799fb-136">Network Settings Schema</span></span>](index.md)
