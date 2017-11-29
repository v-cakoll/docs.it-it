---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5fa64c87bc4cd0c8dc677d8b4c59de45e31d3270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="c750c-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="c750c-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="c750c-103">Impossibile inserire il servizio del protocollo WS-AT in una transazione utilizzando il contesto di coordinamento fornito.</span><span class="sxs-lookup"><span data-stu-id="c750c-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c750c-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c750c-104">Description</span></span>  
 <span data-ttu-id="c750c-105">Traccia eseguita quando l'integrazione di MSDTC in una transazione non riesce per un protocollo 2pc specificato.</span><span class="sxs-lookup"><span data-stu-id="c750c-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="c750c-106">Questa situazione può verificarsi se la transazione non esiste più, se l'integrazione non è più consentita o se sono già presenti troppi elenchi.</span><span class="sxs-lookup"><span data-stu-id="c750c-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c750c-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c750c-107">Troubleshooting</span></span>  
 <span data-ttu-id="c750c-108">Controllare la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.</span><span class="sxs-lookup"><span data-stu-id="c750c-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c750c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c750c-109">See Also</span></span>  
 [<span data-ttu-id="c750c-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="c750c-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c750c-111">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="c750c-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c750c-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c750c-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
