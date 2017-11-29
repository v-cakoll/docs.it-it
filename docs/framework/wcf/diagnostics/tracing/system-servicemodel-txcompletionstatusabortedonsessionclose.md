---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1e9ab5af359b833452664f534e3627f477246fa6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="2da10-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="2da10-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="2da10-103">La transazione specificata è stata interrotta perché non era stata completata alla chiusura della sessione e TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute era impostato su False.</span><span class="sxs-lookup"><span data-stu-id="2da10-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2da10-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2da10-104">Description</span></span>  
 <span data-ttu-id="2da10-105">Viene tracciato se la sessione attiva corrente è stata chiusa prima del completamento della transazione e se TransactionAutoCompleteOnSessionClose è impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="2da10-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2da10-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="2da10-106">Troubleshooting</span></span>  
 <span data-ttu-id="2da10-107">Questa traccia indica un bug potenziale dell'applicazione che deve essere esaminato.</span><span class="sxs-lookup"><span data-stu-id="2da10-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da10-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2da10-108">See Also</span></span>  
 [<span data-ttu-id="2da10-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="2da10-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2da10-110">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="2da10-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2da10-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="2da10-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
