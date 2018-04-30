---
title: Considerazioni sulla protezione per le sessioni protette
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 4d1e5082ace452eabddd91a45a20c6d6363e118b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="security-considerations-for-secure-sessions"></a>Considerazioni sulla protezione per le sessioni protette
Si consiglia di considerare gli elementi seguenti che influiscono sulla sicurezza durante l'implementazione di sessioni protette. Per ulteriori informazioni sulle considerazioni relative alla sicurezza, vedere [considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) e [procedure consigliate per la sicurezza](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sessioni protette e metadati  
 Quando si stabilisce una sessione sicura e si imposta la proprietà <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> su `false`, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] invia un'asserzione `mssp:MustNotSendCancel` come parte dei metadati nel documento WSDL (Web Services Description Language) relativo all'endpoint del servizio. L'asserzione `mssp:MustNotSendCancel` informa i client che il servizio non risponde alle richieste di annullare la sessione protetta. Quando la proprietà <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> è impostata su `true`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera l'asserzione `mssp:MustNotSendCancel` nel documento WSDL. Si prevede che i client inviino una richiesta di annullamento al servizio quando la sessione protetta non è più necessaria. Quando un client viene generato usando il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), il codice client reagisce nel modo appropriato alla presenza o assenza del `mssp:MustNotSendCancel` asserzione.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Conversazioni protette e token personalizzati  
 Si sono verificati problemi nella combinazione di token personalizzati e chiavi derivate a causa della modalità di definizione nella specifica WS-SecureConversation. La specifica afferma che `wsse:SecurityTokenReference` è un elemento facoltativo che fa riferimento al token derivato: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` questo elemento facoltativo viene utilizzato per specificare token del contesto di sicurezza, token di sicurezza o chiave/segreto condiviso usato per la derivazione. Se non è specificata, si presume che il destinatario possa determinare la chiave condivisa dal contesto del messaggio. Se non è possibile determinare il contesto, quindi un errore, ad esempio `wsc:UnknownDerivationSource` deve essere generato. "  
  
 Ciò significa che se si desidera derivare un token personalizzato, è necessario eseguire il wrapping del relativo tipo di clausola in un elemento `SecurityTokenReference`. Benché sia disponibile un'opzione per disattivare la derivazione, per impostazione predefinita le chiavi vengono derivate. Se non è possibile eseguire il wrapping della chiave, la serializzazione del token della chiave derivata viene completata correttamente, ma il tentativo di deserializzazione genera un'eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Disabilitare sessioni sicure in un'associazione WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [Considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Procedure consigliate per la sicurezza](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
