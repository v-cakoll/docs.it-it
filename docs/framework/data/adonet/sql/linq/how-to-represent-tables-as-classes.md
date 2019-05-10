---
title: 'Procedura: Rappresentare tabelle come classi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: ff943fbc7ae137128d6c635fd2366ad14cf70d15
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620026"
---
# <a name="how-to-represent-tables-as-classes"></a>Procedura: Rappresentare tabelle come classi
Usare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attributo per definire una classe come classe di entità associata a una tabella di database.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Per eseguire il mapping di una classe a una tabella di database  
  
- Aggiungere l'attributo <xref:System.Data.Linq.Mapping.TableAttribute> alla dichiarazione di classe.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente la classe `Customer` viene definita come una classe di entità associata alla tabella di database `Customers`.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Non è necessario specificare la proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> se il nome può essere dedotto. Se non si specifica un nome, verrà usato lo stesso nome della proprietà o del campo.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità usando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
