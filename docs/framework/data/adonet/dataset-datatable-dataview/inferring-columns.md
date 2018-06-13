---
title: Deduzione di colonne
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: da98bcbc4537e08a6f8565b36f8b84b476efd027
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761077"
---
# <a name="inferring-columns"></a>Deduzione di colonne
Una volta che ADO.NET ha determinato quali elementi di un documento XML devono essere inferiti come tabelle per un tipo <xref:System.Data.DataSet>, vengono inferite le colonne di tali tabelle. ADO.NET 2.0 è stato introdotto un nuovo motore di inferenza dello schema che consente di inferire un tipo di dati fortemente tipizzati per ogni **simpleType** elemento. Nelle versioni precedenti, il tipo di dati di un tipo derivato **simpleType** era sempre **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Migrazione e compatibilità con versioni precedenti  
 Il **ReadXml** metodo accetta un argomento di tipo **InferSchema**. Tale argomento consente di specificare il comportamento di inferenza compatibile con versioni precedenti. I valori disponibili per il **InferSchema** enumerazione vengono visualizzati nella tabella seguente.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Fornisce compatibilità con le versioni precedenti inferendo sempre un tipo semplice come <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Inferisce un tipo di dati tipizzato in modo sicuro. Viene generata un'eccezione se usato con un tipo <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Ignora tutti gli schemi inline e legge i dati nello schema <xref:System.Data.DataSet> esistente.  
  
## <a name="attributes"></a>Attributi  
 Come definito in [inferenza di tabelle](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), un elemento con attributi verrà inferito come tabella. Gli attributi di tale elemento verranno quindi inferiti come colonne della tabella. Il **ColumnMapping** delle colonne verrà impostata su **MappingType. Attribute**, per assicurare che i nomi delle colonne verrà scritto come attributi se lo schema viene scritto in XML. I valori degli attributi vengono archiviati in una riga della tabella. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Il processo di inferenza genererà una tabella denominata **Element1** con due colonne, **attr1** e **attr2**. Il **ColumnMapping** entrambe le colonne verrà impostata su **MappingType. Attribute**.  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elementi privi di attributi o elementi figlio  
 Se un elemento non dispone di elementi figlio o attributi, tale elemento verrà inferito come colonna. Il **ColumnMapping** della colonna verrà impostata su **MappingType**. Il testo degli elementi figlio è archiviato in una riga della tabella. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza genererà una tabella denominata **Element1** con due colonne, **ChildElement1** e **ChildElement2**. Il **ColumnMapping** entrambe le colonne verrà impostata su **MappingType**.  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>Vedere anche  
 [Deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
