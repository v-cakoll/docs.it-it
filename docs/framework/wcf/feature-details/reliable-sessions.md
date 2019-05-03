---
title: Sessioni affidabili
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991159"
---
# <a name="reliable-sessions"></a>Sessioni affidabili

In questa sezione vengono descritte quali un Windows Communication Foundation (WCF) è una sessione affidabile, ciò che viene utilizzata, come e quando utilizzarla, quali configurazioni di binding supportano. vengono inoltre definite le procedure consigliate. Nella tabella seguente sono riepilogati i dettagli sui punti essenziali e gli argomenti correlati in questa sezione.

La sessione affidabile WCF fornisce funzionalità di garantire che i messaggi inviati tra gli endpoint vengono trasferiti su intermediari SOAP o di trasporto e recapitati solo una volta e, facoltativamente, nello stesso ordine in cui sono stati inviati.

Per usare una sessione affidabile con un'applicazione WCF, utilizzare una delle associazioni fornite dal sistema in WCF che supportano una sessione affidabile per impostazione predefinita o come opzione o creare un'associazione personalizzata che supporti la sessione.

## <a name="in-this-section"></a>In questa sezione

[Panoramica delle sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) descrive le sessioni affidabili, quando utilizzarle, le diverse associazioni che supportano sessioni affidabili, e sul relativo funzionamento.

[Procedura: Scambio dei messaggi all'interno di una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) viene descritto come creare una sessione affidabile su HTTP utilizzando un'associazione personalizzata specificata nella configurazione.

[Procedura: Proteggere i messaggi in sessioni affidabili](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) descrive come proteggere una sessione affidabile.

[Procedura: Creare un'associazione di sessione affidabile di personalizzata con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) viene descritto come creare una sessione affidabile su HTTPS.

[Procedure consigliate per le sessioni affidabili](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) descrive alcune delle procedure consigliate correlate all'utilizzo di una sessione affidabile.

## <a name="reference"></a>Riferimenti

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Vedere anche

- [Code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
