---
title: 'Procedura: Rappresentare colonne calcolate'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: f624bb49773af2c0053851ac55727b6db8632131
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204120"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="e1391-102">Procedura: Rappresentare colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="e1391-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="e1391-103">Usare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> proprietà su un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per rappresentare una colonna il cui contenuto è il risultato del calcolo.</span><span class="sxs-lookup"><span data-stu-id="e1391-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="e1391-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="e1391-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e1391-105">non supporta le colonne calcolate come chiavi primarie.</span><span class="sxs-lookup"><span data-stu-id="e1391-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="e1391-106">Per rappresentare una colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="e1391-106">To represent a computed column</span></span>  
  
1.  <span data-ttu-id="e1391-107">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e1391-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="e1391-108">Assegnare una rappresentazione di stringa della formula alla proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="e1391-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1391-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1391-109">See also</span></span>

- [<span data-ttu-id="e1391-110">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e1391-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="e1391-111">Procedura: Personalizzare classi di entità mediante l'editor del codice</span><span class="sxs-lookup"><span data-stu-id="e1391-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
