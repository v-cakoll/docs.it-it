---
title: 'Procedura: rappresentare colonne come generate dal database'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: f6b127208ae359b43f273f54d7b5c72933c2eba6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353741"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="95f79-102">Procedura: rappresentare colonne come generate dal database</span><span class="sxs-lookup"><span data-stu-id="95f79-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="95f79-103">Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> proprietà il <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o proprietà che rappresenti una colonna generata da database.</span><span class="sxs-lookup"><span data-stu-id="95f79-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="95f79-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="95f79-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="95f79-105">Per definire un campo o una proprietà che rappresenti una colonna generata da database</span><span class="sxs-lookup"><span data-stu-id="95f79-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="95f79-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="95f79-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="95f79-107">Impostare il valore della proprietà su `true`.</span><span class="sxs-lookup"><span data-stu-id="95f79-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f79-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95f79-108">See Also</span></span>  
 [<span data-ttu-id="95f79-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="95f79-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="95f79-110">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="95f79-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
