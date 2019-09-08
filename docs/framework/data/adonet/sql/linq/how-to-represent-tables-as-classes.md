---
title: 'Procedura: Rappresentare tabelle come classi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 1169def4e0180b1d14103d4a968ff3ed56f63d0c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781753"
---
# <a name="how-to-represent-tables-as-classes"></a>Procedura: Rappresentare tabelle come classi
Utilizzare l' [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attributo per definire una classe come classe di entità associata a una tabella di database.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Per eseguire il mapping di una classe a una tabella di database  
  
- Aggiungere l'attributo <xref:System.Data.Linq.Mapping.TableAttribute> alla dichiarazione di classe.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente la classe `Customer` viene definita come una classe di entità associata alla tabella di database `Customers`.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Non è necessario specificare la proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> se il nome può essere dedotto. Se non si specifica un nome, verrà usato lo stesso nome della proprietà o del campo.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
