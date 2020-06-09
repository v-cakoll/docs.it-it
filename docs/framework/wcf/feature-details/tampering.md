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
# <a name="tampering"></a><span data-ttu-id="7e67f-102">Manomissione</span><span class="sxs-lookup"><span data-stu-id="7e67f-102">Tampering</span></span>
<span data-ttu-id="7e67f-103">La *manomissione* è l'azione di modifica di un messaggio, di recapito di un messaggio e di utilizzo del messaggio modificato per uno scopo diverso da quello previsto.</span><span class="sxs-lookup"><span data-stu-id="7e67f-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="7e67f-104">Non disattivare WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="7e67f-104">Do Not Disable WS-Addressing</span></span>  
 <span data-ttu-id="7e67f-105">La specifica WS-Addressing fornisce intestazioni di indirizzo in ogni messaggio, consentendo a un destinatario di verificare il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="7e67f-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="7e67f-106">È possibile disattivare questa funzionalità impostando la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e67f-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="7e67f-107">Quando la modalità di sicurezza è impostata su Message, e se WS-Addressing è disattivato, l'autore di un attacco può prendere una richiesta da un client e inviarla a un altro servizio che non ha modo di rilevare se il messaggio proviene dal client originale.</span><span class="sxs-lookup"><span data-stu-id="7e67f-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="7e67f-108">In effetti, il primo servizio può fingere di essere un client durante la comunicazione con il secondo servizio.</span><span class="sxs-lookup"><span data-stu-id="7e67f-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="7e67f-109">Per limitare questo problema, non impostare mai la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> ed evitare l'utilizzo di <xref:System.ServiceModel.Channels.MessageVersion>, ad esempio la proprietà statica <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>, che imposta la proprietà <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> su <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e67f-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e67f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e67f-110">See also</span></span>

- [<span data-ttu-id="7e67f-111">Security Considerations</span><span class="sxs-lookup"><span data-stu-id="7e67f-111">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="7e67f-112">Divulgazione di informazioni</span><span class="sxs-lookup"><span data-stu-id="7e67f-112">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="7e67f-113">Elevazione dei privilegi</span><span class="sxs-lookup"><span data-stu-id="7e67f-113">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="7e67f-114">Attacco Denial of Service</span><span class="sxs-lookup"><span data-stu-id="7e67f-114">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="7e67f-115">Scenari non supportati</span><span class="sxs-lookup"><span data-stu-id="7e67f-115">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
- [<span data-ttu-id="7e67f-116">Attacchi di tipo replay</span><span class="sxs-lookup"><span data-stu-id="7e67f-116">Replay Attacks</span></span>](replay-attacks.md)
