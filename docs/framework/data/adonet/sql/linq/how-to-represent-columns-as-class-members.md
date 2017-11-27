---
title: 'Procedura: rappresentare colonne come membri di classi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f0e797886b5e2fedafccf08b71e8cbb2791ea72b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-class-members"></a>Procedura: rappresentare colonne come membri di classi
Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per associare un campo o proprietà a una colonna del database.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>Per eseguire il mapping di un campo o una proprietà a una colonna del database  
  
-   Aggiungere l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute> alla dichiarazione del campo o della proprietà.  
  
## <a name="example"></a>Esempio  
 Nel codice riportato di seguito viene eseguito il mapping del campo `CustomerID` nella classe `Customer` alla colonna `CustomerID` nella tabella di database `Customers`.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Non è necessario specificare la proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> se il nome può essere dedotto. Se non si specifica un nome, verrà usato lo stesso nome della proprietà o del campo.  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ to SQL modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Procedura: personalizzare classi di entità utilizzando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
