---
ms.openlocfilehash: 8d7942ef6c36c01a9ae7ae2a9739f26dfcda5813
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394121"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a><span data-ttu-id="cca50-101">Identità: l'interfaccia utente usa la funzionalità statica di asset Web</span><span class="sxs-lookup"><span data-stu-id="cca50-101">Identity: UI uses static web assets feature</span></span>

<span data-ttu-id="cca50-102">ASP.NET Core 3,0 ha introdotto una funzionalità di asset Web statici, che è stata adottata dall'interfaccia utente di identità.</span><span class="sxs-lookup"><span data-stu-id="cca50-102">ASP.NET Core 3.0 introduced a static web assets feature, and Identity UI has adopted it.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cca50-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="cca50-103">Change description</span></span>

<span data-ttu-id="cca50-104">In seguito all'interfaccia utente dell'identità che adotta la funzionalità di asset Web statici:</span><span class="sxs-lookup"><span data-stu-id="cca50-104">As a result of Identity UI adopting the static web assets feature:</span></span>

- <span data-ttu-id="cca50-105">La selezione del Framework viene eseguita usando la proprietà `IdentityUIFrameworkVersion` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cca50-105">Framework selection is accomplished by using the `IdentityUIFrameworkVersion` property in your project file.</span></span>
- <span data-ttu-id="cca50-106">Bootstrap 4 è il Framework dell'interfaccia utente predefinito per l'interfaccia utente Identity.</span><span class="sxs-lookup"><span data-stu-id="cca50-106">Bootstrap 4 is the default UI framework for Identity UI.</span></span> <span data-ttu-id="cca50-107">Il bootstrap 3 ha raggiunto la fine del ciclo di vita ed è consigliabile eseguire la migrazione a una versione supportata.</span><span class="sxs-lookup"><span data-stu-id="cca50-107">Bootstrap 3 has reached end of life, and you should consider migrating to a supported version.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cca50-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="cca50-108">Version introduced</span></span>

<span data-ttu-id="cca50-109">3.0</span><span class="sxs-lookup"><span data-stu-id="cca50-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cca50-110">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="cca50-110">Old behavior</span></span>

<span data-ttu-id="cca50-111">Il Framework dell'interfaccia utente predefinito per l'interfaccia utente di identità è **bootstrap 3**.</span><span class="sxs-lookup"><span data-stu-id="cca50-111">The default UI framework for Identity UI was **Bootstrap 3**.</span></span> <span data-ttu-id="cca50-112">Il Framework dell'interfaccia utente può essere configurato usando un parametro per la chiamata al metodo `AddIdentityUI` in `Startup.ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="cca50-112">The UI framework could be configured using a parameter to the `AddIdentityUI` method call in `Startup.ConfigureServices`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cca50-113">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="cca50-113">New behavior</span></span>

<span data-ttu-id="cca50-114">Il Framework dell'interfaccia utente predefinito per l'interfaccia utente di identità è **bootstrap 4**.</span><span class="sxs-lookup"><span data-stu-id="cca50-114">The default UI framework for Identity UI is **Bootstrap 4**.</span></span> <span data-ttu-id="cca50-115">Il Framework dell'interfaccia utente deve essere configurato nel file di progetto, anziché nella chiamata al metodo `AddIdentityUI`.</span><span class="sxs-lookup"><span data-stu-id="cca50-115">The UI framework must be configured in your project file, instead of in the `AddIdentityUI` method call.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cca50-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="cca50-116">Reason for change</span></span>

<span data-ttu-id="cca50-117">L'adozione della funzionalità Asset Web statici richiede che la configurazione del Framework dell'interfaccia utente passi a MSBuild.</span><span class="sxs-lookup"><span data-stu-id="cca50-117">Adoption of the static web assets feature required that the UI framework configuration move to MSBuild.</span></span> <span data-ttu-id="cca50-118">La decisione sul Framework da incorporare è una decisione in fase di compilazione e non una decisione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cca50-118">The decision on which framework to embed is a build-time decision, not a runtime decision.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cca50-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="cca50-119">Recommended action</span></span>

<span data-ttu-id="cca50-120">Esaminare l'interfaccia utente del sito per assicurarsi che i nuovi componenti di bootstrap 4 siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="cca50-120">Review your site UI to ensure the new Bootstrap 4 components are compatible.</span></span> <span data-ttu-id="cca50-121">Se necessario, usare la proprietà MSBuild `IdentityUIFrameworkVersion` per ripristinare il bootstrap 3.</span><span class="sxs-lookup"><span data-stu-id="cca50-121">If necessary, use the `IdentityUIFrameworkVersion` MSBuild property to revert to Bootstrap 3.</span></span> <span data-ttu-id="cca50-122">Aggiungere la proprietà a un elemento `<PropertyGroup>` nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="cca50-122">Add the property to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="cca50-123">Category</span><span class="sxs-lookup"><span data-stu-id="cca50-123">Category</span></span>

<span data-ttu-id="cca50-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cca50-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cca50-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="cca50-125">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)`

-->