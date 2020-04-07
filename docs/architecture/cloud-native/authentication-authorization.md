---
title: Autenticazione e autorizzazione nelle app native cloud
description: Architettura delle app .NET native per Azure nel cloud Autenticazione e autorizzazione nelle app native cloud
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805551"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>Autenticazione e autorizzazione nelle app cloud native

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

*L'autenticazione* è il processo di determinazione dell'identità di un'entità di sicurezza. *L'autorizzazione* è l'atto di concedere a un'entità autenticata l'autorizzazione per eseguire un'azione o accedere a una risorsa. A volte l'autenticazione viene abbreviata e l'autorizzazione `AuthN` viene abbreviata in `AuthZ`. Le applicazioni native nel cloud devono fare affidamento su protocolli aperti basati su HTTP per autenticare le entità di sicurezza poiché sia i client che le applicazioni potrebbero essere in esecuzione in qualsiasi parte del mondo su qualsiasi piattaforma o dispositivo. L'unico fattore comune è HTTP.

Molte organizzazioni si basano ancora su servizi di autenticazione locale come Active Directory Federation Services (ADFS). Sebbene questo approccio abbia tradizionalmente servito bene le organizzazioni per le esigenze di autenticazione locali, le applicazioni native nel cloud traggono vantaggio dai sistemi progettati specificamente per il cloud. Un recente advisory del National Cyber Security Centre (NCSC) del Regno Unito nel Regno Unito afferma che "le organizzazioni che usano Azure AD come origine di autenticazione primaria abbasseranno effettivamente il rischio rispetto ad ADFS". Alcuni motivi descritti in [questa analisi](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) includono:

- Accesso al set completo di tecnologie microsoft per la protezione delle credenziali.
- La maggior parte delle organizzazioni si basa già su Azure AD in una certa misura.
- Il doppio hash degli hash NTLM garantisce che la compromissione non consenta le credenziali che funzionano in Active Directory locale.

## <a name="references"></a>Riferimenti

- [Nozioni di base sull'autenticazione](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [Token di accesso e attestazioniAccess tokens and claims](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [Potrebbe essere il momento di abbandonare i servizi di autenticazione locali](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[Successivo](identity.md)
>[precedente](azure-active-directory.md)
