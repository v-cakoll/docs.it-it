---
title: 'Procedura: Specificare i tipi di dati del database'
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 67f23ff06aefbcff4ba7e2eaab63d9b8493b9717
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033670"
---
# <a name="how-to-specify-database-data-types"></a>Procedura: Specificare i tipi di dati del database
Usare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> proprietà su un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per specificare il testo esatto che definisce la colonna in una dichiarazione di tabella T-SQL.  
  
 È necessario specificare la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> solo se si prevede di usare <xref:System.Data.Linq.DataContext.CreateDatabase%2A> per creare un'istanza del database.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Per specificare il testo per definire un tipo di dati in una tabella T-SQL  
  
1. Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> specificando il testo esatto usato da T-SQL.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità usando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
