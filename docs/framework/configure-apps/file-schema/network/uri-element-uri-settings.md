---
title: Elemento <Uri> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 80d71da5ca680872e4948fa8ff135fbbdf08cffe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663971"
---
# <a name="uri-element-uri-settings"></a>\<Elemento > URI (impostazioni URI)
Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).  
  
## <a name="schema-hierarchy"></a>Gerarchia dello schema  
 [Elemento \<configuration>](../configuration-element.md)  
  
 [\<uri>](uri-element-uri-settings.md)  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[idn](idn-element-uri-settings.md)|Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.|  
|[iriParsing](iriparsing-element-uri-settings.md)|Specifica se viene applicata l'analisi IRI (International Resource Identifier) a <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.|  
|[schemeSettings](schemesettings-element-uri-settings.md)|Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Contiene le impostazioni per tutti gli spazi dei nomi.|  
  
## <a name="remarks"></a>Note  
 L' `uri` elemento contiene le impostazioni per i membri <xref:System.Uri> della classe <xref:System.Net> utilizzata dalle classi nello spazio dei nomi. Le impostazioni configurano il supporto per IRI e IDN.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrata una configurazione utilizzata <xref:System.Uri> dalla classe per supportare l'analisi IRI e i nomi IDN. Nell'esempio vengono cancellate anche tutte le impostazioni dello schema e viene aggiunto il supporto per non eseguire l'escape dei delimitatori di percorso codificati in percentuale per lo schema http.  
  
### <a name="code"></a>Codice  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di rete](index.md)
