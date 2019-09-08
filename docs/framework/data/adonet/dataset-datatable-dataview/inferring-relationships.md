---
title: Deduzione di relazioni
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 4c9c13453e4a830fcda337e8163649ba6491a995
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785367"
---
# <a name="inferring-relationships"></a>Deduzione di relazioni
Se a un elemento inferito come tabella è associato un elemento figlio a sua volta inferito come tabella, tra le due tabelle verrà creato un tipo <xref:System.Data.DataRelation>. Una nuova colonna con nome **ParentTableName_Id** verrà aggiunta sia alla tabella creata per l'elemento padre che alla tabella creata per l'elemento figlio. La proprietà **ColumnMapping** della colonna Identity verrà impostata su **MappingType. Hidden**. La colonna sarà una chiave primaria a incremento automatico per la tabella padre e verrà utilizzata per la **DataRelation** tra le due tabelle. Il tipo di dati della colonna Identity aggiunta sarà **System. Int32**, a differenza del tipo di dati di tutte le altre colonne inferite, ovvero **System. String**. Verrà <xref:System.Data.ForeignKeyConstraint> creato anche un oggetto con **DeleteRule** = **Cascade** usando la nuova colonna in entrambe le tabelle padre e figlio.  
  
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
  
 La tabella **Element1** includerà due colonne: **Element1_Id** e **ChildElement2**. La proprietà **ColumnMapping** della colonna **Element1_Id** verrà impostata su **MappingType. Hidden**. La proprietà **ColumnMapping** della colonna **ChildElement2** verrà impostata su **MappingType. Element**. La colonna **Element1_Id** verrà impostata come chiave primaria della tabella **Element1** .  
  
 La tabella **ChildElement1** includerà tre colonne: **attr1**, **attr2** e **Element1_Id**. La proprietà **ColumnMapping** per le colonne **attr1** e **attr2** verrà impostata su **MappingType. Attribute**. La proprietà **ColumnMapping** della colonna **Element1_Id** verrà impostata su **MappingType. Hidden**.  
  
 Verranno creati un oggetto **DataRelation** e **ForeignKeyConstraint** usando le colonne **Element1_Id** di entrambe le tabelle.  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **tavolo:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation** Element1_ChildElement1  
  
 **ParentTable** Element1  
  
 **ParentColumn** Element1_Id  
  
 **ChildTable** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Annidati** True  
  
 **ForeignKeyConstraint** Element1_ChildElement1  
  
 **Colonna** Element1_Id  
  
 **ParentTable** Element1  
  
 **ChildTable** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** Nessuna  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Annidamento di oggetti DataRelation](nesting-datarelations.md)
- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
