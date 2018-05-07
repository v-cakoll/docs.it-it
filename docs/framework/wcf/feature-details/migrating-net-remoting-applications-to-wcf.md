---
title: Migrazione delle applicazioni di .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 53f63352503a48ee849580e676b5fe98f3dcf2cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrazione delle applicazioni di .NET Remoting a WCF
**Questo argomento è specifico di una tecnologia legacy mantenuta per una questione di compatibilità con le applicazioni esistenti di versioni precedenti e non è consigliato per il nuovo sviluppo. Le applicazioni distribuite dovrebbero ora essere sviluppate tramite WCF.**  
  
 Esistono due modi per sfruttare i vantaggi di WCF con le applicazioni .NET Remoting esistenti: integrazione e la migrazione. Integrazione consente di avere .net Remoting 2.0 e WCF in esecuzione-by-side lato, consentendo di esporre gli stessi oggetti business su entrambe le tecnologie contemporaneamente senza dovere modificare il .net esistente .NET Remoting 2.0 codice. L'integrazione richiede che sia in esecuzione [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o versione successiva. Se si desidera avvalersi delle funzionalità di WCF e non richiedono la compatibilità di rete con sistemi .NET Remoting 2.0, è possibile eseguire la migrazione dell'intero servizio a WCF. Migrazione da .NET Remoting 2.0 a WCF richiede modifiche all'interfaccia dell'oggetto remoto e le impostazioni di configurazione. Entrambi gli argomenti vengono trattati nelle [dalla comunicazione remota di Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica dei concetti](../../../../docs/framework/wcf/conceptual-overview.md)
