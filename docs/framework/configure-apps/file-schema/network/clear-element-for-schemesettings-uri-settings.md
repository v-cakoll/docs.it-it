---
title: Elemento <clear> per schemeSettings (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087449"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="689e6-102">Elemento \<clear> per schemeSettings (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="689e6-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="689e6-103">Cancella tutte le impostazioni dello schema esistente.</span><span class="sxs-lookup"><span data-stu-id="689e6-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="689e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="689e6-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="689e6-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="689e6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="689e6-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="689e6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="689e6-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="689e6-107">Attributes</span></span>  
 <span data-ttu-id="689e6-108">No.</span><span class="sxs-lookup"><span data-stu-id="689e6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="689e6-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="689e6-109">Child Elements</span></span>  
 <span data-ttu-id="689e6-110">No.</span><span class="sxs-lookup"><span data-stu-id="689e6-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="689e6-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="689e6-111">Parent Elements</span></span>  
  
|<span data-ttu-id="689e6-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="689e6-112">Element</span></span>|<span data-ttu-id="689e6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="689e6-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="689e6-114">\<schemeSettings>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="689e6-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="689e6-115">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="689e6-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="689e6-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="689e6-116">Remarks</span></span>  
 <span data-ttu-id="689e6-117">Per impostazione predefinita, la <xref:System.Uri?displayProperty=nameWithType> classe Annulla l'escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="689e6-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="689e6-118">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="689e6-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="689e6-119">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="689e6-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="689e6-120">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> First Class Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="689e6-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="689e6-121">Il risultato del passaggio dell'URL dannoso precedente al <xref:System.Uri?displayProperty=nameWithType> costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="689e6-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="689e6-122">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="689e6-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="689e6-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="689e6-123">Configuration Files</span></span>  
 <span data-ttu-id="689e6-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="689e6-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="689e6-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="689e6-125">Example</span></span>  
 <span data-ttu-id="689e6-126">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla <xref:System.Uri> classe che cancella tutte le impostazioni dello schema e quindi aggiunge il supporto per evitare l'escape dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="689e6-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="689e6-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="689e6-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="689e6-128">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="689e6-128">Network Settings Schema</span></span>](index.md)
