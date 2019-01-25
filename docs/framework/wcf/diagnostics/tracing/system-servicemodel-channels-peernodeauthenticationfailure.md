---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 1ed037c548f1d833f2a20118ee1e017cd19e3391
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628240"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure
L’handshake di sicurezza con un router adiacente potenziale non è riuscito.  
  
## <a name="description"></a>Descrizione  
 Questa traccia si verifica quando si tenta di stabilire una connessione protetta con un router adiacente. Tale situazione può verificarsi a causa di credenziali insufficienti o incorrette.  
  
 PeerChannel riconosce un solo tipo di token per identificazione sicura, i certificati X.509 che offrono un modello sicuro di identità basato sul tipo di autenticazione e di autorizzazione che può essere implementato. PeerChannel fornisce inoltre il supporto per applicazioni semplici tramite l'utilizzo di password. Le password possono essere utilizzate solo per consentire l'accesso alla sessione, non per eseguire l'autenticazione dei messaggi. Ciò è dovuto al fatto che è difficile e inappropriato utilizzare per l'autenticazione dell'origine un token simmetrico condiviso da un gruppo di peer.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Assicurarsi che tutti i router adiacenti abbiano le credenziali di sicurezza appropriate.  
  
## <a name="see-also"></a>Vedere anche
- [Sicurezza del canale peer](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)
- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso delle tracce per risolvere i problemi di un'applicazione](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
