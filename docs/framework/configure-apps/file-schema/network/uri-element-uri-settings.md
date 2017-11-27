---
title: '&lt;URI&gt; elemento (impostazioni Uri)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 44ef28ca2188973ccd353f4e8615c7c95f5674a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lturigt-element-uri-settings"></a>&lt;URI&gt; elemento (impostazioni Uri)
Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).  
  
## <a name="schema-hierarchy"></a>Gerarchia dello schema  
 [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI >](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
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
|[IDN](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.|  
|[iriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Specifica se l'analisi di identificatore IRI (International Resource) viene applicato a <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[configurazione](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Contiene le impostazioni per tutti gli spazi dei nomi.|  
  
## <a name="remarks"></a>Note  
 Il `uri` elemento contiene le impostazioni per i membri del <xref:System.Uri> utilizzata dalle classi nella classe di <xref:System.Net> dello spazio dei nomi. Le impostazioni di configurano il supporto per IRI e IDN.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene mostrata una configurazione utilizzata per la <xref:System.Uri> classe per supportare l'analisi IRI e i nomi IDN. Nell'esempio viene inoltre Cancella tutte le impostazioni dello schema e quindi aggiunge il supporto per sequenza di escape non delimitatori di percorso con codifica percentuale per lo schema http.  
  
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
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
