---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: cb7019f1e4b47bde7c98b0109afa7b0125b7ef63
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577305"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure
L’handshake di sicurezza con un router adiacente potenziale non è riuscito.  
  
## <a name="description"></a>Descrizione  
 Questa traccia si verifica quando si tenta di stabilire una connessione protetta con un router adiacente. Tale situazione può verificarsi a causa di credenziali insufficienti o incorrette.  
  
 PeerChannel riconosce un solo tipo di token per identificazione sicura, i certificati X.509 che offrono un modello sicuro di identità basato sul tipo di autenticazione e di autorizzazione che può essere implementato. PeerChannel fornisce inoltre il supporto per applicazioni semplici tramite l'utilizzo di password. Le password possono essere utilizzate solo per consentire l'accesso alla sessione, non per eseguire l'autenticazione dei messaggi. Ciò è dovuto al fatto che è difficile e inappropriato utilizzare per l'autenticazione dell'origine un token simmetrico condiviso da un gruppo di peer.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Assicurarsi che tutti i router adiacenti abbiano le credenziali di sicurezza appropriate.  
  
## <a name="see-also"></a>Vedere anche

- [Protezione del canale peer](../../feature-details/peer-channel-security.md)
- [Traccia](index.md)
- [Utilizzo delle tracce per risolvere i problemi di un'applicazione](using-tracing-to-troubleshoot-your-application.md)
- [Amministrazione e diagnostica](../index.md)
