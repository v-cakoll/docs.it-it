---
ms.openlocfilehash: db941229e02064ee856829417d6762aa17b0b926
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309151"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="67656-101">Localizzazione: Costruttore obsoleto rimosso nel middleware di localizzazione della richiesta</span><span class="sxs-lookup"><span data-stu-id="67656-101">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="67656-102">Il <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> costruttore che non dispone di un <xref:Microsoft.Extensions.Logging.ILoggerFactory> parametro è stato contrassegnato come obsoleto [nel commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span><span class="sxs-lookup"><span data-stu-id="67656-102">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="67656-103">In ASP.NET Core 5,0, il costruttore obsoleto è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="67656-103">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="67656-104">Per informazioni, vedere [DotNet/aspnetcore # 23785](https://github.com/dotnet/aspnetcore/issues/23785).</span><span class="sxs-lookup"><span data-stu-id="67656-104">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="67656-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="67656-105">Version introduced</span></span>

<span data-ttu-id="67656-106">5,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="67656-106">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="67656-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="67656-107">Old behavior</span></span>

<span data-ttu-id="67656-108">Il costruttore obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` esiste.</span><span class="sxs-lookup"><span data-stu-id="67656-108">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="67656-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="67656-109">New behavior</span></span>

<span data-ttu-id="67656-110">Il costruttore obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` non esiste.</span><span class="sxs-lookup"><span data-stu-id="67656-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="67656-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="67656-111">Reason for change</span></span>

<span data-ttu-id="67656-112">Questa modifica garantisce che il middleware di localizzazione delle richieste abbia sempre accesso a un logger.</span><span class="sxs-lookup"><span data-stu-id="67656-112">This change ensures that the request localization middleware always has access to a logger.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="67656-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="67656-113">Recommended action</span></span>

<span data-ttu-id="67656-114">Quando si crea manualmente un'istanza di `RequestLocalizationMiddleware` , passare un' `ILoggerFactory` istanza del costruttore.</span><span class="sxs-lookup"><span data-stu-id="67656-114">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="67656-115">Se un' `ILoggerFactory` istanza valida non è disponibile in tale contesto, provare a passare il costruttore del middleware a un' <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> istanza.</span><span class="sxs-lookup"><span data-stu-id="67656-115">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

#### <a name="category"></a><span data-ttu-id="67656-116">Categoria</span><span class="sxs-lookup"><span data-stu-id="67656-116">Category</span></span>

<span data-ttu-id="67656-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="67656-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="67656-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="67656-118">Affected APIs</span></span>

[<span data-ttu-id="67656-119">RequestLocalizationMiddleware. ctor (RequestDelegate, IOptions \<RequestLocalizationOptions> )</span><span class="sxs-lookup"><span data-stu-id="67656-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
