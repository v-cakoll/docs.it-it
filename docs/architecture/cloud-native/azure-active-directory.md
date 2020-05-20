---
title: Azure Active Directory
description: Architettura di app .NET cloud native per Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 03f5ea8e84bc3c4a2a88a63d4b109aabf0c64f36
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614279"
---
# <a name="azure-active-directory"></a>Azure Active Directory

Microsoft Azure Active Directory (Azure AD) offre la gestione delle identità e degli accessi come servizio. I clienti lo usano per configurare e gestire gli utenti, le informazioni da archiviare, chi può accedere a tali informazioni, chi può gestirla e quali app possono accedervi. AAD è in grado di autenticare gli utenti per le applicazioni configurate per l'uso, offrendo un'esperienza di Single Sign-On (SSO). Può essere usato autonomamente o integrato con Windows AD in esecuzione in locale.

Azure AD viene creato per il cloud. Si tratta di una soluzione di identità nativa del cloud che usa una API Graph basata su REST e la sintassi OData per le query, a differenza di Windows AD, che usa LDAP. In locale Active Directory possibile sincronizzare gli attributi utente nel cloud usando i servizi di sincronizzazione delle identità, consentendo a tutte le autenticazioni di essere applicate nel cloud usando Azure AD. In alternativa, l'autenticazione può essere configurata tramite Connetti per passare nuovamente al Active Directory locale tramite ADFS per essere completata da Windows AD in locale.

Azure AD supporta le schermate di accesso personalizzate dell'azienda, l'autenticazione a più Factory e i proxy di applicazione basati sul cloud usati per fornire SSO per le applicazioni ospitate in locale. Offre diversi tipi di report di sicurezza e funzionalità di avviso.

## <a name="references"></a>Riferimenti

- [Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Precedente](authentication-authorization.md) 
> [Avanti](identity-server.md)
