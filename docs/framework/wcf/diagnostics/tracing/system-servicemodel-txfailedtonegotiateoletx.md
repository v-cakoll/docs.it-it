---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61360eff4f2c403eea98bbc0a2eae36e516b3d7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx
È impossibile completare la negoziazione del protocollo OleTransactions per il contesto di coordinamento specificato.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato quando una transazione in ingresso con informazioni OleTx non è in grado di utilizzare le informazioni OleTx allegate e utilizzerà pertanto WS-AT.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Indica un problema potenziale con la comunicazione RPC MSDTC tra i computer. Se il registro contiene molte di queste traccie, può verificarsi una drastica riduzione delle prestazioni.  Se non si desidera utilizzare OleTx, impostare `OleTxUpgradeEnabled` su 0 nella configurazione del Registro di sistema WS-AT.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Utilizzo delle tracce per risolvere i problemi dell'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
