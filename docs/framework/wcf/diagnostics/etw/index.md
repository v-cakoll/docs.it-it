---
title: Traccia analitica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: a0e3e3d27283e588b161e2209c5a682558d18f79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="analytic-tracing-with-etw"></a>Traccia analitica con ETW
Traccia analitica di Windows Communication Foundation (WCF) offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servizio. Gli eventi di traccia analitica di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] vengono generati in punti chiave dello stack [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] per consentire la risoluzione dei problemi relativi ai servizi di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in un ambiente di produzione. Traccia analitica per [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services ha un impatto minimo sulle prestazioni di un server di prodotto che ospita [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servizi in quanto tali eventi vengono generati in modo molto efficiente a una sessione Event Tracing for Windows (ETW).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica della traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Descrive la modalità in cui la traccia analitica di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] funziona in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Abilitazione dinamica della traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.  
  
 [Configurazione della traccia del flusso di messaggi](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Descrive la modalità di configurazione della traccia del flusso di messaggi.  
  
 [Riferimento dell'evento di traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [WCF Services e Event Tracing for Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Eventi di rilevamento in Traccia eventi per Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
