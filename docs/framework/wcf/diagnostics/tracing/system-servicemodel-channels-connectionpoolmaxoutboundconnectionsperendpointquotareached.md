---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 742e80a3115e8f8caa728e0d8c460ee8b964ddc9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84588717"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="c4429-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="c4429-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="c4429-103">Impossibile inserire il servizio del protocollo WS-AT in una transazione utilizzando il contesto di coordinamento fornito.</span><span class="sxs-lookup"><span data-stu-id="c4429-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c4429-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4429-104">Description</span></span>  
 <span data-ttu-id="c4429-105">Traccia eseguita quando l'integrazione di MSDTC in una transazione non riesce per un protocollo 2pc specificato.</span><span class="sxs-lookup"><span data-stu-id="c4429-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="c4429-106">Questa situazione può verificarsi se la transazione non esiste più, se l'integrazione non è più consentita o se sono già presenti troppi elenchi.</span><span class="sxs-lookup"><span data-stu-id="c4429-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c4429-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c4429-107">Troubleshooting</span></span>  
 <span data-ttu-id="c4429-108">Controllare la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.</span><span class="sxs-lookup"><span data-stu-id="c4429-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4429-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4429-109">See also</span></span>

- [<span data-ttu-id="c4429-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="c4429-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="c4429-111">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="c4429-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c4429-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c4429-112">Administration and Diagnostics</span></span>](../index.md)
