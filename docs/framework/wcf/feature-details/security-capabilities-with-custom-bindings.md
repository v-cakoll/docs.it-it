---
title: Funzionalità di sicurezza con associazioni personalizzate
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 48d17543f2b133c74bcfa82cfe1a2a0de28b1d01
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595193"
---
# <a name="security-capabilities-with-custom-bindings"></a>Funzionalità di sicurezza con associazioni personalizzate
Per eseguire la maggior parte delle attività di sicurezza comuni, è possibile utilizzare una delle associazioni fornite dal sistema. Se è necessario un maggiore controllo, tuttavia, è possibile creare un'associazione personalizzata con un oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement>, come viene spiegato in questi argomenti. Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Modalità di autenticazione di SecurityBindingElement](securitybindingelement-authentication-modes.md)  
 Vengono descritte le modalità di autenticazione possibili con un'associazione personalizzata.  
  
 [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Vengono descritti i passaggi di base per la creazione di un'associazione personalizzata con un elemento di sicurezza.  
  
 [Procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificata](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Viene descritto come creare un elemento di sicurezza per una modalità di autenticazione specificata.  
  
 [Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Viene descritto come disattivare sessioni protette durante la creazione di un servizio federativo.  
  
 [Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi](how-to-enable-message-replay-detection.md)  
 Viene descritto come determinare il verificarsi di un attacco di tipo replay.  
  
 [Procedura: creare una credenziale di supporto](how-to-create-a-supporting-credential.md)  
 Viene descritto come fornire una credenziale di supporto a un servizio, se il servizio lo richiede.  
  
 [Procedura: impostare una conferma della firma](how-to-set-up-a-signature-confirmation.md)  
 Vengono descritti i passaggi necessari per confermare le firme durante la firma digitale dei messaggi.  
  
 [Procedura: impostare lo sfasamento massimo dei segnali di clock](how-to-set-a-max-clock-skew.md)  
 Viene descritto come impostare la differenza oraria massima consentita tra un servizio e un client.  
  
 [Procedura: disattivare la crittografia delle firme digitali](how-to-disable-encryption-of-digital-signatures.md)  
 Viene descritto come la disattivazione della crittografia di firme digitali possa influire positivamente sulle prestazioni.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Informazioni sul livello di protezione](../understanding-protection-level.md)  
  
 [Securing Services and Clients](securing-services-and-clients.md)  
  
## <a name="see-also"></a>Vedere anche

- [Associazioni e protezione](bindings-and-security.md)
- [Panoramica della sicurezza](security-overview.md)
- [Associazioni fornite dal sistema](../system-provided-bindings.md)
