---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: bcac4683655476c6aa868232b0483336b815b6cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705982"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="a778d-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="a778d-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="a778d-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="a778d-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="a778d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a778d-104">Description</span></span>  
 <span data-ttu-id="a778d-105">Un messaggio è stato nuovamente chiuso.</span><span class="sxs-lookup"><span data-stu-id="a778d-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="a778d-106">Un messaggio deve essere chiuso solo una volta.</span><span class="sxs-lookup"><span data-stu-id="a778d-106">A message should be closed only once.</span></span> <span data-ttu-id="a778d-107">Se questa traccia viene emessa in codice di estensione utente, indica che tale codice sta chiudendo un messaggio che è già stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="a778d-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="a778d-108">Se viene emessa tramite codice del prodotto, indica che il codice di estensione utente potrebbe potenzialmente stare per chiudere un messaggio troppo presto.</span><span class="sxs-lookup"><span data-stu-id="a778d-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a778d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a778d-109">See also</span></span>
- [<span data-ttu-id="a778d-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="a778d-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="a778d-111">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="a778d-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a778d-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="a778d-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
