---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394212"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a><span data-ttu-id="44c27-101">MVC: shim di compatibilità API Web rimosso</span><span class="sxs-lookup"><span data-stu-id="44c27-101">MVC: Web API compatibility shim removed</span></span>

<span data-ttu-id="44c27-102">A partire da ASP.NET Core 3,0, il pacchetto `Microsoft.AspNetCore.Mvc.WebApiCompatShim` non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="44c27-102">Starting with ASP.NET Core 3.0, the `Microsoft.AspNetCore.Mvc.WebApiCompatShim` package is no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="44c27-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="44c27-103">Change description</span></span>

<span data-ttu-id="44c27-104">Il pacchetto `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) fornisce la compatibilità parziale in ASP.NET Core con l'API Web 2 di ASP.NET 4. x per semplificare la migrazione delle implementazioni API Web esistenti ai ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44c27-104">The `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) package provides partial compatibility in ASP.NET Core with ASP.NET 4.x Web API 2 to simplify migrating existing Web API implementations to ASP.NET Core.</span></span> <span data-ttu-id="44c27-105">Tuttavia, le app che usano WebApiCompatShim non traggono vantaggio dalle funzionalità relative all'API fornite nelle versioni di ASP.NET Core recenti.</span><span class="sxs-lookup"><span data-stu-id="44c27-105">However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases.</span></span> <span data-ttu-id="44c27-106">Tali funzionalità includono la generazione di specifiche API aperte migliorata, la gestione standardizzata degli errori e la generazione di codice client.</span><span class="sxs-lookup"><span data-stu-id="44c27-106">Such features include improved Open API specification generation, standardized error handling, and client code generation.</span></span> <span data-ttu-id="44c27-107">Per concentrarsi meglio sulle attività dell'API in 3,0, WebApiCompatShim è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="44c27-107">To better focus the API efforts in 3.0, WebApiCompatShim was removed.</span></span> <span data-ttu-id="44c27-108">Le app esistenti che usano WebApiCompatShim devono eseguire la migrazione al modello più recente `[ApiController]`.</span><span class="sxs-lookup"><span data-stu-id="44c27-108">Existing apps using the WebApiCompatShim should migrate to the newer `[ApiController]` model.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="44c27-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="44c27-109">Version introduced</span></span>

<span data-ttu-id="44c27-110">3.0</span><span class="sxs-lookup"><span data-stu-id="44c27-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="44c27-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="44c27-111">Reason for change</span></span>

<span data-ttu-id="44c27-112">Lo shim di compatibilità dell'API Web è stato uno strumento di migrazione.</span><span class="sxs-lookup"><span data-stu-id="44c27-112">The Web API compatibility shim was a migration tool.</span></span> <span data-ttu-id="44c27-113">Limita l'accesso degli utenti alle nuove funzionalità aggiunte in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44c27-113">It restricts user access to new functionality added in ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="44c27-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="44c27-114">Recommended action</span></span>

<span data-ttu-id="44c27-115">Rimuovere l'utilizzo di questo shim e migrare direttamente alla funzionalità simile in ASP.NET Core stesso.</span><span class="sxs-lookup"><span data-stu-id="44c27-115">Remove usage of this shim and migrate directly to the similar functionality in ASP.NET Core itself.</span></span>

#### <a name="category"></a><span data-ttu-id="44c27-116">Category</span><span class="sxs-lookup"><span data-stu-id="44c27-116">Category</span></span>

<span data-ttu-id="44c27-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="44c27-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="44c27-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="44c27-118">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
