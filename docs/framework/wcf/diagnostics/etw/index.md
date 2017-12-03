---
title: Traccia analitica con ETW
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42683acdfe2e63d59a13496b210f83fb97c02de7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="analytic-tracing-with-etw"></a>Traccia analitica con ETW
La traccia analitica di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un servizio di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Gli eventi di traccia analitica di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] vengono generati in punti chiave dello stack [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] per consentire la risoluzione dei problemi relativi ai servizi di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in un ambiente di produzione. Traccia analitica per [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services ha un impatto minimo sulle prestazioni di un server di prodotto che ospita [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servizi in quanto tali eventi vengono generati in modo molto efficiente a una sessione Event Tracing for Windows (ETW).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica della traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Descrive la modalità in cui la traccia analitica di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] funziona in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Abilitazione dinamica della traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.  
  
 [Configurazione di traccia del flusso di messaggi](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Descrive la modalità di configurazione della traccia del flusso di messaggi.  
  
 [Riferimento all'evento di traccia analitica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [WCF Services and Event Tracing for Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Eventi di rilevamento in Event Tracing in Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
