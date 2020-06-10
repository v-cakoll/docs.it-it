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
ms.openlocfilehash: 910ad952192243c6aa8a79417ad711d8c2a4ba2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590540"
---
# <a name="reliable-sessions"></a>Sessioni affidabili

In questa sezione viene descritta la modalità di utilizzo di una sessione affidabile Windows Communication Foundation (WCF), come e quando utilizzarne una, le configurazioni di binding che la supportano e i puntatori alle procedure consigliate. Nella tabella seguente sono riepilogati i dettagli sui punti essenziali e gli argomenti correlati in questa sezione.

La sessione affidabile WCF fornisce funzionalità che assicurano che i messaggi inviati tra gli endpoint vengano trasferiti tra gli intermediari SOAP o di trasporto e vengano recapitati solo una volta e, facoltativamente, nello stesso ordine in cui sono stati inviati.

Per utilizzare una sessione affidabile con un'applicazione WCF, utilizzare una delle associazioni fornite dal sistema in WCF che supportano una sessione affidabile per impostazione predefinita o come opzione oppure creare un'associazione personalizzata che supporti la sessione.

## <a name="in-this-section"></a>Contenuto della sezione

[Panoramica delle sessioni affidabili](reliable-sessions-overview.md) Descrive le sessioni affidabili, quando utilizzarle, le diverse associazioni che supportano sessioni affidabili e il loro funzionamento.

[Procedura: scambiare messaggi in una sessione affidabile](how-to-exchange-messages-within-a-reliable-session.md) Viene descritto come creare una sessione affidabile su HTTP utilizzando un'associazione personalizzata specificata nella configurazione.

[Procedura: proteggere i messaggi all'interno di sessioni affidabili](how-to-secure-messages-within-reliable-sessions.md) Viene descritto come proteggere una sessione affidabile.

[Procedura: creare un'associazione di sessione affidabile personalizzata con https](how-to-create-a-custom-reliable-session-binding-with-https.md) Viene descritto come creare una sessione affidabile su HTTPS.

[Procedure consigliate per le sessioni affidabili](best-practices-for-reliable-sessions.md) Vengono descritte alcune delle procedure consigliate associate all'utilizzo di una sessione affidabile.

## <a name="reference"></a>Informazioni di riferimento

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Vedere anche

- [Code e sessioni affidabili](queues-and-reliable-sessions.md)
- [Sessioni, istanze e concorrenza](sessions-instancing-and-concurrency.md)
