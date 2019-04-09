---
title: "Procedura: Rappresentare colonne per l'accettazione di valori Null"
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: e3bab3f307bcba77e0d311b96fa79d5a0d01e937
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169637"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>Procedura: Rappresentare colonne per l'accettazione di valori Null
Usare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> proprietà di <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per specificare che la colonna di database associato può contenere valori null.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>Per definire una colonna in modo che accetti valori null  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> su `true`.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare classi di entità mediante l'editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
