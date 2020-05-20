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
# <a name="azure-active-directory"></a><span data-ttu-id="58b4e-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="58b4e-103">Azure Active Directory</span></span>

<span data-ttu-id="58b4e-104">Microsoft Azure Active Directory (Azure AD) offre la gestione delle identità e degli accessi come servizio.</span><span class="sxs-lookup"><span data-stu-id="58b4e-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="58b4e-105">I clienti lo usano per configurare e gestire gli utenti, le informazioni da archiviare, chi può accedere a tali informazioni, chi può gestirla e quali app possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="58b4e-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="58b4e-106">AAD è in grado di autenticare gli utenti per le applicazioni configurate per l'uso, offrendo un'esperienza di Single Sign-On (SSO).</span><span class="sxs-lookup"><span data-stu-id="58b4e-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="58b4e-107">Può essere usato autonomamente o integrato con Windows AD in esecuzione in locale.</span><span class="sxs-lookup"><span data-stu-id="58b4e-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="58b4e-108">Azure AD viene creato per il cloud.</span><span class="sxs-lookup"><span data-stu-id="58b4e-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="58b4e-109">Si tratta di una soluzione di identità nativa del cloud che usa una API Graph basata su REST e la sintassi OData per le query, a differenza di Windows AD, che usa LDAP.</span><span class="sxs-lookup"><span data-stu-id="58b4e-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="58b4e-110">In locale Active Directory possibile sincronizzare gli attributi utente nel cloud usando i servizi di sincronizzazione delle identità, consentendo a tutte le autenticazioni di essere applicate nel cloud usando Azure AD.</span><span class="sxs-lookup"><span data-stu-id="58b4e-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="58b4e-111">In alternativa, l'autenticazione può essere configurata tramite Connetti per passare nuovamente al Active Directory locale tramite ADFS per essere completata da Windows AD in locale.</span><span class="sxs-lookup"><span data-stu-id="58b4e-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="58b4e-112">Azure AD supporta le schermate di accesso personalizzate dell'azienda, l'autenticazione a più Factory e i proxy di applicazione basati sul cloud usati per fornire SSO per le applicazioni ospitate in locale.</span><span class="sxs-lookup"><span data-stu-id="58b4e-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="58b4e-113">Offre diversi tipi di report di sicurezza e funzionalità di avviso.</span><span class="sxs-lookup"><span data-stu-id="58b4e-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="58b4e-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="58b4e-114">References</span></span>

- [<span data-ttu-id="58b4e-115">Microsoft Identity Platform</span><span class="sxs-lookup"><span data-stu-id="58b4e-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="58b4e-116">[Precedente](authentication-authorization.md) 
> [Avanti](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="58b4e-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>
