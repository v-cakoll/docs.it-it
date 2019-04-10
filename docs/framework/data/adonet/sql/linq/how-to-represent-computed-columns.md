---
title: 'Procedura: Rappresentare colonne calcolate'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: df72562b303e5b9a7c31334df06926f157b59b05
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324740"
---
# <a name="how-to-represent-computed-columns"></a>Procedura: Rappresentare colonne calcolate
Usare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> proprietà su un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per rappresentare una colonna il cui contenuto è il risultato del calcolo.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta le colonne calcolate come chiavi primarie.  
  
### <a name="to-represent-a-computed-column"></a>Per rappresentare una colonna calcolata  
  
1. Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Assegnare una rappresentazione di stringa della formula alla proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare classi di entità mediante l'editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
