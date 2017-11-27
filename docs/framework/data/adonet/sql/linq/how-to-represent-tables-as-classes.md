---
title: 'Procedura: rappresentare tabelle come classi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d524daab97be56bc0b6b428b41dc1f3db2350f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="800ee-102">Procedura: rappresentare tabelle come classi</span><span class="sxs-lookup"><span data-stu-id="800ee-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="800ee-103">Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attributo per definire una classe come classe di entità associata a una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="800ee-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="800ee-104">Per eseguire il mapping di una classe a una tabella di database</span><span class="sxs-lookup"><span data-stu-id="800ee-104">To map a class to a database table</span></span>  
  
-   <span data-ttu-id="800ee-105">Aggiungere l'attributo <xref:System.Data.Linq.Mapping.TableAttribute> alla dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="800ee-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="800ee-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="800ee-106">Example</span></span>  
 <span data-ttu-id="800ee-107">Nel codice seguente la classe `Customer` viene definita come una classe di entità associata alla tabella di database `Customers`.</span><span class="sxs-lookup"><span data-stu-id="800ee-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="800ee-108">Non è necessario specificare la proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> se il nome può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="800ee-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="800ee-109">Se non si specifica un nome, verrà usato lo stesso nome della proprietà o del campo.</span><span class="sxs-lookup"><span data-stu-id="800ee-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800ee-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="800ee-110">See Also</span></span>  
 [<span data-ttu-id="800ee-111">LINQ to SQL modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="800ee-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="800ee-112">Procedura: personalizzare classi di entità utilizzando l'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="800ee-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
