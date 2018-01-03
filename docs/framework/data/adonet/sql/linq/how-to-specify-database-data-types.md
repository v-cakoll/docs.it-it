---
title: 'Procedura: specificare i tipi di dati del database'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 60f07a629c981eb0ad72f7c3e2d8537d5ca77515
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-database-data-types"></a>Procedura: specificare i tipi di dati del database
Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> proprietà in un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per specificare il testo esatto che definisce la colonna in una dichiarazione di tabella T-SQL.  
  
 È necessario specificare la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> solo se si prevede di usare <xref:System.Data.Linq.DataContext.CreateDatabase%2A> per creare un'istanza del database.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Per specificare il testo per definire un tipo di dati in una tabella T-SQL  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> specificando il testo esatto usato da T-SQL.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Procedura: personalizzare classi di entità mediante l'Editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
