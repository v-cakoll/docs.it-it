---
title: Considerazioni sulla protezione per le sessioni protette
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
author: BrucePerlerMS
ms.openlocfilehash: 470ffc007ed73b28beba24bd0eb9c670dea9337d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47109381"
---
# <a name="security-considerations-for-secure-sessions"></a>Considerazioni sulla protezione per le sessioni protette
Si consiglia di considerare gli elementi seguenti che influiscono sulla sicurezza durante l'implementazione di sessioni protette. Per altre informazioni sulle considerazioni relative alla sicurezza, vedere [considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) e [procedure consigliate per la sicurezza](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sessioni protette e metadati  
 Quando viene stabilita una sessione protetta e il <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> è impostata su `false`, Windows Communication Foundation (WCF) invia un `mssp:MustNotSendCancel` asserzione come parte dei metadati nel documento Web Services Description Language (WSDL) per il endpoint del servizio. L'asserzione `mssp:MustNotSendCancel` informa i client che il servizio non risponde alle richieste di annullare la sessione protetta. Quando la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> è impostata su `true`, quindi WCF non generi un `mssp:MustNotSendCancel` asserzione nel documento WSDL. Si prevede che i client inviino una richiesta di annullamento al servizio quando la sessione protetta non è più necessaria. Quando un client viene generato usando il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), il codice client reagisce in modo appropriato alla presenza o assenza del `mssp:MustNotSendCancel` asserzione.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Conversazioni protette e token personalizzati  
 Si sono verificati problemi nella combinazione di token personalizzati e chiavi derivate a causa della modalità di definizione nella specifica WS-SecureConversation. La specifica afferma che `wsse:SecurityTokenReference` è un elemento facoltativo che fa riferimento al token derivato: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` questo elemento facoltativo consente di specificare token del contesto di sicurezza, token di sicurezza o chiave/segreto condiviso usato per la derivazione. Se non è specificata, si presume che il destinatario possa determinare la chiave condivisa dal contesto del messaggio. Se non è possibile determinare il contesto di un errore, ad esempio `wsc:UnknownDerivationSource` deve essere generato. "  
  
 Ciò significa che se si desidera derivare un token personalizzato, è necessario eseguire il wrapping del relativo tipo di clausola in un elemento `SecurityTokenReference`. Benché sia disponibile un'opzione per disattivare la derivazione, per impostazione predefinita le chiavi vengono derivate. Se non è possibile eseguire il wrapping della chiave, la serializzazione del token della chiave derivata viene completata correttamente, ma il tentativo di deserializzazione genera un'eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Disabilitare sessioni sicure in un'associazione WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [Considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Procedure consigliate per la sicurezza](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
