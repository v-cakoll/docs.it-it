---
title: Migrazione delle applicazioni di .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: d12583904e4a025a8de1103f0fb48f4656d6855e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598775"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="d4cbb-102">Migrazione delle applicazioni di .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="d4cbb-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="d4cbb-103">**Questo argomento è specifico di una tecnologia legacy che viene mantenuta per la compatibilità con le applicazioni esistenti e non è consigliata per il nuovo sviluppo. Le applicazioni distribuite devono ora essere sviluppate tramite WCF.**</span><span class="sxs-lookup"><span data-stu-id="d4cbb-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="d4cbb-104">Esistono due modi per sfruttare i vantaggi offerti da WCF con le applicazioni .NET Remoting esistenti: integrazione e migrazione.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="d4cbb-105">L'integrazione consente di disporre di .NET Remoting 2,0 e WCF in esecuzione side-by-Side, consentendo di esporre contemporaneamente gli stessi oggetti business su entrambe le tecnologie senza dover modificare il codice .NET Remoting 2,0 esistente.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="d4cbb-106">Per l'integrazione è necessario che sia in esecuzione in .NET Framework 2,0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-106">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="d4cbb-107">Se si desidera sfruttare le funzionalità di WCF e non è necessaria la compatibilità con i dispositivi con i sistemi .NET Remoting 2,0, è possibile eseguire la migrazione dell'intero servizio a WCF.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="d4cbb-108">Per la migrazione da .NET Remoting 2,0 a WCF è necessario apportare modifiche all'interfaccia dell'oggetto remoto e alle relative impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="d4cbb-109">Entrambi gli argomenti sono trattati in [dalla comunicazione remota al Windows Communication Foundation](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="d4cbb-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cbb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4cbb-110">See also</span></span>

- [<span data-ttu-id="d4cbb-111">Panoramica concettuale</span><span class="sxs-lookup"><span data-stu-id="d4cbb-111">Conceptual Overview</span></span>](../conceptual-overview.md)
