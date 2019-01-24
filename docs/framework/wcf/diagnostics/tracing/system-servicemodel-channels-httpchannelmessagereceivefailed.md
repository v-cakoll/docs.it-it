---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 22730ef8a0c0b4706f9e267fef251014a70a58fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720171"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
Impossibile ricevere un messaggio tramite canale HTTP.  
  
## <a name="description"></a>Descrizione  
 Questa traccia può essere emessa come avviso o come errore. In entrambi i casi, la traccia viene emessa quando non viene trovato un listener compatibile per una richiesta HTTP in entrata e tale richiesta viene eliminata. Questa situazione può verificarsi in quanto il verbo HTTP della richiesta non è stato riconosciuto da un listener HTTP o perchè nessun listener era in ascolto sull'indirizzo a cui era destinata la richiesta. La traccia viene emessa come avviso nel caso di un servizio indipendente e come errore nel caso di un servizio ospitato in IIS.  
  
## <a name="see-also"></a>Vedere anche
- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
