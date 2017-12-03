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
ms.openlocfilehash: ec4a0acc70f1878756776d7ed8e8d8e5ee64035f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="527bd-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="527bd-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="527bd-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="527bd-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="527bd-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="527bd-104">Description</span></span>  
 <span data-ttu-id="527bd-105">Un messaggio è stato nuovamente chiuso.</span><span class="sxs-lookup"><span data-stu-id="527bd-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="527bd-106">Un messaggio deve essere chiuso solo una volta.</span><span class="sxs-lookup"><span data-stu-id="527bd-106">A message should be closed only once.</span></span> <span data-ttu-id="527bd-107">Se questa traccia viene emessa in codice di estensione utente, indica che tale codice sta chiudendo un messaggio che è già stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="527bd-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="527bd-108">Se viene emessa tramite codice del prodotto, indica che il codice di estensione utente potrebbe potenzialmente stare per chiudere un messaggio troppo presto.</span><span class="sxs-lookup"><span data-stu-id="527bd-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="527bd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="527bd-109">See Also</span></span>  
 [<span data-ttu-id="527bd-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="527bd-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="527bd-111">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="527bd-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="527bd-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="527bd-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
