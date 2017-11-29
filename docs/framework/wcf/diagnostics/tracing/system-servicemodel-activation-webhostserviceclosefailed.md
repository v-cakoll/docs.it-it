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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8550c30f74968d4f58d9a2fd1deac69bf9d3abe7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="91c06-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="91c06-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="91c06-103">Si verifica quando un servizio non può essere chiuso normalmente e viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="91c06-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="91c06-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91c06-104">Description</span></span>  
 <span data-ttu-id="91c06-105">Questo codice di errore viene visualizzato nel file di log.</span><span class="sxs-lookup"><span data-stu-id="91c06-105">This error code only appears in the log file.</span></span> <span data-ttu-id="91c06-106">In genere, indica un errore di programmazione, ad esempio quando si tenta di chiudere un servizio dopo che è già stato chiamato Abort.</span><span class="sxs-lookup"><span data-stu-id="91c06-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="91c06-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="91c06-107">Troubleshooting</span></span>  
 <span data-ttu-id="91c06-108">Verificare il codice sorgente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="91c06-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c06-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91c06-109">See Also</span></span>  
 [<span data-ttu-id="91c06-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="91c06-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="91c06-111">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="91c06-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="91c06-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="91c06-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
