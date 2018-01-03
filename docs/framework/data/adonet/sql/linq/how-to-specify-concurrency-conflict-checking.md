---
title: 'Procedura: specificare il controllo di conflitti di concorrenza'
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
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6e69b97de78c469bd252319c49d362fe96af6833
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="91c98-102">Procedura: specificare il controllo di conflitti di concorrenza</span><span class="sxs-lookup"><span data-stu-id="91c98-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="91c98-103">È possibile specificare in quali colonne del database deve essere effettuato il controllo dei conflitti di concorrenza quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="91c98-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="91c98-104">Per ulteriori informazioni, vedere [procedura: specificare che i membri vengono verificati i conflitti di concorrenza](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="91c98-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c98-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="91c98-105">Example</span></span>  
 <span data-ttu-id="91c98-106">Nel codice seguente viene specificato che il membro `HomePage` non dovrà mai essere testato durante i controlli di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="91c98-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="91c98-107">Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="91c98-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="91c98-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91c98-108">See Also</span></span>  
 [<span data-ttu-id="91c98-109">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="91c98-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="91c98-110">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="91c98-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
