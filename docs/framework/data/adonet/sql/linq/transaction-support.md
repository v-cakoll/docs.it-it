---
title: Supporto delle transazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 543ea3d1a0f767a10b36e040155e7e9304aca5a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="transaction-support"></a><span data-ttu-id="b4c81-102">Supporto delle transazioni</span><span class="sxs-lookup"><span data-stu-id="b4c81-102">Transaction Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="b4c81-103">supporta tre modelli di transazione distinti.</span><span class="sxs-lookup"><span data-stu-id="b4c81-103"> supports three distinct transaction models.</span></span> <span data-ttu-id="b4c81-104">Di seguito sono elencati tali modelli nell'ordine di esecuzione dei controlli.</span><span class="sxs-lookup"><span data-stu-id="b4c81-104">The following lists these models in the order of checks performed.</span></span>  
  
## <a name="explicit-local-transaction"></a><span data-ttu-id="b4c81-105">Transazione locale esplicita</span><span class="sxs-lookup"><span data-stu-id="b4c81-105">Explicit Local Transaction</span></span>  
 <span data-ttu-id="b4c81-106">Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, se la proprietà <xref:System.Data.Linq.DataContext.Transaction%2A> è impostata su una transazione (`IDbTransaction`), la chiamata <xref:System.Data.Linq.DataContext.SubmitChanges%2A> viene eseguita nel contesto della stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="b4c81-106">When <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called, if the <xref:System.Data.Linq.DataContext.Transaction%2A> property is set to a (`IDbTransaction`) transaction, the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> call is executed in the context of the same transaction.</span></span>  
  
 <span data-ttu-id="b4c81-107">È compito del programmatore eseguire il commit o il rollback della transazione dopo che ne è stata completata l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4c81-107">It is your responsibility to commit or rollback the transaction after successful execution of the transaction.</span></span> <span data-ttu-id="b4c81-108">La connessione corrispondente alla transazione deve essere la stessa usata per costruire <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="b4c81-108">The connection corresponding to the transaction must match the connection used for constructing the <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="b4c81-109">Se si usa una connessione diversa, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b4c81-109">An exception is thrown if a different connection is used.</span></span>  
  
## <a name="explicit-distributable-transaction"></a><span data-ttu-id="b4c81-110">Transazione distribuibile esplicita</span><span class="sxs-lookup"><span data-stu-id="b4c81-110">Explicit Distributable Transaction</span></span>  
 <span data-ttu-id="b4c81-111">È possibile chiamare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (inclusi, a titolo esemplificativo, <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) nell'ambito di un oggetto attivo <xref:System.Transactions.Transaction>.</span><span class="sxs-lookup"><span data-stu-id="b4c81-111">You can call [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (including but not limited to <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) in the scope of an active <xref:System.Transactions.Transaction>.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="b4c81-112">rileva che la chiamata è nell'ambito di una transazione e non crea una nuova transazione.</span><span class="sxs-lookup"><span data-stu-id="b4c81-112"> detects that the call is in the scope of a transaction and does not create a new transaction.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="b4c81-113">evita la chiusura della connessione in questo caso.</span><span class="sxs-lookup"><span data-stu-id="b4c81-113"> also avoids closing the connection in this case.</span></span> <span data-ttu-id="b4c81-114">Nel contesto di tale transazione è possibile eseguire query ed esecuzioni di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="b4c81-114">You can perform query and <xref:System.Data.Linq.DataContext.SubmitChanges%2A> executions in the context of such a transaction.</span></span>  
  
## <a name="implicit-transaction"></a><span data-ttu-id="b4c81-115">Transazione implicita</span><span class="sxs-lookup"><span data-stu-id="b4c81-115">Implicit Transaction</span></span>  
 <span data-ttu-id="b4c81-116">Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] controlla se la chiamata si trova nell'ambito di un <xref:System.Transactions.Transaction> o se il `Transaction` proprietà (`IDbTransaction`) è impostato su una transazione locale avviata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b4c81-116">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] checks to see whether the call is in the scope of a <xref:System.Transactions.Transaction> or if the `Transaction` property (`IDbTransaction`) is set to a user-started local transaction.</span></span> <span data-ttu-id="b4c81-117">Se trovata alcuna transazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] avvia una transazione locale (`IDbTransaction`) e lo usa per eseguire i comandi SQL generati.</span><span class="sxs-lookup"><span data-stu-id="b4c81-117">If it finds neither transaction, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a local transaction (`IDbTransaction`) and uses it to execute the generated SQL commands.</span></span> <span data-ttu-id="b4c81-118">Dopo aver completato correttamente l'esecuzione di tutti i comandi SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue il commit della transazione locale e lo restituisce.</span><span class="sxs-lookup"><span data-stu-id="b4c81-118">When all SQL commands have been successfully completed, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] commits the local transaction and returns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c81-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4c81-119">See Also</span></span>  
 [<span data-ttu-id="b4c81-120">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="b4c81-120">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="b4c81-121">Procedura: racchiudere tra parentesi quadre gli invii di dati utilizzando transazioni</span><span class="sxs-lookup"><span data-stu-id="b4c81-121">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
