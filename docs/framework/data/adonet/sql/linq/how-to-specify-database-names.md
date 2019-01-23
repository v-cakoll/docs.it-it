---
title: 'Procedura: Specificare i nomi di Database'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: a1198a294cd4921728919981bae213c0ee891da6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556375"
---
# <a name="how-to-specify-database-names"></a>Procedura: Specificare i nomi di Database
Usare la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> su un attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> per specificare il nome di un database quando non viene fornito dalla connessione.  
  
 Per alcuni esempi di codice, vedere <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### <a name="to-specify-the-name-of-the-database"></a>Per specificare il nome del database  
  
1.  Aggiungere l'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> alla dichiarazione di classe per il database.  
  
2.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> all'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
3.  Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> sul nome che si desidera specificare.  
  
## <a name="see-also"></a>Vedere anche
- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità usando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
