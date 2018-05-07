---
title: Manomissioni
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: 519881a0813ac0b9f9218db42a42723a19a3089c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="tampering"></a>Manomissioni
*Manomissione* comporta la modifica di un messaggio o il recapito di un messaggio e utilizza il messaggio modificato a fini diversi da quelli per cui è stato creato.  
  
## <a name="do-not-disable-ws-addressing"></a>Non disattivare WS-Addressing  
 La specifica WS-Addressing fornisce intestazioni di indirizzo in ogni messaggio, consentendo a un destinatario di verificare il mittente del messaggio. È possibile disattivare questa funzionalità impostando la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Quando la modalità di sicurezza è impostata su Message, e se WS-Addressing è disattivato, l'autore di un attacco può prendere una richiesta da un client e inviarla a un altro servizio che non ha modo di rilevare se il messaggio proviene dal client originale. In effetti, il primo servizio può fingere di essere un client durante la comunicazione con il secondo servizio.  
  
 Per limitare questo problema, non impostare mai la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> ed evitare l'utilizzo di <xref:System.ServiceModel.Channels.MessageVersion>, ad esempio la proprietà statica <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>, che imposta la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Divulgazione di informazioni](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [Elevazione dei privilegi](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Negazione del servizio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 [Attacchi di tipo replay](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
