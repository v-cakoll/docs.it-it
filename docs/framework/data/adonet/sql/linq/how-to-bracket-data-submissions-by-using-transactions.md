---
title: 'Procedura: Tra parentesi quadre gli invii di dati tramite transazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 2cbb50cc8762780849c337b597bbb36631c6ac1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584532"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="75dc6-102">Procedura: Tra parentesi quadre gli invii di dati tramite transazioni</span><span class="sxs-lookup"><span data-stu-id="75dc6-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="75dc6-103">È possibile usare <xref:System.Transactions.TransactionScope> per raggruppare gli invii al database.</span><span class="sxs-lookup"><span data-stu-id="75dc6-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="75dc6-104">Per altre informazioni, vedere [supporto delle transazioni](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="75dc6-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75dc6-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="75dc6-105">Example</span></span>  
 <span data-ttu-id="75dc6-106">Nel codice seguente l'invio al database viene incluso in <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="75dc6-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="75dc6-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75dc6-107">See also</span></span>
- [<span data-ttu-id="75dc6-108">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="75dc6-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="75dc6-109">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="75dc6-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="75dc6-110">Supporto delle transazioni</span><span class="sxs-lookup"><span data-stu-id="75dc6-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
