---
title: 'Procedura: Rappresentare colonne come generate dal database'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: bb9510986581ad6d3bcd0711aed681ef3a7c4e45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781791"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="069dc-102">Procedura: Rappresentare colonne come generate dal database</span><span class="sxs-lookup"><span data-stu-id="069dc-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="069dc-103">Utilizzare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> proprietà sull'<xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o una proprietà che rappresenti una colonna generata dal database.</span><span class="sxs-lookup"><span data-stu-id="069dc-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="069dc-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="069dc-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="069dc-105">Per definire un campo o una proprietà che rappresenti una colonna generata da database</span><span class="sxs-lookup"><span data-stu-id="069dc-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="069dc-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="069dc-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="069dc-107">Impostare il valore della proprietà su `true`.</span><span class="sxs-lookup"><span data-stu-id="069dc-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="069dc-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="069dc-108">See also</span></span>

- [<span data-ttu-id="069dc-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="069dc-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="069dc-110">Procedura: Personalizzare le classi di entità tramite l'editor di codice</span><span class="sxs-lookup"><span data-stu-id="069dc-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
