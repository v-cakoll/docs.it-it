---
title: "&lt;add&gt; dell'elemento &lt;declaredTypes&gt;"
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 90eaf11ce8b9e3675a23ed3875680b03f149b56b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754119"
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a>&lt;add&gt; dell'elemento &lt;declaredTypes&gt;
Aggiunge un tipo usato dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione. Ogni tipo dichiarato contiene i tipi noti che verranno restituiti come campo o come proprietà del tipo dichiarato.  
  
 system.runtime.serialization  
\<dataContractSerializer >  
\<declaredTypes >  
\<aggiungere > di \<declaredTypes >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|tipo|Attributo stringa obbligatorio.<br /><br /> Specifica il nome del tipo (compreso lo spazio dei nomi), il nome dell'assembly, il numero di versione, impostazioni cultura e token di chiave pubblica.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<knownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Specifica il tipo conosciuto del tipo dichiarato da aggiungere. Se il tipo dichiarato è un tipo generico occorre aggiungere anche un elemento di parametro all'elemento `<knownType>` per specificare quale parametro generico viene usato per restituire il tipo conosciuto.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<declaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Contiene i tipi che richiedono tipi noti durante la deserializzazione eseguita dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Note  
 Per ulteriori informazioni sui tipi noti, vedere [tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Vedere il [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.  
  
> [!NOTE]
>  Se si aggiunge il tipo <xref:System.Object> come tipo `<declaredType>`, viene generata un'eccezione <xref:System.Configuration.ConfigurationErrorsException>. Ciò è dovuto al fatto che il tipo <xref:System.Object> non può essere usato come tipo dichiarato in configurazione.  
  
## <a name="example"></a>Esempio  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Tipi noti di contratto di dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<aggiungere > di \<declaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
