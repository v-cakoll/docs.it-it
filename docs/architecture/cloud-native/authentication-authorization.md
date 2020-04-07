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
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="a781f-103">Autenticazione e autorizzazione nelle app cloud native</span><span class="sxs-lookup"><span data-stu-id="a781f-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="a781f-104">*L'autenticazione* è il processo di determinazione dell'identità di un'entità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a781f-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="a781f-105">*L'autorizzazione* è l'atto di concedere a un'entità autenticata l'autorizzazione per eseguire un'azione o accedere a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="a781f-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="a781f-106">A volte l'autenticazione viene abbreviata e l'autorizzazione `AuthN` viene abbreviata in `AuthZ`.</span><span class="sxs-lookup"><span data-stu-id="a781f-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="a781f-107">Le applicazioni native nel cloud devono fare affidamento su protocolli aperti basati su HTTP per autenticare le entità di sicurezza poiché sia i client che le applicazioni potrebbero essere in esecuzione in qualsiasi parte del mondo su qualsiasi piattaforma o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a781f-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="a781f-108">L'unico fattore comune è HTTP.</span><span class="sxs-lookup"><span data-stu-id="a781f-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="a781f-109">Molte organizzazioni si basano ancora su servizi di autenticazione locale come Active Directory Federation Services (ADFS).</span><span class="sxs-lookup"><span data-stu-id="a781f-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="a781f-110">Sebbene questo approccio abbia tradizionalmente servito bene le organizzazioni per le esigenze di autenticazione locali, le applicazioni native nel cloud traggono vantaggio dai sistemi progettati specificamente per il cloud.</span><span class="sxs-lookup"><span data-stu-id="a781f-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="a781f-111">Un recente advisory del National Cyber Security Centre (NCSC) del Regno Unito nel Regno Unito afferma che "le organizzazioni che usano Azure AD come origine di autenticazione primaria abbasseranno effettivamente il rischio rispetto ad ADFS".</span><span class="sxs-lookup"><span data-stu-id="a781f-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="a781f-112">Alcuni motivi descritti in [questa analisi](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) includono:</span><span class="sxs-lookup"><span data-stu-id="a781f-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="a781f-113">Accesso al set completo di tecnologie microsoft per la protezione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="a781f-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="a781f-114">La maggior parte delle organizzazioni si basa già su Azure AD in una certa misura.</span><span class="sxs-lookup"><span data-stu-id="a781f-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="a781f-115">Il doppio hash degli hash NTLM garantisce che la compromissione non consenta le credenziali che funzionano in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="a781f-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="a781f-116">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a781f-116">References</span></span>

- [<span data-ttu-id="a781f-117">Nozioni di base sull'autenticazione</span><span class="sxs-lookup"><span data-stu-id="a781f-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="a781f-118">Token di accesso e attestazioniAccess tokens and claims</span><span class="sxs-lookup"><span data-stu-id="a781f-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="a781f-119">Potrebbe essere il momento di abbandonare i servizi di autenticazione locali</span><span class="sxs-lookup"><span data-stu-id="a781f-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="a781f-120">[Successivo](identity.md)
>[precedente](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="a781f-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
