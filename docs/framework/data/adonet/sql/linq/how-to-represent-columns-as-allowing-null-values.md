---
title: "Procedura: Rappresentare colonne per l'accettazione di valori Null"
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 00a837467010c2d8a9f0ca16d6aba2fc5f4c973f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781813"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="55130-102">Procedura: Rappresentare colonne per l'accettazione di valori Null</span><span class="sxs-lookup"><span data-stu-id="55130-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="55130-103">Utilizzare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> proprietà sull'<xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per specificare che la colonna di database associata può mantenere i valori null.</span><span class="sxs-lookup"><span data-stu-id="55130-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="55130-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="55130-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="55130-105">Per definire una colonna in modo che accetti valori null</span><span class="sxs-lookup"><span data-stu-id="55130-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="55130-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="55130-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="55130-107">Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="55130-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55130-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55130-108">See also</span></span>

- [<span data-ttu-id="55130-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="55130-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="55130-110">Procedura: Personalizzare le classi di entità tramite l'editor di codice</span><span class="sxs-lookup"><span data-stu-id="55130-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
