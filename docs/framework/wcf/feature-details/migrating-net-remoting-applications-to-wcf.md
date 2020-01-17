---
title: Migrazione delle applicazioni di .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 1d7edab8ad89660f3384d0ccf556384175c4d5db
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212156"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrazione delle applicazioni di .NET Remoting a WCF
**Questo argomento è specifico di una tecnologia legacy che viene mantenuta per la compatibilità con le applicazioni esistenti e non è consigliata per il nuovo sviluppo. Le applicazioni distribuite devono ora essere sviluppate tramite WCF.**  
  
 Esistono due modi per sfruttare i vantaggi offerti da WCF con le applicazioni .NET Remoting esistenti: integrazione e migrazione. L'integrazione consente di disporre di .NET Remoting 2,0 e WCF in esecuzione side-by-Side, consentendo di esporre contemporaneamente gli stessi oggetti business su entrambe le tecnologie senza dover modificare il codice .NET Remoting 2,0 esistente. Per l'integrazione è necessario che sia in esecuzione in .NET Framework 2,0 o versione successiva. Se si desidera sfruttare le funzionalità di WCF e non è necessaria la compatibilità con i dispositivi con i sistemi .NET Remoting 2,0, è possibile eseguire la migrazione dell'intero servizio a WCF. Per la migrazione da .NET Remoting 2,0 a WCF è necessario apportare modifiche all'interfaccia dell'oggetto remoto e alle relative impostazioni di configurazione. Entrambi gli argomenti sono trattati in [dalla comunicazione remota al Windows Communication Foundation](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80)).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dei concetti](../../../../docs/framework/wcf/conceptual-overview.md)
