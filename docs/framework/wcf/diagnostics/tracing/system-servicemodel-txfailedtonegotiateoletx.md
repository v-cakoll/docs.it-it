---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7f376244343a75c16d5d2355642d626f666e42bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx
È impossibile completare la negoziazione del protocollo OleTransactions per il contesto di coordinamento specificato.  
  
## <a name="description"></a>Descrizione  
 Viene tracciato quando una transazione in ingresso con informazioni OleTx non è in grado di utilizzare le informazioni OleTx allegate e utilizzerà pertanto WS-AT.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Indica un problema potenziale con la comunicazione RPC MSDTC tra i computer. Se il registro contiene molte di queste traccie, può verificarsi una drastica riduzione delle prestazioni.  Se non si desidera utilizzare OleTx, impostare `OleTxUpgradeEnabled` su 0 nella configurazione del Registro di sistema WS-AT.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
