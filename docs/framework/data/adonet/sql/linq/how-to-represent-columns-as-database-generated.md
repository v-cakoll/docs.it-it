---
title: 'Procedura: Rappresentare colonne come generate dal Database'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 572da93c216694b496dc5220af66bc00229ccd00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518345"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="0f70e-102">Procedura: Rappresentare colonne come generate dal Database</span><span class="sxs-lookup"><span data-stu-id="0f70e-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="0f70e-103">Usare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> proprietà di <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o proprietà che rappresenti una colonna generata da database.</span><span class="sxs-lookup"><span data-stu-id="0f70e-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="0f70e-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f70e-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="0f70e-105">Per definire un campo o una proprietà che rappresenti una colonna generata da database</span><span class="sxs-lookup"><span data-stu-id="0f70e-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="0f70e-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0f70e-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="0f70e-107">Impostare il valore della proprietà su `true`.</span><span class="sxs-lookup"><span data-stu-id="0f70e-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f70e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f70e-108">See also</span></span>
- [<span data-ttu-id="0f70e-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0f70e-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="0f70e-110">Procedura: Personalizzare le classi di entità usando l'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="0f70e-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
