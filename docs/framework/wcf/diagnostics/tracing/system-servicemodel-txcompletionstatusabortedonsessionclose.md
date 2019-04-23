---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166504"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="ef837-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="ef837-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="ef837-103">La transazione specificata è stata interrotta perché non era stata completata alla chiusura della sessione e TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute era impostato su False.</span><span class="sxs-lookup"><span data-stu-id="ef837-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ef837-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef837-104">Description</span></span>  
 <span data-ttu-id="ef837-105">Viene tracciato se la sessione attiva corrente è stata chiusa prima del completamento della transazione e se TransactionAutoCompleteOnSessionClose è impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="ef837-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ef837-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ef837-106">Troubleshooting</span></span>  
 <span data-ttu-id="ef837-107">Questa traccia indica un bug potenziale dell'applicazione che deve essere esaminato.</span><span class="sxs-lookup"><span data-stu-id="ef837-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef837-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef837-108">See also</span></span>

- [<span data-ttu-id="ef837-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="ef837-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ef837-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="ef837-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ef837-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="ef837-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
