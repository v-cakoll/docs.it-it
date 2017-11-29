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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3963fe28ccaf55b3946254e395b770619c8f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="63c43-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="63c43-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="63c43-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="63c43-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="63c43-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63c43-104">Description</span></span>  
 <span data-ttu-id="63c43-105">Un messaggio è stato nuovamente chiuso.</span><span class="sxs-lookup"><span data-stu-id="63c43-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="63c43-106">Un messaggio deve essere chiuso solo una volta.</span><span class="sxs-lookup"><span data-stu-id="63c43-106">A message should be closed only once.</span></span> <span data-ttu-id="63c43-107">Se questa traccia viene emessa in codice di estensione utente, indica che tale codice sta chiudendo un messaggio che è già stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="63c43-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="63c43-108">Se viene emessa tramite codice del prodotto, indica che il codice di estensione utente potrebbe potenzialmente stare per chiudere un messaggio troppo presto.</span><span class="sxs-lookup"><span data-stu-id="63c43-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c43-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63c43-109">See Also</span></span>  
 [<span data-ttu-id="63c43-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="63c43-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="63c43-111">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="63c43-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="63c43-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="63c43-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
