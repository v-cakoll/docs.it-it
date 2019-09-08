---
title: 'Procedura: Rappresentare le chiavi primarie'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 5df82292f000d7f5e61cab699237b86de30bda70
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793435"
---
# <a name="how-to-represent-primary-keys"></a>Procedura: Rappresentare le chiavi primarie
Utilizzare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> proprietà sull'<xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire una proprietà o un campo per rappresentare la chiave primaria per una colonna del database.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
> In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportate colonne calcolate come chiavi primarie.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Per definire una proprietà o un campo come chiave primaria  
  
1. Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Specificare il valore come `true`.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
