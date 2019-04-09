---
title: Deduzione di relazioni
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: f8a9aba493dfe82466608ea60932ddfec5ef64f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127881"
---
# <a name="inferring-relationships"></a>Deduzione di relazioni
Se a un elemento inferito come tabella è associato un elemento figlio a sua volta inferito come tabella, tra le due tabelle verrà creato un tipo <xref:System.Data.DataRelation>. Una nuova colonna con il nome **ParentTableName_Id** verranno aggiunti alla tabella creata per l'elemento padre sia la tabella creata per l'elemento figlio. Il **ColumnMapping** della colonna identity verrà impostata su **MappingType**. La colonna sarà una chiave primaria con incremento automatico per la tabella padre e verrà usata per il **DataRelation** tra le due tabelle. Il tipo di dati della colonna identity aggiunta sarà **System.Int32**, a differenza del tipo di dati di tutte le altre colonne inferite, ovvero **System. String**. Oggetto <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** verrà inoltre creato usando la nuova colonna nelle tabelle padre e figlio.  
  
 Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Dal processo di inferenza verranno prodotte due tabelle: **Element1** e **ChildElement1**.  
  
 Il **Element1** tabella sarà presenti due colonne: **Element1_Id** e **ChildElement2**. Il **ColumnMapping** proprietà delle **Element1_Id** colonna verrà impostata su **MappingType**. Il **ColumnMapping** proprietà delle **ChildElement2** colonna verrà impostata su **MappingType**. Il **Element1_Id** verrà impostata come chiave primaria della colonna la **Element1** tabella.  
  
 Il **ChildElement1** tabella sarà presenti tre colonne: **attr1**, **attr2** e **Element1_Id**. Il **ColumnMapping** proprietà per il **attr1** e **attr2** colonne verranno impostate su **MappingType**. Il **ColumnMapping** proprietà delle **Element1_Id** colonna verrà impostata su **MappingType**.  
  
 Oggetto **DataRelation** e **ForeignKeyConstraint** verrà creato utilizzando il **Element1_Id** colonne di entrambe le tabelle.  
  
 **DataSet:** DocumentElement  
  
 **tavolo:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **tavolo:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Annidati:** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Colonna:** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** nessuno  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di dataset da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un dataset da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema di dataset da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [Utilizzo di XML in un dataset](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
