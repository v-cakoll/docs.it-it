---
title: 'Procedura: specificare campi di archiviazione privati'
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: d8a9bacd88b08384e7619dc64ab86cb0651ac44d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361598"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="d31c6-102">Procedura: specificare campi di archiviazione privati</span><span class="sxs-lookup"><span data-stu-id="d31c6-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="d31c6-103">Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> proprietà il <xref:System.Data.Linq.Mapping.DataAttribute> attributo per definire il nome di un campo di archiviazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="d31c6-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="d31c6-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="d31c6-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="d31c6-105">Per specificare il nome di un campo di archiviazione sottostante</span><span class="sxs-lookup"><span data-stu-id="d31c6-105">To specify the name of an underlying storage field</span></span>  
  
1.  <span data-ttu-id="d31c6-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d31c6-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="d31c6-107">Assegnare il nome del campo come valore della proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="d31c6-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31c6-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d31c6-108">See Also</span></span>  
 [<span data-ttu-id="d31c6-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d31c6-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="d31c6-110">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="d31c6-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
