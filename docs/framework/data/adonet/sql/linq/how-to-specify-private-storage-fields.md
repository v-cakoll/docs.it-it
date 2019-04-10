---
title: 'Procedura: Specificare campi di archiviazione privati'
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: 843b7ae8dbddb76e0e5fa33d3594a5655dbf1a37
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302452"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="c40e2-102">Procedura: Specificare campi di archiviazione privati</span><span class="sxs-lookup"><span data-stu-id="c40e2-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="c40e2-103">Usare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> proprietà di <xref:System.Data.Linq.Mapping.DataAttribute> attributo per definire il nome di un campo di archiviazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="c40e2-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="c40e2-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="c40e2-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="c40e2-105">Per specificare il nome di un campo di archiviazione sottostante</span><span class="sxs-lookup"><span data-stu-id="c40e2-105">To specify the name of an underlying storage field</span></span>  
  
1. <span data-ttu-id="c40e2-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c40e2-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="c40e2-107">Assegnare il nome del campo come valore della proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="c40e2-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40e2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c40e2-108">See also</span></span>

- [<span data-ttu-id="c40e2-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c40e2-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c40e2-110">Procedura: Personalizzare classi di entità mediante l'editor del codice</span><span class="sxs-lookup"><span data-stu-id="c40e2-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
