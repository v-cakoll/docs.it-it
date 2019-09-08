---
title: 'Procedura: Rappresentare colonne come membri di classi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 515a8477b3a9c72934e0ad11d7b1bf599e8b16a2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793511"
---
# <a name="how-to-represent-columns-as-class-members"></a>Procedura: Rappresentare colonne come membri di classi
Utilizzare l' [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per associare un campo o una proprietà a una colonna del database.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>Per eseguire il mapping di un campo o una proprietà a una colonna del database  
  
- Aggiungere l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute> alla dichiarazione del campo o della proprietà.  
  
## <a name="example"></a>Esempio  
 Nelle mappe del codice riportate di seguito viene eseguito il mapping del campo `CustomerID` nella classe `Customer` alla colonna `CustomerID` nella tabella di database `Customers`.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Non è necessario specificare la proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> se il nome può essere dedotto. Se non si specifica un nome, verrà usato lo stesso nome della proprietà o del campo.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
