---
title: "Procedura: rappresentare colonne per l'accettazione di valori Null"
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 6700ee5d4de53dd82da29d48ca7c42785d52afc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355977"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="a1281-102">Procedura: rappresentare colonne per l'accettazione di valori Null</span><span class="sxs-lookup"><span data-stu-id="a1281-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="a1281-103">Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> proprietà il <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per specificare che la colonna di database associata può contenere valori null.</span><span class="sxs-lookup"><span data-stu-id="a1281-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="a1281-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="a1281-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="a1281-105">Per definire una colonna in modo che accetti valori null</span><span class="sxs-lookup"><span data-stu-id="a1281-105">To designate a column as allowing null values</span></span>  
  
1.  <span data-ttu-id="a1281-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a1281-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="a1281-107">Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a1281-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1281-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1281-108">See Also</span></span>  
 [<span data-ttu-id="a1281-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a1281-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="a1281-110">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="a1281-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
