---
title: 'Procedura: rappresentare colonne calcolate'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: c53c781e8d4ec6836e032120816c3ef55de2ae0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-represent-computed-columns"></a>Procedura: rappresentare colonne calcolate
Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> proprietà in un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per rappresentare una colonna il cui contenuto è il risultato del calcolo.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportate colonne calcolate come chiavi primarie.  
  
### <a name="to-represent-a-computed-column"></a>Per rappresentare una colonna calcolata  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Assegnare una rappresentazione di stringa della formula alla proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Procedura: personalizzare classi di entità mediante l'Editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
