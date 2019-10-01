---
title: Elemento <schemeSettings> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697765"
---
# <a name="schemesettings-element-uri-settings"></a>Elemento > \<schemeSettings (impostazioni URI)
Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<schemeSettings >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[add](add-element-for-schemesettings-uri-settings.md)|Aggiunge un'impostazione dello schema per un nome di schema.|  
|[clear](clear-element-for-schemesettings-uri-settings.md)|Cancella tutte le impostazioni dello schema esistente.|  
|[remove](remove-element-for-schemesettings-uri-settings.md)|Rimuove un'impostazione dello schema per un nome di schema.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, la classe <xref:System.Uri?displayProperty=nameWithType> Annulla il carattere di escape per cento delimitatori di percorso codificati prima di eseguire la compressione del percorso. Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Per questo motivo, la classe <xref:System.Uri?displayProperty=nameWithType> First Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso. Il risultato del passaggio dell'URL dannoso precedente al costruttore della classe <xref:System.Uri?displayProperty=nameWithType> comporta l'URI seguente:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe <xref:System.Uri> per supportare la mancata evasione dei delimitatori di percorso codificati in percentuale per lo schema http.  
  
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
|Spazio dei nomi|System|  
|Nome di schema||  
|File di convalida||  
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
