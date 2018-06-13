---
title: Traccia analitica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 210418b8a8765a1fc59658e9df57c92ce087c95f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809264"
---
# <a name="analytic-tracing-with-etw"></a>Traccia analitica con ETW
Traccia analitica di Windows Communication Foundation (WCF) offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un servizio WCF. Gli eventi di traccia analitica WCF vengono generati in punti chiave nello stack di WCF per consentire la risoluzione dei problemi dei servizi WCF in un ambiente di produzione. Traccia analitica per i servizi WCF ha un impatto minimo sulle prestazioni di un server di prodotto che ospita [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] servizi WCF, poiché questi eventi vengono generati in modo molto efficiente in una sessione di traccia eventi per Windows (ETW).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica della traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Illustra il funzionamento di traccia analitica WCF in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Abilitazione dinamica della traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.  
  
 [Configurazione della traccia del flusso di messaggi](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Descrive la modalità di configurazione della traccia del flusso di messaggi.  
  
 [Riferimento dell'evento di traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [WCF Services e Event Tracing for Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Eventi di rilevamento in Traccia eventi per Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
