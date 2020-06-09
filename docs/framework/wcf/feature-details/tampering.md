---
title: Manomissione
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: e618ab369a46d403aa8db26c4b472e2be3634785
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600711"
---
# <a name="tampering"></a>Manomissione
La *manomissione* è l'azione di modifica di un messaggio, di recapito di un messaggio e di utilizzo del messaggio modificato per uno scopo diverso da quello previsto.  
  
## <a name="do-not-disable-ws-addressing"></a>Non disattivare WS-Addressing  
 La specifica WS-Addressing fornisce intestazioni di indirizzo in ogni messaggio, consentendo a un destinatario di verificare il mittente del messaggio. È possibile disattivare questa funzionalità impostando la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Quando la modalità di sicurezza è impostata su Message, e se WS-Addressing è disattivato, l'autore di un attacco può prendere una richiesta da un client e inviarla a un altro servizio che non ha modo di rilevare se il messaggio proviene dal client originale. In effetti, il primo servizio può fingere di essere un client durante la comunicazione con il secondo servizio.  
  
 Per limitare questo problema, non impostare mai la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> ed evitare l'utilizzo di <xref:System.ServiceModel.Channels.MessageVersion>, ad esempio la proprietà statica <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>, che imposta la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Security Considerations](security-considerations-in-wcf.md)
- [Divulgazione di informazioni](information-disclosure.md)
- [Elevazione dei privilegi](elevation-of-privilege.md)
- [Attacco Denial of Service](denial-of-service.md)
- [Scenari non supportati](unsupported-scenarios.md)
- [Attacchi di tipo replay](replay-attacks.md)
