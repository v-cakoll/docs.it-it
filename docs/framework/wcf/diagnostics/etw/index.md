---
title: Traccia analitica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798084"
---
# <a name="analytic-tracing-with-etw"></a>Traccia analitica con ETW
La traccia analitica Windows Communication Foundation (WCF) offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un servizio WCF. Gli eventi di traccia analitica WCF vengono emessi in punti chiave dello stack WCF per consentire la risoluzione dei problemi relativi ai servizi WCF in un ambiente di produzione. La traccia analitica per i servizi WCF ha un effetto minimo sulle prestazioni di un server [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] di prodotto che ospita i servizi WCF poiché questi eventi vengono inviati in modo molto efficiente a una sessione di Event Tracing for Windows (ETW).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica della traccia analitica](analytic-tracing-overview.md)  
 Viene illustrato il funzionamento della traccia analitica di WCF in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Abilitazione dinamica della traccia analitica](dynamically-enabling-analytic-tracing.md)  
 Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.  
  
 [Configurazione della traccia del flusso di messaggi](configuring-message-flow-tracing.md)  
 Descrive la modalità di configurazione della traccia del flusso di messaggi.  
  
 [Riferimento dell'evento di traccia analitica](analytic-trace-event-reference.md)  
 Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- [WCF Services e Event Tracing for Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [Eventi di rilevamento in Traccia eventi per Windows](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
