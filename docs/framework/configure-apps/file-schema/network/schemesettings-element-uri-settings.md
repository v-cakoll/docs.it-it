---
title: '&lt;schemeSettings&gt; elemento (impostazioni Uri)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4cf1d2013a51985f9d7772ac0ef86e5dbb120be9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltschemesettingsgt-element-uri-settings"></a>&lt;schemeSettings&gt; elemento (impostazioni Uri)
Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.  
  
 \<configuration>  
\<URI >  
\<schemeSettings >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|Aggiunge un'impostazione dello schema per il nome di schema.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|Cancella tutte le impostazioni di schema esistenti.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|Rimuove un'impostazione dello schema per il nome di schema.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso. È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Se questo URI viene passato a moduli non gestiscono percentuale correttamente codificati in caratteri, potrebbe verificarsi il seguente comando viene eseguito dal server:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classe e quindi applica la compressione del percorso. Il risultato di passare l'URL dannoso per <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Per non delimitatori di percorso con codifica percentuale di caratteri di escape annullare utilizzando l'opzione di configurazione schemeSettings per uno schema specifico, è possibile modificare questo comportamento predefinito.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrata una configurazione utilizzata per la <xref:System.Uri> classe per il supporto non escape delimitatori di percorso con codifica percentuale per lo schema http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a>Informazioni sull'elemento  
  
|||
|-|-|  
|Spazio dei nomi|Sistema|  
|Nome di schema||  
|File di convalida||  
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
