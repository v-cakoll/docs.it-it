---
title: 'Procedura: Rappresentare colonne come generate dal database'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 2803697c668a8e1dbbeb426ea41b64878f70c145
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307912"
---
# <a name="how-to-represent-columns-as-database-generated"></a>Procedura: Rappresentare colonne come generate dal database
Usare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> proprietà di <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o proprietà che rappresenti una colonna generata da database.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>Per definire un campo o una proprietà che rappresenti una colonna generata da database  
  
1. Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Impostare il valore della proprietà su `true`.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare classi di entità mediante l'editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
