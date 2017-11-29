---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e3cbe9443f32ec9752198646e96cc1012d7343c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="a49c8-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="a49c8-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="a49c8-103">Servizio del protocollo WS-AT: impossibile registrare un partecipante per un protocollo di controllo.</span><span class="sxs-lookup"><span data-stu-id="a49c8-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a49c8-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a49c8-104">Description</span></span>  
 <span data-ttu-id="a49c8-105">Viene tracciato se MSDTC rileva una richiesta di registrazione non valida.</span><span class="sxs-lookup"><span data-stu-id="a49c8-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="a49c8-106">Può essere causato da più richieste di registrazione di completamento e da errori interni.</span><span class="sxs-lookup"><span data-stu-id="a49c8-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a49c8-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a49c8-107">Troubleshooting</span></span>  
 <span data-ttu-id="a49c8-108">Non tentare la registrazione di completamento più di una volta.</span><span class="sxs-lookup"><span data-stu-id="a49c8-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="a49c8-109">Controllare inoltre la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.</span><span class="sxs-lookup"><span data-stu-id="a49c8-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49c8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a49c8-110">See Also</span></span>  
 [<span data-ttu-id="a49c8-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="a49c8-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a49c8-112">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a49c8-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="a49c8-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="a49c8-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
