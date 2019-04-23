---
title: Migrazione delle applicazioni di .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 4040fb0ac223f91705a49b733f6a1f42d144068e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091121"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="f0b6e-102">Migrazione delle applicazioni di .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="f0b6e-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="f0b6e-103">**Questo argomento è specifico di una tecnologia legacy mantenuta per una questione di compatibilità con le applicazioni esistenti di versioni precedenti e non è consigliato per il nuovo sviluppo. Le applicazioni distribuite devono ora essere sviluppate utilizzando WCF.**</span><span class="sxs-lookup"><span data-stu-id="f0b6e-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="f0b6e-104">Esistono due modi per sfruttare i vantaggi di WCF con le applicazioni .NET Remoting esistenti: integrazione e la migrazione.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="f0b6e-105">L'integrazione consente di disporre di .NET Remoting 2.0 e WCF in esecuzione side-by-side, consentendo di esporre simultaneamente gli stessi oggetti business su entrambe le tecnologie senza dover modificare il codice esistente .NET Remoting 2.0.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="f0b6e-106">L'integrazione richiede che sia in esecuzione [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="f0b6e-107">Se si desidera avvalersi delle funzionalità di WCF e non è necessario compatibility wire con sistemi .NET Remoting 2.0, è possibile eseguire la migrazione dell'intero servizio a WCF.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="f0b6e-108">Migrazione da .NET Remoting 2.0 a WCF richiede modifiche all'interfaccia dell'oggetto remoto e relative impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="f0b6e-109">Entrambi questi argomenti vengono analizzate [da .NET Remoting a Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="f0b6e-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b6e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0b6e-110">See also</span></span>

- [<span data-ttu-id="f0b6e-111">Panoramica dei concetti</span><span class="sxs-lookup"><span data-stu-id="f0b6e-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
