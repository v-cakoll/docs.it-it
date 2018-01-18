---
title: Deduzione del testo dell'elemento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 239c70ca0e7f8894b988f17d248b2e5b3b98bf6a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-element-text"></a>Deduzione del testo dell'elemento
Se un elemento contiene testo e non contiene elementi figlio da inferire come tabelle, ad esempio (elementi con attributi) o elementi ripetuti, una nuova colonna con il nome **TableName_Text** verranno aggiunti alla tabella inferita per l'elemento. Il testo contenuto nell'elemento viene aggiunto a una riga della tabella e archiviato nella nuova colonna. Il **ColumnMapping** della nuova colonna verrà impostata su **MappingType**.  
  
 Ad esempio, si consideri il seguente codice XML.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza genererà una tabella denominata **Element1** con due colonne: **attr1** e **Element1_Text**. Il **ColumnMapping** proprietà del **attr1** colonna verrà impostata su **MappingType. Attribute**. Il **ColumnMapping** proprietà del **Element1_Text** colonna verrà impostata su **MappingType**.  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
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
  
 Il processo di inferenza genererà una tabella denominata **Element1** con una colonna denominata **ChildElement1**. Il testo per il **ChildElement1** elemento verrà inclusi in una riga nella tabella. Il testo rimanente verrà ignorato. Il **ColumnMapping** proprietà del **ChildElement1** colonna verrà impostata su **MappingType**.  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Vedere anche  
 [Deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
