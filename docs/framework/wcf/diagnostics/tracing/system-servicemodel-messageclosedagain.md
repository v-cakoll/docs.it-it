---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: d341953b8e12b14e6a3fe8a477c16a1b3a4454ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580437"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="5f717-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="5f717-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="5f717-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="5f717-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="5f717-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f717-104">Description</span></span>  
 <span data-ttu-id="5f717-105">Un messaggio è stato nuovamente chiuso.</span><span class="sxs-lookup"><span data-stu-id="5f717-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="5f717-106">Un messaggio deve essere chiuso solo una volta.</span><span class="sxs-lookup"><span data-stu-id="5f717-106">A message should be closed only once.</span></span> <span data-ttu-id="5f717-107">Se questa traccia viene emessa in codice di estensione utente, indica che tale codice sta chiudendo un messaggio che è già stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="5f717-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="5f717-108">Se viene emessa tramite codice del prodotto, indica che il codice di estensione utente potrebbe potenzialmente stare per chiudere un messaggio troppo presto.</span><span class="sxs-lookup"><span data-stu-id="5f717-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f717-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f717-109">See also</span></span>

- [<span data-ttu-id="5f717-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="5f717-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="5f717-111">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="5f717-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5f717-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="5f717-112">Administration and Diagnostics</span></span>](../index.md)
