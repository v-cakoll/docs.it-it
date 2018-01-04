---
title: System.ServiceModel.MessageClosedAgain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57500bf3c66c0aec47150bb21cc8871738d4b72d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="49b96-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="49b96-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="49b96-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="49b96-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="49b96-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49b96-104">Description</span></span>  
 <span data-ttu-id="49b96-105">Un messaggio è stato nuovamente chiuso.</span><span class="sxs-lookup"><span data-stu-id="49b96-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="49b96-106">Un messaggio deve essere chiuso solo una volta.</span><span class="sxs-lookup"><span data-stu-id="49b96-106">A message should be closed only once.</span></span> <span data-ttu-id="49b96-107">Se questa traccia viene emessa in codice di estensione utente, indica che tale codice sta chiudendo un messaggio che è già stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="49b96-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="49b96-108">Se viene emessa tramite codice del prodotto, indica che il codice di estensione utente potrebbe potenzialmente stare per chiudere un messaggio troppo presto.</span><span class="sxs-lookup"><span data-stu-id="49b96-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b96-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49b96-109">See Also</span></span>  
 [<span data-ttu-id="49b96-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="49b96-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="49b96-111">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="49b96-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="49b96-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="49b96-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
