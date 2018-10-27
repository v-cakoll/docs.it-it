---
title: '&lt;rimuovere&gt; (elemento) per schemeSettings (impostazioni Uri)'
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: d444e2eeeace2dc59a53467316507d0bc38970d5
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50186044"
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a>&lt;rimuovere&gt; (elemento) per schemeSettings (impostazioni Uri)
Rimuove un'impostazione di schema per un nome di schema.  
  
 \<configuration>  
\<URI >  
\<schemeSettings >  
\<rimuovere >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Il nome dello schema per il quale si applica questa impostazione. Il solo valori supportati sono: nome = "http" e nome = "https".|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<schemeSettings> (impostazioni URI)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso. È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Se viene passato questo URI lungo i moduli non gestiscono percento codificati in caratteri correttamente, potrebbero verificarsi il seguente comando eseguito dal server:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classi e quindi applica la compressione del percorso. Il risultato di passare l'URL dannoso a <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Possibile è possibile modificare questo comportamento predefinito per non i delimitatori del percorso con codifica percentuale ONU-escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe che rimuove qualsiasi impostazione dello schema per lo schema http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
- <xref:System.Uri?displayProperty=nameWithType>  
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
