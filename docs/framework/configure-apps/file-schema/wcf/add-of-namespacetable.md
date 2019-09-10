---
title: <add> di <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850390"
---
# <a name="add-of-namespacetable"></a>\<aggiungere > di \<namespaceTable >
Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> namespaceTable**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|namespace|Stringa contenente lo spazio dei nomi.|  
|prefix|Stringa contenente il prefisso per questo spazio dei nomi.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
