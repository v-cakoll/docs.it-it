---
title: 'Procedura: rappresentare colonne come timestamp o versioni'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: 2fc8aaf260dc3657e33e539939fdf58ad8224c93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361239"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="1296b-102">Procedura: rappresentare colonne come timestamp o versioni</span><span class="sxs-lookup"><span data-stu-id="1296b-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="1296b-103">Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> proprietà del <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per definire un campo o proprietà che rappresenti una colonna di database che contiene i database timestamp o numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="1296b-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="1296b-104">Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="1296b-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="1296b-105">Per definire un campo o una proprietà che rappresenti una colonna contenente timestamp o numeri di versione</span><span class="sxs-lookup"><span data-stu-id="1296b-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1.  <span data-ttu-id="1296b-106">Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1296b-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="1296b-107">Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="1296b-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1296b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1296b-108">See Also</span></span>  
 [<span data-ttu-id="1296b-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1296b-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="1296b-110">Procedura: specificare per quali membri viene eseguito il test dei conflitti di concorrenza</span><span class="sxs-lookup"><span data-stu-id="1296b-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 [<span data-ttu-id="1296b-111">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="1296b-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
