---
title: Sessioni affidabili
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16480996b96145873b1d1f84d56af6d1aa863710
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-sessions"></a>Sessioni affidabili

In questa sezione descrive cosa un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è una sessione affidabile, cosa è utilizzata, come e quando utilizzarla, quali configurazioni di associazione supportano e indicatori di misura su procedure consigliate. Nella tabella seguente sono riepilogati i dettagli sui punti essenziali e gli argomenti correlati in questa sezione.

La sessione affidabile [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce featrues assicurandosi che i messaggi inviati tra endpoint vengono trasferiti su intermediari SOAP o trasporto e recapitati una sola volta e, facoltativamente, nello stesso ordine in cui sono stati inviati.

Per utilizzare una sessione affidabile con un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilizzare una delle associazioni fornite dal sistema in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che supporta una sessione affidabile per impostazione predefinita o come opzione, oppure creare un'associazione personalizzata che supporti la sessione.

## <a name="in-this-section"></a>In questa sezione

[Panoramica delle sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
Descrive le sessioni affidabili, quando utilizzarle, le diverse associazioni che supportano sessioni affidabili e come funzionano.

[Procedura: scambiare messaggi in una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
Descrive come creare una sessione affidabile su HTTP utilizzando un'associazione personalizzata specificata nella configurazione.

[Procedura: proteggere i messaggi in sessioni affidabili](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
Descrive come proteggere una sessione affidabile.

[Procedura: creare un'associazione di sessione affidabile personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
Descrive come creare una sessione affidabile su HTTPS.

[Procedure consigliate per le sessioni affidabili](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
Descrive alcune delle procedure consigliate associate all'utilizzo di una sessione affidabile.

## <a name="reference"></a>Riferimenti

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Vedere anche

[Code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
[Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
