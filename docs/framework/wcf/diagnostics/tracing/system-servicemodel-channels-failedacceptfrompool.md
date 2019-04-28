---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: de0bdd9e5ab922b09249bf550fde745042be8e58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666755"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a>System.ServiceModel.Channels.FailedAcceptFromPool
Tentativo di riutilizzare una connessione in pool non riuscito. Verrà effettuato un altro tentativo entro il periodo di timeout specificato.  
  
## <a name="description"></a>Descrizione  
 Questa traccia informativa indica che si è verificato un errore durante il tentativo di riutilizzare una connessione in pool. Ciò è dovuto al fatto che la connessione in pool non era compatibile o pronta oppure era ancora attiva. Verranno eseguiti ulteriori tentativi di riutilizzo della connessione in pool entro un determinato periodo di tempo. Nel caso in cui non verranno trovate connessioni utilizzabili, verrà creata una nuova connessione.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
