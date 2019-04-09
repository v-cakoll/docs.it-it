---
title: 'Procedura: Rappresentare le chiavi primarie'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 714211046afcafab4c2b67bf9318cfbede314476
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173212"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="f182f-102">Procedura: Rappresentare le chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="f182f-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="f182f-103">Usare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> proprietà di <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire una proprietà o campo che rappresenti la chiave primaria per una colonna del database.</span><span class="sxs-lookup"><span data-stu-id="f182f-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="f182f-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="f182f-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f182f-105">non supporta le colonne calcolate come chiavi primarie.</span><span class="sxs-lookup"><span data-stu-id="f182f-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="f182f-106">Per definire una proprietà o un campo come chiave primaria</span><span class="sxs-lookup"><span data-stu-id="f182f-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="f182f-107">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f182f-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="f182f-108">Specificare il valore come `true`.</span><span class="sxs-lookup"><span data-stu-id="f182f-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f182f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f182f-109">See also</span></span>

- [<span data-ttu-id="f182f-110">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f182f-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f182f-111">Procedura: Personalizzare classi di entità mediante l'editor del codice</span><span class="sxs-lookup"><span data-stu-id="f182f-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
