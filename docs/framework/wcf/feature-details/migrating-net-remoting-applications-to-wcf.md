---
title: Migrazione delle applicazioni di .NET Remoting a WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 240901f4fa04a2468d5964821680506ea117bf7f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="32e66-102">Migrazione delle applicazioni di .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="32e66-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="32e66-103">**Questo argomento è specifico di una tecnologia legacy mantenuta per una questione di compatibilità con le applicazioni esistenti di versioni precedenti e non è consigliato per il nuovo sviluppo. Le applicazioni distribuite devono essere sviluppate ora utilizzando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span><span class="sxs-lookup"><span data-stu-id="32e66-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span></span>  
  
 <span data-ttu-id="32e66-104">Esistono due modalità per avvalersi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con applicazioni .NET Remoting esistenti: integrazione e migrazione.</span><span class="sxs-lookup"><span data-stu-id="32e66-104">There are two ways to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="32e66-105">L'integrazione consente di avere .NET Remoting 2.0 e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in esecuzione affiancata, la qual cosa consente di esporre simultaneamente su entrambe le tecnologie gli stessi oggetti business senza dovere modificare il codice esistente .NET Remoting 2.0.</span><span class="sxs-lookup"><span data-stu-id="32e66-105">Integration allows you to have .Net Remoting 2.0 and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .Net Remoting 2.0 code.</span></span> <span data-ttu-id="32e66-106">L'integrazione richiede che sia in esecuzione [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="32e66-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="32e66-107">Se si desidera avvalersi delle funzionalità di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e non si ha necessità delle compatibilità di rete con sistemi .NET Remoting 2.0, è possibile eseguire la migrazione dell'intero servizio a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32e66-107">If you want to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="32e66-108">La migrazione da .NET Remoting 2.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiede modifiche all'interfaccia dell'oggetto remoto e alle rispettive impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="32e66-108">Migration from .NET Remoting 2.0 to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="32e66-109">Entrambi gli argomenti vengono trattati nelle [dalla comunicazione remota di Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="32e66-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e66-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32e66-110">See Also</span></span>  
 [<span data-ttu-id="32e66-111">Panoramica dei concetti</span><span class="sxs-lookup"><span data-stu-id="32e66-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
