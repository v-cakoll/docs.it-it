---
title: 'Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 47e1e45cfe693e3569c343f1058ce2d610af96dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163150"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="e05de-102">Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext</span><span class="sxs-lookup"><span data-stu-id="e05de-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="e05de-103">In quanto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fa parte del [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] famiglia di tecnologie e si basa sui servizi forniti dai [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], è possibile riutilizzare una connessione tra un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] comando e un <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="e05de-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e05de-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e05de-104">Example</span></span>  
 <span data-ttu-id="e05de-105">Nell'esempio seguente viene illustrato come riutilizzare la stessa connessione tra un comando [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] e <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="e05de-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e05de-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e05de-106">See also</span></span>

- [<span data-ttu-id="e05de-107">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="e05de-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="e05de-108">ADO.NET e LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e05de-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="e05de-109">Comunicazione con il database</span><span class="sxs-lookup"><span data-stu-id="e05de-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
