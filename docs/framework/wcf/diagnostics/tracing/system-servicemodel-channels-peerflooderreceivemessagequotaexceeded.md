---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 0ca3d198ce225221348ac7b405ea91ad215cd298
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190899"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
La velocità di ricezione dei messaggi in ingresso è troppo elevata.  
  
## <a name="description"></a>Descrizione  
 Questa traccia si verifica quando si tenta di elaborare messaggi in ingresso. Non è possibile inoltrare un messaggio a un elemento adiacente poiché la quota impostata per tale elemento è stata superata. Questo problema si verifica quando un elemento adiacente che non risponde non riesce a cancellare un backlog di messaggi in sospeso per tale elemento adiacente.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Ridurre la velocità di invio dei messaggi all'interno della rete.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
