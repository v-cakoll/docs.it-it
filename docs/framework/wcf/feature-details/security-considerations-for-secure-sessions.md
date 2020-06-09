---
title: Considerazioni sulla protezione per le sessioni protette
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
ms.openlocfilehash: 587897cc296523e0bfd5a4d4fa50b1e145cb69fb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601049"
---
# <a name="security-considerations-for-secure-sessions"></a>Considerazioni sulla protezione per le sessioni protette
Si consiglia di considerare gli elementi seguenti che influiscono sulla sicurezza durante l'implementazione di sessioni protette. Per ulteriori informazioni sulle considerazioni relative alla sicurezza, vedere [considerazioni sulla sicurezza](security-considerations-in-wcf.md) e [procedure consigliate per la sicurezza](best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sessioni protette e metadati  
 Quando viene stabilita una sessione protetta e la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> proprietà è impostata su `false` , Windows Communication Foundation (WCF) Invia un' `mssp:MustNotSendCancel` asserzione come parte dei metadati nel documento di Web Services Description Language (WSDL) per l'endpoint del servizio. L'asserzione `mssp:MustNotSendCancel` informa i client che il servizio non risponde alle richieste di annullare la sessione protetta. Quando la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> proprietà è impostata su `true` , WCF non emette un' `mssp:MustNotSendCancel` asserzione nel documento WSDL. Si prevede che i client inviino una richiesta di annullamento al servizio quando la sessione protetta non è più necessaria. Quando un client viene generato utilizzando lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md), il codice client reagisce in modo appropriato alla presenza o all'assenza dell' `mssp:MustNotSendCancel` asserzione.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Conversazioni protette e token personalizzati  
 Si sono verificati problemi nella combinazione di token personalizzati e chiavi derivate a causa della modalità di definizione nella specifica WS-SecureConversation. La specifica indica che `wsse:SecurityTokenReference` è un elemento facoltativo che fa riferimento al token derivato: " `/wsc:DerivedKeyToken/wsse:SecurityTokenReference` questo elemento facoltativo viene usato per specificare il token del contesto di sicurezza, il token di sicurezza o la chiave o il segreto condiviso usato per la derivazione. Se non è specificata, si presume che il destinatario possa determinare la chiave condivisa dal contesto del messaggio. Se non è possibile determinare il contesto, è necessario generare un errore, ad esempio `wsc:UnknownDerivationSource` ".  
  
 Ciò significa che se si desidera derivare un token personalizzato, è necessario eseguire il wrapping del relativo tipo di clausola in un elemento `SecurityTokenReference`. Benché sia disponibile un'opzione per disattivare la derivazione, per impostazione predefinita le chiavi vengono derivate. Se non è possibile eseguire il wrapping della chiave, la serializzazione del token della chiave derivata viene completata correttamente, ma il tentativo di deserializzazione genera un'eccezione.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Security Considerations](security-considerations-in-wcf.md)
- [Procedure consigliate per la sicurezza](best-practices-for-security-in-wcf.md)
