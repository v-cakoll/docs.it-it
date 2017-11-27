---
title: 'Procedura: rappresentare le chiavi primarie'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3510d52f6f6de9ee2e99ebc1e9fc6fa581d58f3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-primary-keys"></a>Procedura: rappresentare le chiavi primarie
Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> proprietà il <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire una proprietà o campo che rappresenti la chiave primaria per una colonna del database.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
>  In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportate colonne calcolate come chiavi primarie.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Per definire una proprietà o un campo come chiave primaria  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Specificare il valore come `true`.  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ to SQL modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Procedura: personalizzare classi di entità utilizzando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
