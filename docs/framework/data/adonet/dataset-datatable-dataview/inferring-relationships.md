---
title: Deduzione di relazioni
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 9833966fa5a16bef70a6ae2b9ca618fde0e05fbb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759036"
---
# <a name="inferring-relationships"></a>Deduzione di relazioni
Se a un elemento inferito come tabella è associato un elemento figlio a sua volta inferito come tabella, tra le due tabelle verrà creato un tipo <xref:System.Data.DataRelation>. Una nuova colonna con un nome di **ParentTableName_Id** verranno aggiunti alla tabella creata per l'elemento padre e la tabella creata per l'elemento figlio. Il **ColumnMapping** della colonna identity verrà impostata su **MappingType**. La colonna sarà una chiave primaria con incremento automatico per la tabella padre e verrà utilizzata per il **DataRelation** tra le due tabelle. Il tipo di dati della colonna identity aggiunta sarà **System. Int32**, a differenza del tipo di dati di tutte le altre colonne inferite, che è **System. String**. Oggetto <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** verrà creata anche usando la nuova colonna nelle tabelle padre e figlio.  
  
 Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza verrà prodotte due tabelle: **Element1** e **ChildElement1**.  
  
 Il **Element1** tabella sarà presenti due colonne: **Element1_Id** e **ChildElement2**. Il **ColumnMapping** proprietà del **Element1_Id** colonna verrà impostata su **MappingType**. Il **ColumnMapping** proprietà del **ChildElement2** colonna verrà impostata su **MappingType**. Il **Element1_Id** verrà impostata come chiave primaria della colonna di **Element1** tabella.  
  
 Il **ChildElement1** tabella sarà presenti tre colonne: **attr1**, **attr2** e **Element1_Id**. Il **ColumnMapping** proprietà per il **attr1** e **attr2** colonne verranno impostate su **MappingType. Attribute**. Il **ColumnMapping** proprietà del **Element1_Id** colonna verrà impostata su **MappingType**.  
  
 Oggetto **DataRelation** e **ForeignKeyConstraint** verrà creata utilizzando il **Element1_Id** le colonne di entrambe le tabelle.  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabella:** ChildElement1  
  
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
 [Deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
