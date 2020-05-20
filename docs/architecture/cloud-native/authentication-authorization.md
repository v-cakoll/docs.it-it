---
title: Autenticazione e autorizzazione in app native del cloud
description: Architettura di app .NET cloud native per Azure | Autenticazione e autorizzazione nelle app cloud native
ms.date: 05/13/2020
ms.openlocfilehash: e5254560ac82662e5e3ea6a25997516cd2b478b0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614305"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>Autenticazione e autorizzazione nelle app cloud native

L' *autenticazione* è il processo di determinazione dell'identità di un'entità di sicurezza. L' *autorizzazione* è l'atto di concedere a un'entità autenticata un'autorizzazione per eseguire un'azione o accedere a una risorsa. A volte l'autenticazione viene abbreviata `AuthN` e l'autorizzazione viene abbreviata in `AuthZ` . Le applicazioni native del cloud devono basarsi su protocolli basati su HTTP aperti per autenticare le entità di sicurezza, poiché sia i client che le applicazioni possono essere eseguiti ovunque nel mondo su qualsiasi piattaforma o dispositivo. L'unico fattore comune è HTTP.

Molte organizzazioni si basano ancora sui servizi di autenticazione locali come Active Directory Federation Services (ADFS). Sebbene questo approccio abbia tradizionalmente servito le organizzazioni per le esigenze di autenticazione locali, le applicazioni native del cloud traggono vantaggio dai sistemi progettati specificamente per il cloud. Una recente consulenza NCSC (National Cyber Security Centre) 2019 del Regno Unito afferma che "le organizzazioni che utilizzano Azure AD come origine di autenticazione primaria diminuiranno effettivamente i rischi rispetto ad ADFS". Di seguito sono riportati alcuni dei motivi descritti in [questa analisi](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) :

- Accesso al set completo di tecnologie di protezione delle credenziali di Microsoft.
- La maggior parte delle organizzazioni si trova già in una certa misura Azure AD.
- Il doppio hash degli hash NTLM garantisce che il compromesso non consenta le credenziali che funzionano in Active Directory locali.

## <a name="references"></a>Riferimenti

- [Nozioni di base sull'autenticazione](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [Attestazioni e token di accesso](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [Potrebbe essere il momento di abbandonare i servizi di autenticazione locali](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[Precedente](identity.md) 
> [Avanti](azure-active-directory.md)
