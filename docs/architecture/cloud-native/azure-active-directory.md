---
title: Azure Active Directory
description: Architettura di app .NET cloud native per Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 207043507a9052c47683383a98cef6417a1a2740
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183693"
---
# <a name="azure-active-directory"></a>Azure Active Directory

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Microsoft Azure Active Directory (Azure AD) offre la gestione delle identità e degli accessi come servizio. I clienti lo usano per configurare e gestire gli utenti, le informazioni da archiviare, chi può accedere a tali informazioni, chi può gestirla e quali app possono accedervi. AAD è in grado di autenticare gli utenti per le applicazioni configurate per l'uso, offrendo un'esperienza di Single Sign-On (SSO). Può essere usato autonomamente o integrato con Windows AD in esecuzione in locale.

Azure AD viene creato per il cloud. Si tratta di una soluzione di identità nativa del cloud che usa una API Graph basata su REST e la sintassi OData per le query, a differenza di Windows AD, che usa LDAP. In locale Active Directory possibile sincronizzare gli attributi utente nel cloud usando i servizi di sincronizzazione delle identità, consentendo a tutte le autenticazioni di essere applicate nel cloud usando Azure AD. In alternativa, l'autenticazione può essere configurata tramite Connetti per passare nuovamente al Active Directory locale tramite ADFS per essere completata da Windows AD in locale.

Azure AD supporta le schermate di accesso personalizzate dell'azienda, l'autenticazione a più Factory e i proxy di applicazione basati sul cloud usati per fornire SSO per le applicazioni ospitate in locale. Offre diversi tipi di report di sicurezza e funzionalità di avviso.

## <a name="references"></a>Riferimenti

- [Piattaforma di identità Microsoft](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Precedente](authentication-authorization.md)
>[Successivo](identity-server.md)
