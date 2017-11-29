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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dff06fbc52c0f4371abf0bcc465fd6a6d8be5859
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrazione delle applicazioni di .NET Remoting a WCF
**Questo argomento è specifico di una tecnologia legacy mantenuta per una questione di compatibilità con le applicazioni esistenti di versioni precedenti e non è consigliato per il nuovo sviluppo. Le applicazioni distribuite devono essere sviluppate ora utilizzando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**  
  
 Esistono due modalità per avvalersi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con applicazioni .NET Remoting esistenti: integrazione e migrazione. L'integrazione consente di avere .NET Remoting 2.0 e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in esecuzione affiancata, la qual cosa consente di esporre simultaneamente su entrambe le tecnologie gli stessi oggetti business senza dovere modificare il codice esistente .NET Remoting 2.0. L'integrazione richiede che sia in esecuzione [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o versione successiva. Se si desidera avvalersi delle funzionalità di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e non si ha necessità delle compatibilità di rete con sistemi .NET Remoting 2.0, è possibile eseguire la migrazione dell'intero servizio a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. La migrazione da .NET Remoting 2.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiede modifiche all'interfaccia dell'oggetto remoto e alle rispettive impostazioni di configurazione. Entrambi gli argomenti vengono trattati nelle [dalla comunicazione remota di Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica dei concetti](../../../../docs/framework/wcf/conceptual-overview.md)
