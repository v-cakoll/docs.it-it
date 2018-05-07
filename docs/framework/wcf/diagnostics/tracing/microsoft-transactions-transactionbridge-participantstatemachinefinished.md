---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 85b8cc4e5044cc7c87ea784e09c160cc527dddaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a>Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
La macchina a stati dell'integrazione di un partecipante è passata allo stato di operazione completata.  
  
## <a name="description"></a>Descrizione  
 Traccia eseguita quando l'elaborazione 2PC dell'integrazione di un partecipante subordinato è stata completata. Il risultato dell'integrazione può essere "Committed" o "Aborted", a indicare rispettivamente il commit o l'interruzione di una transazione. Questa traccia viene inoltre eseguita se un partecipante vota "ReadOnly" durante la fase di preparazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
