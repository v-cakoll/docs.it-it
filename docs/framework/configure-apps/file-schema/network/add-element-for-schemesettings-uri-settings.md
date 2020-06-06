---
title: Elemento <add> per schemeSettings (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: ed40098e8d4c2d1298771e67a618b8d04f59c912
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087723"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="094ee-102">Elemento \<add> per schemeSettings (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="094ee-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="094ee-103">Aggiunge un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="094ee-103">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="094ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="094ee-104">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="094ee-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="094ee-105">Attributes and Elements</span></span>  
 <span data-ttu-id="094ee-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="094ee-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="094ee-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="094ee-107">Attributes</span></span>  
  
|<span data-ttu-id="094ee-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="094ee-108">Attribute</span></span>|<span data-ttu-id="094ee-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="094ee-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="094ee-110">name</span><span class="sxs-lookup"><span data-stu-id="094ee-110">name</span></span>|<span data-ttu-id="094ee-111">Nome dello schema a cui si applica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="094ee-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="094ee-112">Gli unici valori supportati sono Name = "http" e Name = "https".</span><span class="sxs-lookup"><span data-stu-id="094ee-112">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="094ee-113">{Nome attributo} Attributo</span><span class="sxs-lookup"><span data-stu-id="094ee-113">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="094ee-114">Valore</span><span class="sxs-lookup"><span data-stu-id="094ee-114">Value</span></span>|<span data-ttu-id="094ee-115">Description</span><span class="sxs-lookup"><span data-stu-id="094ee-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="094ee-116">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="094ee-116">genericUriParserOptions</span></span>|<span data-ttu-id="094ee-117">Opzioni del parser per questo schema.</span><span class="sxs-lookup"><span data-stu-id="094ee-117">The parser options for this scheme.</span></span> <span data-ttu-id="094ee-118">L'unico valore supportato è genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="094ee-118">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="094ee-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="094ee-119">Child Elements</span></span>  
 <span data-ttu-id="094ee-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="094ee-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="094ee-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="094ee-121">Parent Elements</span></span>  
  
|<span data-ttu-id="094ee-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="094ee-122">Element</span></span>|<span data-ttu-id="094ee-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="094ee-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="094ee-124">\<schemeSettings>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="094ee-124">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="094ee-125">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="094ee-125">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="094ee-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="094ee-126">Remarks</span></span>  
 <span data-ttu-id="094ee-127">Per impostazione predefinita, la <xref:System.Uri?displayProperty=nameWithType> classe Annulla l'escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="094ee-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="094ee-128">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="094ee-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="094ee-129">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="094ee-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="094ee-130">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> First Class Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="094ee-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="094ee-131">Il risultato del passaggio dell'URL dannoso precedente al <xref:System.Uri?displayProperty=nameWithType> costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="094ee-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="094ee-132">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="094ee-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="094ee-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="094ee-133">Configuration Files</span></span>  
 <span data-ttu-id="094ee-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="094ee-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="094ee-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="094ee-135">Example</span></span>  
 <span data-ttu-id="094ee-136">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla <xref:System.Uri> classe per supportare la mancata evasione dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="094ee-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="094ee-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="094ee-137">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="094ee-138">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="094ee-138">Network Settings Schema</span></span>](index.md)
