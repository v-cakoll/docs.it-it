---
title: 'Procedura: Rappresentare le chiavi primarie'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: dcb8929c9cd9a7b88f19d760b70117a1092760f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295588"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="b7dec-102">Procedura: Rappresentare le chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="b7dec-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="b7dec-103">Usare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> proprietà di <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire una proprietà o campo che rappresenti la chiave primaria per una colonna del database.</span><span class="sxs-lookup"><span data-stu-id="b7dec-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="b7dec-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="b7dec-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7dec-105">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportate colonne calcolate come chiavi primarie.</span><span class="sxs-lookup"><span data-stu-id="b7dec-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="b7dec-106">Per definire una proprietà o un campo come chiave primaria</span><span class="sxs-lookup"><span data-stu-id="b7dec-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="b7dec-107">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b7dec-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b7dec-108">Specificare il valore come `true`.</span><span class="sxs-lookup"><span data-stu-id="b7dec-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7dec-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7dec-109">See also</span></span>

- [<span data-ttu-id="b7dec-110">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b7dec-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="b7dec-111">Procedura: Personalizzare le classi di entità usando l'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="b7dec-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
