---
title: Migrazione delle applicazioni di .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: c0ce7c9badc8bad6eedc58827b6efe2595ab2cf8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592862"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrazione delle applicazioni di .NET Remoting a WCF
**Questo argomento è specifico di una tecnologia legacy mantenuta per una questione di compatibilità con le applicazioni esistenti di versioni precedenti e non è consigliato per il nuovo sviluppo. Le applicazioni distribuite devono ora essere sviluppate utilizzando WCF.**  
  
 Esistono due modi per sfruttare i vantaggi di WCF con le applicazioni .NET Remoting esistenti: integrazione e la migrazione. L'integrazione consente di disporre di .NET Remoting 2.0 e WCF in esecuzione side-by-side, consentendo di esporre simultaneamente gli stessi oggetti business su entrambe le tecnologie senza dover modificare il codice esistente .NET Remoting 2.0. L'integrazione richiede che sia in esecuzione in .NET Framework 2.0 o versione successiva. Se si desidera avvalersi delle funzionalità di WCF e non è necessario compatibility wire con sistemi .NET Remoting 2.0, è possibile eseguire la migrazione dell'intero servizio a WCF. Migrazione da .NET Remoting 2.0 a WCF richiede modifiche all'interfaccia dell'oggetto remoto e relative impostazioni di configurazione. Entrambi questi argomenti vengono analizzate [da .NET Remoting a Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dei concetti](../../../../docs/framework/wcf/conceptual-overview.md)
