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
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrazione delle applicazioni di .NET Remoting a WCF
**Questo argomento è specifico di una tecnologia legacy che viene mantenuta per la compatibilità con le applicazioni esistenti e non è consigliata per il nuovo sviluppo. Le applicazioni distribuite devono ora essere sviluppate tramite WCF.**  
  
 Esistono due modi per sfruttare i vantaggi offerti da WCF con le applicazioni .NET Remoting esistenti: integrazione e migrazione. L'integrazione consente di disporre di .NET Remoting 2,0 e WCF in esecuzione side-by-Side, consentendo di esporre contemporaneamente gli stessi oggetti business su entrambe le tecnologie senza dover modificare il codice .NET Remoting 2,0 esistente. Per l'integrazione è necessario che sia in esecuzione in .NET Framework 2,0 o versione successiva. Se si desidera sfruttare le funzionalità di WCF e non è necessaria la compatibilità con i dispositivi con i sistemi .NET Remoting 2,0, è possibile eseguire la migrazione dell'intero servizio a WCF. Per la migrazione da .NET Remoting 2,0 a WCF è necessario apportare modifiche all'interfaccia dell'oggetto remoto e alle relative impostazioni di configurazione. Entrambi gli argomenti sono trattati in [dalla comunicazione remota al Windows Communication Foundation](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80)).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica concettuale](../conceptual-overview.md)
