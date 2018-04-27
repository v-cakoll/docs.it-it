---
title: Esempio di CompensableActivity
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba81d0eb32305e8ea099a291bef612639915292f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="compensable-activity-sample"></a>Esempio di CompensableActivity
In questo esempio viene illustrato come usare l'attività `CompensableActivity` per definire il lavoro da eseguire per un'azione specificata durante la normale esecuzione e il lavoro che è necessario eseguire per compensare tale azione, se necessario in un secondo tempo.  La prima parte dell'esempio viene illustrato come unità di lavoro compensabile possono essere definite in Windows Workflow Foundation (WF) utilizzando un `CompensableActivity` attività e come vengono eseguiti in un'esecuzione riuscita.  Nella seconda parte dell'esempio viene illustrato in che modo le stesse unità di lavoro compensabile eseguono automaticamente la compensazione quando viene rilevato un evento imprevisto e l'istanza del flusso di lavoro viene annullata.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Tramite Visual Studio 2010 aprire CompensableActivity.sln.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione,  
  
3.  Eseguire l'applicazione premendo F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`