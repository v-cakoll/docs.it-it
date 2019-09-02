---
title: Deduzione del testo dell'elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: d8d64c0cbb0aecf736a54fa6816e286ab7efa191
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203537"
---
# <a name="inferring-element-text"></a>Deduzione del testo dell'elemento
Se un elemento contiene testo e non ha elementi figlio da inferire come tabelle, ad esempio elementi con attributi o elementi ripetuti, viene aggiunta una nuova colonna con il nome **TableName_Text** alla tabella dedotta per l'elemento. Il testo contenuto nell'elemento viene aggiunto a una riga della tabella e archiviato nella nuova colonna. La proprietà **ColumnMapping** della nuova colonna verrà impostata su **MappingType. simpleContent**.  
  
 Ad esempio, si consideri il seguente codice XML.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza produrrà una tabella denominata **Element1** con due colonne: **attr1** e **Element1_Text**. La proprietà **ColumnMapping** della colonna **attr1** verrà impostata su **MappingType. Attribute**. La proprietà **ColumnMapping** della colonna **Element1_Text** verrà impostata su **MappingType. simpleContent**.  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Se in un elemento è presente del testo ma a tale elemento sono associati anche elementi figlio contenenti testo, alla tabella non verrà aggiunta alcuna colonna in cui archiviare il testo contenuto nell'elemento. Il testo contenuto nell'elemento verrà ignorato e il testo degli elementi figlio viene incluso in una riga della tabella. Ad esempio, si consideri il seguente codice XML.  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 Il processo di inferenza produrrà una tabella denominata **Element1** con una colonna denominata **ChildElement1**. Il testo per l'elemento **ChildElement1** verrà incluso in una riga della tabella. Il testo rimanente verrà ignorato. La proprietà **ColumnMapping** della colonna **ChildElement1** verrà impostata su **MappingType. Element**.  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
