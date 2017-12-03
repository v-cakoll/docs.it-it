---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1761ef66bf2aedf2d4382558ba70bf1956af0f3e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="d9a3c-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="d9a3c-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="d9a3c-103">Si verifica quando un servizio non può essere chiuso normalmente e viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="d9a3c-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d9a3c-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9a3c-104">Description</span></span>  
 <span data-ttu-id="d9a3c-105">Questo codice di errore viene visualizzato nel file di log.</span><span class="sxs-lookup"><span data-stu-id="d9a3c-105">This error code only appears in the log file.</span></span> <span data-ttu-id="d9a3c-106">In genere, indica un errore di programmazione, ad esempio quando si tenta di chiudere un servizio dopo che è già stato chiamato Abort.</span><span class="sxs-lookup"><span data-stu-id="d9a3c-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d9a3c-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d9a3c-107">Troubleshooting</span></span>  
 <span data-ttu-id="d9a3c-108">Verificare il codice sorgente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d9a3c-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a3c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9a3c-109">See Also</span></span>  
 [<span data-ttu-id="d9a3c-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="d9a3c-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d9a3c-111">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d9a3c-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d9a3c-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="d9a3c-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
