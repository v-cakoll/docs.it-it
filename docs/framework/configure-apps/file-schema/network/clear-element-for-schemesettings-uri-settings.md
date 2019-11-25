---
title: Elemento <clear> per schemeSettings (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087449"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="966b7-102">\<elemento clear > per schemeSettings (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="966b7-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="966b7-103">Cancella tutte le impostazioni dello schema esistente.</span><span class="sxs-lookup"><span data-stu-id="966b7-103">Clears all existing scheme settings.</span></span>  

<span data-ttu-id="966b7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="966b7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="966b7-105">&nbsp;&nbsp;[**uri\<** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="966b7-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="966b7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<SchemeSettings**](schemesettings-element-uri-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="966b7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="966b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Cancella** ></span><span class="sxs-lookup"><span data-stu-id="966b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="966b7-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="966b7-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="966b7-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="966b7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="966b7-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="966b7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="966b7-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="966b7-111">Attributes</span></span>  
 <span data-ttu-id="966b7-112">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="966b7-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="966b7-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="966b7-113">Child Elements</span></span>  
 <span data-ttu-id="966b7-114">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="966b7-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="966b7-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="966b7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="966b7-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="966b7-116">Element</span></span>|<span data-ttu-id="966b7-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="966b7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="966b7-118">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="966b7-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="966b7-119">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="966b7-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="966b7-120">Note</span><span class="sxs-lookup"><span data-stu-id="966b7-120">Remarks</span></span>  
 <span data-ttu-id="966b7-121">Per impostazione predefinita, la classe <xref:System.Uri?displayProperty=nameWithType> Annulla il carattere di escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="966b7-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="966b7-122">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="966b7-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="966b7-123">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="966b7-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="966b7-124">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> classe First Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="966b7-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="966b7-125">Il risultato del passaggio dell'URL dannoso precedente a <xref:System.Uri?displayProperty=nameWithType> costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="966b7-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="966b7-126">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="966b7-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="966b7-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="966b7-127">Configuration Files</span></span>  
 <span data-ttu-id="966b7-128">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="966b7-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="966b7-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="966b7-129">Example</span></span>  
 <span data-ttu-id="966b7-130">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe <xref:System.Uri> che cancella tutte le impostazioni dello schema e quindi aggiunge il supporto per evitare l'escape dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="966b7-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="966b7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="966b7-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="966b7-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="966b7-132">Network Settings Schema</span></span>](index.md)
