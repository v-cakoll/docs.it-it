---
title: 'Procedura: specificare campi di archiviazione privati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 776095db1696a604e4e9a8344a41f319d718bf01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="b092b-102">Procedura: specificare campi di archiviazione privati</span><span class="sxs-lookup"><span data-stu-id="b092b-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="b092b-103">Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> proprietà il <xref:System.Data.Linq.Mapping.DataAttribute> attributo per definire il nome di un campo di archiviazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="b092b-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="b092b-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="b092b-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="b092b-105">Per specificare il nome di un campo di archiviazione sottostante</span><span class="sxs-lookup"><span data-stu-id="b092b-105">To specify the name of an underlying storage field</span></span>  
  
1.  <span data-ttu-id="b092b-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b092b-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="b092b-107">Assegnare il nome del campo come valore della proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="b092b-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b092b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b092b-108">See Also</span></span>  
 [<span data-ttu-id="b092b-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b092b-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="b092b-110">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="b092b-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
