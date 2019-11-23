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
# <a name="azure-active-directory"></a><span data-ttu-id="c0e16-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c0e16-103">Azure Active Directory</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c0e16-104">Microsoft Azure Active Directory (Azure AD) offre la gestione delle identità e degli accessi come servizio.</span><span class="sxs-lookup"><span data-stu-id="c0e16-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="c0e16-105">I clienti lo usano per configurare e gestire gli utenti, le informazioni da archiviare, chi può accedere a tali informazioni, chi può gestirla e quali app possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="c0e16-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="c0e16-106">AAD è in grado di autenticare gli utenti per le applicazioni configurate per l'uso, offrendo un'esperienza di Single Sign-On (SSO).</span><span class="sxs-lookup"><span data-stu-id="c0e16-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="c0e16-107">Può essere usato autonomamente o integrato con Windows AD in esecuzione in locale.</span><span class="sxs-lookup"><span data-stu-id="c0e16-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="c0e16-108">Azure AD viene creato per il cloud.</span><span class="sxs-lookup"><span data-stu-id="c0e16-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="c0e16-109">Si tratta di una soluzione di identità nativa del cloud che usa una API Graph basata su REST e la sintassi OData per le query, a differenza di Windows AD, che usa LDAP.</span><span class="sxs-lookup"><span data-stu-id="c0e16-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="c0e16-110">In locale Active Directory possibile sincronizzare gli attributi utente nel cloud usando i servizi di sincronizzazione delle identità, consentendo a tutte le autenticazioni di essere applicate nel cloud usando Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0e16-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="c0e16-111">In alternativa, l'autenticazione può essere configurata tramite Connetti per passare nuovamente al Active Directory locale tramite ADFS per essere completata da Windows AD in locale.</span><span class="sxs-lookup"><span data-stu-id="c0e16-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="c0e16-112">Azure AD supporta le schermate di accesso personalizzate dell'azienda, l'autenticazione a più Factory e i proxy di applicazione basati sul cloud usati per fornire SSO per le applicazioni ospitate in locale.</span><span class="sxs-lookup"><span data-stu-id="c0e16-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="c0e16-113">Offre diversi tipi di report di sicurezza e funzionalità di avviso.</span><span class="sxs-lookup"><span data-stu-id="c0e16-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="c0e16-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c0e16-114">References</span></span>

- [<span data-ttu-id="c0e16-115">Piattaforma di identità Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0e16-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="c0e16-116">[Precedente](authentication-authorization.md)
>[Successivo](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="c0e16-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>
