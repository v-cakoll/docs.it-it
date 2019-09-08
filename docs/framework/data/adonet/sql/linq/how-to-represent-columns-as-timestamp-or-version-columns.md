---
title: 'Procedura: Rappresentare colonne come timestamp o colonne di versione'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: ef99e0420b328f94686e08256ecf229000467810
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793496"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>Procedura: Rappresentare colonne come timestamp o colonne di versione
Utilizzare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> proprietà dell'<xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o una proprietà che rappresenti una colonna del database che include timestamp o numeri di versione del database.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>Per definire un campo o una proprietà che rappresenti una colonna contenente timestamp o numeri di versione  
  
1. Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> su `true`.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedura: Specificare i membri sottoposti a test per i conflitti di concorrenza](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
