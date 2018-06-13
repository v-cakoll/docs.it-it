---
title: 'Procedura: specificare nomi di database'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: a69fa1723c0660d3c6dfa8bfa7ec3b9e4dc75d7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361585"
---
# <a name="how-to-specify-database-names"></a>Procedura: specificare nomi di database
Usare la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> su un attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> per specificare il nome di un database quando non viene fornito dalla connessione.  
  
 Per alcuni esempi di codice, vedere <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### <a name="to-specify-the-name-of-the-database"></a>Per specificare il nome del database  
  
1.  Aggiungere l'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> alla dichiarazione di classe per il database.  
  
2.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> all'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
3.  Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> sul nome che si desidera specificare.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Procedura: personalizzare classi di entità mediante l'Editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
