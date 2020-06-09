---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: c398fc52d5924c033500b95924f9287b43cc9e9d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576603"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="8abe7-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="8abe7-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="8abe7-103">La transazione specificata è stata interrotta perché non era stata completata alla chiusura della sessione e TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute era impostato su False.</span><span class="sxs-lookup"><span data-stu-id="8abe7-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8abe7-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8abe7-104">Description</span></span>  
 <span data-ttu-id="8abe7-105">Viene tracciato se la sessione attiva corrente è stata chiusa prima del completamento della transazione e se TransactionAutoCompleteOnSessionClose è impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="8abe7-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8abe7-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="8abe7-106">Troubleshooting</span></span>  
 <span data-ttu-id="8abe7-107">Questa traccia indica un bug potenziale dell'applicazione che deve essere esaminato.</span><span class="sxs-lookup"><span data-stu-id="8abe7-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8abe7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8abe7-108">See also</span></span>

- [<span data-ttu-id="8abe7-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="8abe7-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="8abe7-110">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="8abe7-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8abe7-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="8abe7-111">Administration and Diagnostics</span></span>](../index.md)
