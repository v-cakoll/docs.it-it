---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394212"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a><span data-ttu-id="bbcbd-101">MVC: shim di compatibilità API Web rimosso</span><span class="sxs-lookup"><span data-stu-id="bbcbd-101">MVC: Web API compatibility shim removed</span></span>

<span data-ttu-id="bbcbd-102">A partire da ASP.NET Core `Microsoft.AspNetCore.Mvc.WebApiCompatShim` 3.0, il pacchetto non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-102">Starting with ASP.NET Core 3.0, the `Microsoft.AspNetCore.Mvc.WebApiCompatShim` package is no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bbcbd-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="bbcbd-103">Change description</span></span>

<span data-ttu-id="bbcbd-104">Il `Microsoft.AspNetCore.Mvc.WebApiCompatShim` pacchetto (WebApiCompatShim) fornisce compatibilità parziale in ASP.NET Core con ASP.NET 4.x Web API 2 per semplificare la migrazione delle implementazioni di API Web esistenti a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-104">The `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) package provides partial compatibility in ASP.NET Core with ASP.NET 4.x Web API 2 to simplify migrating existing Web API implementations to ASP.NET Core.</span></span> <span data-ttu-id="bbcbd-105">Tuttavia, le app che utilizzano WebApiCompatShim non traggono vantaggio dalle funzionalità correlate alle API che vengono esordiate nelle versioni recenti di ASP.NET Core.However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-105">However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases.</span></span> <span data-ttu-id="bbcbd-106">Tali funzionalità includono una migliore generazione di specifiche Open API, una gestione standardizzata degli errori e la generazione di codice client.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-106">Such features include improved Open API specification generation, standardized error handling, and client code generation.</span></span> <span data-ttu-id="bbcbd-107">Per concentrare meglio gli sforzi dell'API nella 3.0, WebApiCompatShim è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-107">To better focus the API efforts in 3.0, WebApiCompatShim was removed.</span></span> <span data-ttu-id="bbcbd-108">Le app esistenti che usano WebApiCompatShim `[ApiController]` devono eseguire la migrazione al modello più recente.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-108">Existing apps using the WebApiCompatShim should migrate to the newer `[ApiController]` model.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bbcbd-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bbcbd-109">Version introduced</span></span>

<span data-ttu-id="bbcbd-110">3.0</span><span class="sxs-lookup"><span data-stu-id="bbcbd-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bbcbd-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="bbcbd-111">Reason for change</span></span>

<span data-ttu-id="bbcbd-112">Lo shim di compatibilità delle API Web era uno strumento di migrazione.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-112">The Web API compatibility shim was a migration tool.</span></span> <span data-ttu-id="bbcbd-113">Limita l'accesso degli utenti alle nuove funzionalità aggiunte in ASP.NET Core.It restricts user access to new functionality added in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-113">It restricts user access to new functionality added in ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bbcbd-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bbcbd-114">Recommended action</span></span>

<span data-ttu-id="bbcbd-115">Rimuovere l'utilizzo di questo shim ed eseguire la migrazione direttamente alla funzionalità simile in ASP.NET Core stesso.</span><span class="sxs-lookup"><span data-stu-id="bbcbd-115">Remove usage of this shim and migrate directly to the similar functionality in ASP.NET Core itself.</span></span>

#### <a name="category"></a><span data-ttu-id="bbcbd-116">Category</span><span class="sxs-lookup"><span data-stu-id="bbcbd-116">Category</span></span>

<span data-ttu-id="bbcbd-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bbcbd-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bbcbd-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="bbcbd-118">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
