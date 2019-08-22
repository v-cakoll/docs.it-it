---
title: Elemento <add> per schemeSettings (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 027c7aaffea7950739f532309255d77afa031ada
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659547"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="0b84e-102">\<aggiungere > elemento per schemeSettings (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="0b84e-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="0b84e-103">Aggiunge un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="0b84e-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="0b84e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0b84e-104">\<configuration></span></span>  
<span data-ttu-id="0b84e-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="0b84e-105">\<uri></span></span>  
<span data-ttu-id="0b84e-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="0b84e-106">\<schemeSettings></span></span>  
<span data-ttu-id="0b84e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="0b84e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b84e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b84e-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b84e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0b84e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0b84e-110">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0b84e-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b84e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="0b84e-111">Attributes</span></span>  
  
|<span data-ttu-id="0b84e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="0b84e-112">Attribute</span></span>|<span data-ttu-id="0b84e-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0b84e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b84e-114">name</span><span class="sxs-lookup"><span data-stu-id="0b84e-114">name</span></span>|<span data-ttu-id="0b84e-115">Nome dello schema a cui si applica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="0b84e-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="0b84e-116">Gli unici valori supportati sono Name = "http" e Name = "https".</span><span class="sxs-lookup"><span data-stu-id="0b84e-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="0b84e-117">{Nome attributo} Attributo</span><span class="sxs-lookup"><span data-stu-id="0b84e-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="0b84e-118">Value</span><span class="sxs-lookup"><span data-stu-id="0b84e-118">Value</span></span>|<span data-ttu-id="0b84e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b84e-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b84e-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="0b84e-120">genericUriParserOptions</span></span>|<span data-ttu-id="0b84e-121">Opzioni del parser per questo schema.</span><span class="sxs-lookup"><span data-stu-id="0b84e-121">The parser options for this scheme.</span></span> <span data-ttu-id="0b84e-122">L'unico valore supportato è genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="0b84e-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b84e-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0b84e-123">Child Elements</span></span>  
 <span data-ttu-id="0b84e-124">Nessuna</span><span class="sxs-lookup"><span data-stu-id="0b84e-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b84e-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0b84e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0b84e-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b84e-126">Element</span></span>|<span data-ttu-id="0b84e-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0b84e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b84e-128">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="0b84e-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="0b84e-129">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="0b84e-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b84e-130">Note</span><span class="sxs-lookup"><span data-stu-id="0b84e-130">Remarks</span></span>  
 <span data-ttu-id="0b84e-131">Per impostazione predefinita, <xref:System.Uri?displayProperty=nameWithType> la classe Annulla l'escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="0b84e-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="0b84e-132">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b84e-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="0b84e-133">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="0b84e-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="0b84e-134">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> First Class Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="0b84e-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="0b84e-135">Il risultato del passaggio dell'URL dannoso precedente <xref:System.Uri?displayProperty=nameWithType> al costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="0b84e-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="0b84e-136">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="0b84e-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0b84e-137">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0b84e-137">Configuration Files</span></span>  
 <span data-ttu-id="0b84e-138">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0b84e-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b84e-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b84e-139">Example</span></span>  
 <span data-ttu-id="0b84e-140">Nell'esempio seguente viene illustrata una configurazione utilizzata <xref:System.Uri> dalla classe per supportare la mancata evasione dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="0b84e-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b84e-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b84e-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="0b84e-142">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0b84e-142">Network Settings Schema</span></span>](index.md)
