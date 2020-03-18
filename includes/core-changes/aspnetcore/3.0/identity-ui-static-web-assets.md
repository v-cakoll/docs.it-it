---
ms.openlocfilehash: c5e4b5619394f99a419fe48aee190ad741ea8c0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73041659"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a><span data-ttu-id="2704f-101">Identità: l'interfaccia utente usa la funzionalità delle risorse Web staticheIdentity: UI uses static web assets feature</span><span class="sxs-lookup"><span data-stu-id="2704f-101">Identity: UI uses static web assets feature</span></span>

<span data-ttu-id="2704f-102">ASP.NET Core 3.0 è stata introdotta una funzionalità delle risorse Web statiche e l'interfaccia utente di Identity l'ha adottata.</span><span class="sxs-lookup"><span data-stu-id="2704f-102">ASP.NET Core 3.0 introduced a static web assets feature, and Identity UI has adopted it.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2704f-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="2704f-103">Change description</span></span>

<span data-ttu-id="2704f-104">Come risultato dell'interfaccia utente di identità che adotta la funzionalità delle risorse Web statiche:</span><span class="sxs-lookup"><span data-stu-id="2704f-104">As a result of Identity UI adopting the static web assets feature:</span></span>

- <span data-ttu-id="2704f-105">La selezione del framework `IdentityUIFrameworkVersion` viene eseguita utilizzando la proprietà nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2704f-105">Framework selection is accomplished by using the `IdentityUIFrameworkVersion` property in your project file.</span></span>
- <span data-ttu-id="2704f-106">Bootstrap 4 è il framework dell'interfaccia utente predefinito per l'interfaccia utente di identità.</span><span class="sxs-lookup"><span data-stu-id="2704f-106">Bootstrap 4 is the default UI framework for Identity UI.</span></span> <span data-ttu-id="2704f-107">Bootstrap 3 ha raggiunto la fine del ciclo di vita, e si dovrebbe prendere in considerazione la migrazione a una versione supportata.</span><span class="sxs-lookup"><span data-stu-id="2704f-107">Bootstrap 3 has reached end of life, and you should consider migrating to a supported version.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2704f-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2704f-108">Version introduced</span></span>

<span data-ttu-id="2704f-109">3.0</span><span class="sxs-lookup"><span data-stu-id="2704f-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2704f-110">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="2704f-110">Old behavior</span></span>

<span data-ttu-id="2704f-111">Il framework dell'interfaccia utente predefinito per l'interfaccia utente di identità era **Bootstrap 3**.</span><span class="sxs-lookup"><span data-stu-id="2704f-111">The default UI framework for Identity UI was **Bootstrap 3**.</span></span> <span data-ttu-id="2704f-112">È possibile configurare il framework `AddDefaultUI` dell'interfaccia `Startup.ConfigureServices`utente utilizzando un parametro per la chiamata al metodo in .</span><span class="sxs-lookup"><span data-stu-id="2704f-112">The UI framework could be configured using a parameter to the `AddDefaultUI` method call in `Startup.ConfigureServices`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2704f-113">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="2704f-113">New behavior</span></span>

<span data-ttu-id="2704f-114">Il framework dell'interfaccia utente predefinito per l'interfaccia utente di identità è **Bootstrap 4**.</span><span class="sxs-lookup"><span data-stu-id="2704f-114">The default UI framework for Identity UI is **Bootstrap 4**.</span></span> <span data-ttu-id="2704f-115">Il framework dell'interfaccia utente deve essere configurato `AddDefaultUI` nel file di progetto, anziché nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="2704f-115">The UI framework must be configured in your project file, instead of in the `AddDefaultUI` method call.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2704f-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2704f-116">Reason for change</span></span>

<span data-ttu-id="2704f-117">L'adozione della funzionalità degli asset Web statici ha richiesto lo spostamento della configurazione del framework dell'interfaccia utente in MSBuild.</span><span class="sxs-lookup"><span data-stu-id="2704f-117">Adoption of the static web assets feature required that the UI framework configuration move to MSBuild.</span></span> <span data-ttu-id="2704f-118">La decisione sul framework da incorporare è una decisione in fase di compilazione, non una decisione di runtime.</span><span class="sxs-lookup"><span data-stu-id="2704f-118">The decision on which framework to embed is a build-time decision, not a runtime decision.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2704f-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2704f-119">Recommended action</span></span>

<span data-ttu-id="2704f-120">Esaminare l'interfaccia utente del sito per assicurarsi che i nuovi componenti Bootstrap 4 siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="2704f-120">Review your site UI to ensure the new Bootstrap 4 components are compatible.</span></span> <span data-ttu-id="2704f-121">Se necessario, `IdentityUIFrameworkVersion` utilizzare la proprietà MSBuild per ripristinare Bootstrap 3.</span><span class="sxs-lookup"><span data-stu-id="2704f-121">If necessary, use the `IdentityUIFrameworkVersion` MSBuild property to revert to Bootstrap 3.</span></span> <span data-ttu-id="2704f-122">Aggiungere la proprietà `<PropertyGroup>` a un elemento nel file di progetto:Add the property to a element in your project file:</span><span class="sxs-lookup"><span data-stu-id="2704f-122">Add the property to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="2704f-123">Category</span><span class="sxs-lookup"><span data-stu-id="2704f-123">Category</span></span>

<span data-ttu-id="2704f-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2704f-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2704f-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="2704f-125">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
