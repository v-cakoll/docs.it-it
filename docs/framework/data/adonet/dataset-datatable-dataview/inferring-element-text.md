---
title: Deduzione del testo dell'elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 6ffe8f2fbf01fbe8dfa9d78f3dfb9e39b6e80b16
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224962"
---
# <a name="inferring-element-text"></a>Deduzione del testo dell'elemento
Se un elemento contiene testo e non contiene elementi figlio da inferire come tabelle, ad esempio (elementi con attributi) o elementi ripetuti, una nuova colonna con il nome **TableName_Text** verranno aggiunti alla tabella inferita per l'elemento. Il testo contenuto nell'elemento viene aggiunto a una riga della tabella e archiviato nella nuova colonna. Il **ColumnMapping** della nuova colonna verrà impostata su **MappingType**.  
  
 Ad esempio, si consideri il seguente codice XML.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza genererà una tabella denominata **Element1** con due colonne: **attr1** e **Element1_Text**. Il **ColumnMapping** proprietà delle **attr1** colonna verrà impostata su **MappingType**. Il **ColumnMapping** proprietà delle **Element1_Text** colonna verrà impostata su **MappingType**.  
  
 **DataSet:** DocumentElement  
  
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
  
 Il processo di inferenza genererà una tabella denominata **Element1** con una sola colonna denominata **ChildElement1**. Il testo per il **ChildElement1** elemento verrà incluso in una riga nella tabella. Il testo rimanente verrà ignorato. Il **ColumnMapping** proprietà delle **ChildElement1** colonna verrà impostata su **MappingType**.  
  
 **DataSet:** DocumentElement  
  
 **tavolo:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di dataset da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un dataset da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema di dataset da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Utilizzo di XML in un dataset](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
