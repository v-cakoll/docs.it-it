---
title: 'Procedura: rappresentare colonne come timestamp o versioni'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 465be5cc0125d0ac45c0a00d7f1f238f3de8a390
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="86a9a-102">Procedura: rappresentare colonne come timestamp o versioni</span><span class="sxs-lookup"><span data-stu-id="86a9a-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="86a9a-103">Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> proprietà del <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o proprietà che rappresenti una colonna di database che contiene i database timestamp o numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="86a9a-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="86a9a-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="86a9a-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="86a9a-105">Per definire un campo o una proprietà che rappresenti una colonna contenente timestamp o numeri di versione</span><span class="sxs-lookup"><span data-stu-id="86a9a-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1.  <span data-ttu-id="86a9a-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="86a9a-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="86a9a-107">Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="86a9a-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a9a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86a9a-108">See Also</span></span>  
 [<span data-ttu-id="86a9a-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="86a9a-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="86a9a-110">Procedura: specificare per quali membri viene eseguito il test dei conflitti di concorrenza</span><span class="sxs-lookup"><span data-stu-id="86a9a-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 [<span data-ttu-id="86a9a-111">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="86a9a-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
