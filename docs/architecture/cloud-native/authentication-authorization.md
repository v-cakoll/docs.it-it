---
title: Autenticazione e autorizzazione in app native del cloud
description: Architettura di app .NET cloud native per Azure | Autenticazione e autorizzazione nelle app cloud native
ms.date: 06/30/2019
ms.openlocfilehash: a397175e98c2e8103d2a8c372c81fcca65f19b11
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183728"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="32c23-103">Autenticazione e autorizzazione nelle app cloud native</span><span class="sxs-lookup"><span data-stu-id="32c23-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="32c23-104">L' *autenticazione* è il processo di determinazione dell'identità di un'entità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="32c23-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="32c23-105">L' *autorizzazione* è l'atto di concedere a un'entità autenticata un'autorizzazione per eseguire un'azione o accedere a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="32c23-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="32c23-106">A volte l'autenticazione viene abbreviata `AuthN` e l'autorizzazione viene abbreviata per `AuthZ`.</span><span class="sxs-lookup"><span data-stu-id="32c23-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="32c23-107">Le applicazioni native del cloud devono basarsi su protocolli basati su HTTP aperti per autenticare le entità di sicurezza, poiché sia i client che le applicazioni possono essere eseguiti ovunque nel mondo su qualsiasi piattaforma o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="32c23-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="32c23-108">L'unico fattore comune è HTTP.</span><span class="sxs-lookup"><span data-stu-id="32c23-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="32c23-109">Molte organizzazioni si basano ancora sui servizi di autenticazione locali come Active Directory Federation Services (ADFS).</span><span class="sxs-lookup"><span data-stu-id="32c23-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="32c23-110">Sebbene questo approccio abbia tradizionalmente servito le organizzazioni per le esigenze di autenticazione locali, le applicazioni native del cloud traggono vantaggio dai sistemi progettati specificamente per il cloud.</span><span class="sxs-lookup"><span data-stu-id="32c23-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="32c23-111">Una recente consulenza NCSC (National Cyber Security Centre) 2019 del Regno Unito afferma che "le organizzazioni che utilizzano Azure AD come origine di autenticazione primaria diminuiranno effettivamente i rischi rispetto ad ADFS".</span><span class="sxs-lookup"><span data-stu-id="32c23-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="32c23-112">Di seguito sono riportati alcuni dei motivi descritti in [questa analisi](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) :</span><span class="sxs-lookup"><span data-stu-id="32c23-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="32c23-113">Accesso al set completo di tecnologie di protezione delle credenziali di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32c23-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="32c23-114">La maggior parte delle organizzazioni si trova già in una certa misura Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32c23-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="32c23-115">Il doppio hash degli hash NTLM garantisce che il compromesso non consenta le credenziali che funzionano in Active Directory locali.</span><span class="sxs-lookup"><span data-stu-id="32c23-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="32c23-116">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="32c23-116">References</span></span>

- [<span data-ttu-id="32c23-117">Nozioni di base sull'autenticazione</span><span class="sxs-lookup"><span data-stu-id="32c23-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="32c23-118">Attestazioni e token di accesso</span><span class="sxs-lookup"><span data-stu-id="32c23-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="32c23-119">Potrebbe essere il momento di abbandonare i servizi di autenticazione locali</span><span class="sxs-lookup"><span data-stu-id="32c23-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="32c23-120">[Precedente](identity.md)
>[Successivo](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="32c23-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
