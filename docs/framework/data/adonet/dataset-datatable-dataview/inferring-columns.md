---
title: Deduzione di colonne
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 2718cbcf29799f99c8648b129fdb6079a6f6d344
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786185"
---
# <a name="inferring-columns"></a>Deduzione di colonne
Una volta che ADO.NET ha determinato quali elementi di un documento XML devono essere inferiti come tabelle per un tipo <xref:System.Data.DataSet>, vengono inferite le colonne di tali tabelle. In ADO.NET 2,0 è stato introdotto un nuovo motore di inferenza dello schema che deduce un tipo di dati fortemente tipizzato per ogni elemento **simpleType** . Nelle versioni precedenti il tipo di dati di un elemento **simpleType** derivato era sempre **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Migrazione e compatibilità con versioni precedenti  
 Il metodo **ReadXml** accetta un argomento di tipo **InferSchema**. Tale argomento consente di specificare il comportamento di inferenza compatibile con versioni precedenti. Nella tabella seguente sono riportati i valori disponibili per l'enumerazione **InferSchema** .  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Fornisce compatibilità con le versioni precedenti inferendo sempre un tipo semplice come <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Inferisce un tipo di dati tipizzato in modo sicuro. Viene generata un'eccezione se usato con un tipo <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Ignora tutti gli schemi inline e legge i dati nello schema <xref:System.Data.DataSet> esistente.  
  
## <a name="attributes"></a>Attributi  
 Come definito in [deduzione di tabelle](inferring-tables.md), un elemento con attributi verrà dedotto come tabella. Gli attributi di tale elemento verranno quindi inferiti come colonne della tabella. La proprietà **ColumnMapping** delle colonne verrà impostata su **MappingType. Attribute**, per garantire che i nomi delle colonne vengano scritti come attributi se lo schema viene riscritto in XML. I valori degli attributi vengono archiviati in una riga della tabella. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Il processo di inferenza produrrà una tabella denominata **Element1** con due colonne, **attr1** e **attr2**. La proprietà **ColumnMapping** di entrambe le colonne verrà impostata su **MappingType. Attribute**.  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elementi privi di attributi o elementi figlio  
 Se un elemento non dispone di elementi figlio o attributi, tale elemento verrà inferito come colonna. La proprietà **ColumnMapping** della colonna verrà impostata su **MappingType. Element**. Il testo degli elementi figlio è archiviato in una riga della tabella. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza produrrà una tabella denominata **Element1** con due colonne, **ChildElement1** e **ChildElement2**. La proprietà **ColumnMapping** di entrambe le colonne verrà impostata su **MappingType. Element**.  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
