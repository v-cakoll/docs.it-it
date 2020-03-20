---
title: Elemento <schemeSettings> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154647"
---
# <a name="schemesettings-element-uri-settings"></a>\<Elemento schemeSettings> (impostazioni URI)
Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.  
  
[**\<>di configurazione**](../configuration-element.md)  
&nbsp;&nbsp;[**\<>uri**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<>schemeSettings**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[aggiungi](add-element-for-schemesettings-uri-settings.md)|Aggiunge un'impostazione di schema per un nome di schema.|  
|[Chiaro](clear-element-for-schemesettings-uri-settings.md)|Cancella tutte le impostazioni dello schema esistenti.|  
|[rimozione](remove-element-for-schemesettings-uri-settings.md)|Rimuove un'impostazione di schema per un nome di schema.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Uri](uri-element-uri-settings.md)|Contiene impostazioni che specificano il modo in cui .NET Framework gestisce gli indirizzi Web espressi utilizzando URI (Uniform Resource Identifier).|  
  
## <a name="remarks"></a>Osservazioni  
 Per impostazione <xref:System.Uri?displayProperty=nameWithType> predefinita, la classe annulla l'escape dei delimitatori di percorso con codifica percentuale prima di eseguire la compressione del percorso. Questo è stato implementato come un meccanismo di sicurezza contro gli attacchi come il seguente:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Se questo URI viene passato ai moduli che non gestiscono correttamente la percentuale di caratteri codificati, è possibile che il comando seguente venga eseguito dal server:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Per questo <xref:System.Uri?displayProperty=nameWithType> motivo, la classe prima annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso. Il risultato del passaggio <xref:System.Uri?displayProperty=nameWithType> dell'URL dannoso sopra al costruttore di classe genera il seguente URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Questo comportamento predefinito può essere modificato per non annullare l'escape dei delimitatori di percorso con codifica percentuale utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe per supportare la <xref:System.Uri> non escludidelimitatori di percorso con codifica percentuale per lo schema http.  
  
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
|Schema Name||  
|File di convalida||  
|Può essere Vuoto||  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
