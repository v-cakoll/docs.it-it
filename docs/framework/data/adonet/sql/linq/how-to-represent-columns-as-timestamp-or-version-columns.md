---
title: 'Procedura: Rappresentare colonne come timestamp o colonne di versione'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: db73bf4880d8f5556247f7b037fca24b0ddc56d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297889"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="eac97-102">Procedura: Rappresentare colonne come timestamp o colonne di versione</span><span class="sxs-lookup"><span data-stu-id="eac97-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="eac97-103">Usare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> proprietà del <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o proprietà che rappresenti una colonna del database che contiene i database timestamp o numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="eac97-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="eac97-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="eac97-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="eac97-105">Per definire un campo o una proprietà che rappresenti una colonna contenente timestamp o numeri di versione</span><span class="sxs-lookup"><span data-stu-id="eac97-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1. <span data-ttu-id="eac97-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="eac97-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="eac97-107">Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="eac97-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac97-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eac97-108">See also</span></span>

- [<span data-ttu-id="eac97-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="eac97-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="eac97-110">Procedura: Specificare che i membri vengono verificati i conflitti di concorrenza</span><span class="sxs-lookup"><span data-stu-id="eac97-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="eac97-111">Procedura: Personalizzare le classi di entità usando l'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="eac97-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
