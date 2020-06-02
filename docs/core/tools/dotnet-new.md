---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 04/10/2020
ms.openlocfilehash: 39301ad95761848b60b45cb5c18ede937f70c32c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283975"
---
# <a name="dotnet-new"></a><span data-ttu-id="1bd89-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bd89-103">dotnet new</span></span>

<span data-ttu-id="1bd89-104">**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1bd89-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1bd89-105">Nome</span><span class="sxs-lookup"><span data-stu-id="1bd89-105">Name</span></span>

<span data-ttu-id="1bd89-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1bd89-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1bd89-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="1bd89-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bd89-108">Description</span></span>

<span data-ttu-id="1bd89-109">Il `dotnet new` comando crea un progetto .NET Core o altri artefatti in base a un modello.</span><span class="sxs-lookup"><span data-stu-id="1bd89-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="1bd89-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="1bd89-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="1bd89-111">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="1bd89-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="1bd89-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1bd89-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="1bd89-113">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="1bd89-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="1bd89-114">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="1bd89-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="1bd89-115">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="1bd89-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="1bd89-116">È possibile eseguire `dotnet new --list` o `dotnet new -l` per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="1bd89-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="1bd89-117">Se il `TEMPLATE` valore non corrisponde esattamente al testo presente nella colonna **modelli** o **nome breve** della tabella restituita, viene eseguita una corrispondenza della sottostringa su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="1bd89-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="1bd89-118">A partire da .NET Core 3,0 SDK, l'interfaccia della riga di comando Cerca i modelli in NuGet.org quando si richiama il `dotnet new` comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bd89-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="1bd89-119">Se l'interfaccia della riga di comando non riesce a trovare una corrispondenza del modello durante la chiamata `dotnet new` , non anche parziale.</span><span class="sxs-lookup"><span data-stu-id="1bd89-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="1bd89-120">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="1bd89-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="1bd89-121">In questo caso, il progetto o l'artefatto viene creato, ma l'interfaccia della riga di comando segnala una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="1bd89-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="1bd89-122">Nella tabella seguente sono illustrati i modelli preinstallati con la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="1bd89-123">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="1bd89-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="1bd89-124">Fare clic sul collegamento nome breve per visualizzare le opzioni specifiche del modello.</span><span class="sxs-lookup"><span data-stu-id="1bd89-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="1bd89-125">Modelli</span><span class="sxs-lookup"><span data-stu-id="1bd89-125">Templates</span></span>                                    | <span data-ttu-id="1bd89-126">Nome breve</span><span class="sxs-lookup"><span data-stu-id="1bd89-126">Short name</span></span>                      | <span data-ttu-id="1bd89-127">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="1bd89-127">Language</span></span>     | <span data-ttu-id="1bd89-128">Tag</span><span class="sxs-lookup"><span data-stu-id="1bd89-128">Tags</span></span>                                  | <span data-ttu-id="1bd89-129">Introdotte</span><span class="sxs-lookup"><span data-stu-id="1bd89-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="1bd89-130">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="1bd89-130">Console Application</span></span>                          | [<span data-ttu-id="1bd89-131">Console</span><span class="sxs-lookup"><span data-stu-id="1bd89-131">console</span></span>](#console)             | <span data-ttu-id="1bd89-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bd89-132">[C#], F#, VB</span></span> | <span data-ttu-id="1bd89-133">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="1bd89-133">Common/Console</span></span>                        | <span data-ttu-id="1bd89-134">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-134">1.0</span></span>        |
| <span data-ttu-id="1bd89-135">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="1bd89-135">Class library</span></span>                                | [<span data-ttu-id="1bd89-136">classlib</span><span class="sxs-lookup"><span data-stu-id="1bd89-136">classlib</span></span>](#classlib)           | <span data-ttu-id="1bd89-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bd89-137">[C#], F#, VB</span></span> | <span data-ttu-id="1bd89-138">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="1bd89-138">Common/Library</span></span>                        | <span data-ttu-id="1bd89-139">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-139">1.0</span></span>        |
| <span data-ttu-id="1bd89-140">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-140">WPF Application</span></span>                              | [<span data-ttu-id="1bd89-141">WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="1bd89-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-142">[C#]</span></span>         | <span data-ttu-id="1bd89-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-143">Common/WPF</span></span>                            | <span data-ttu-id="1bd89-144">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-144">3.0</span></span>        |
| <span data-ttu-id="1bd89-145">Libreria di classi WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-145">WPF Class library</span></span>                            | [<span data-ttu-id="1bd89-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="1bd89-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="1bd89-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-147">[C#]</span></span>         | <span data-ttu-id="1bd89-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-148">Common/WPF</span></span>                            | <span data-ttu-id="1bd89-149">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-149">3.0</span></span>        |
| <span data-ttu-id="1bd89-150">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="1bd89-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="1bd89-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="1bd89-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-152">[C#]</span></span>         | <span data-ttu-id="1bd89-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-153">Common/WPF</span></span>                            | <span data-ttu-id="1bd89-154">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-154">3.0</span></span>        |
| <span data-ttu-id="1bd89-155">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="1bd89-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="1bd89-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="1bd89-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-157">[C#]</span></span>         | <span data-ttu-id="1bd89-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bd89-158">Common/WPF</span></span>                            | <span data-ttu-id="1bd89-159">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-159">3.0</span></span>        |
| <span data-ttu-id="1bd89-160">Applicazione Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1bd89-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="1bd89-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="1bd89-161">winforms</span></span>](#winforms)           | <span data-ttu-id="1bd89-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-162">[C#]</span></span>         | <span data-ttu-id="1bd89-163">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bd89-163">Common/WinForms</span></span>                       | <span data-ttu-id="1bd89-164">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-164">3.0</span></span>        |
| <span data-ttu-id="1bd89-165">Libreria di classi Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1bd89-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="1bd89-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="1bd89-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="1bd89-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-167">[C#]</span></span>         | <span data-ttu-id="1bd89-168">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bd89-168">Common/WinForms</span></span>                       | <span data-ttu-id="1bd89-169">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-169">3.0</span></span>        |
| <span data-ttu-id="1bd89-170">Servizio ruolo di lavoro</span><span class="sxs-lookup"><span data-stu-id="1bd89-170">Worker Service</span></span>                               | [<span data-ttu-id="1bd89-171">lavoro</span><span class="sxs-lookup"><span data-stu-id="1bd89-171">worker</span></span>](#web-others)           | <span data-ttu-id="1bd89-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-172">[C#]</span></span>         | <span data-ttu-id="1bd89-173">Comune/di lavoro/Web</span><span class="sxs-lookup"><span data-stu-id="1bd89-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="1bd89-174">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-174">3.0</span></span>        |
| <span data-ttu-id="1bd89-175">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="1bd89-175">Unit Test Project</span></span>                            | [<span data-ttu-id="1bd89-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="1bd89-176">mstest</span></span>](#test)                 | <span data-ttu-id="1bd89-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bd89-177">[C#], F#, VB</span></span> | <span data-ttu-id="1bd89-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="1bd89-178">Test/MSTest</span></span>                           | <span data-ttu-id="1bd89-179">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-179">1.0</span></span>        |
| <span data-ttu-id="1bd89-180">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="1bd89-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="1bd89-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="1bd89-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bd89-182">[C#], F#, VB</span></span> | <span data-ttu-id="1bd89-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-183">Test/NUnit</span></span>                            | <span data-ttu-id="1bd89-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="1bd89-184">2.1.400</span></span>    |
| <span data-ttu-id="1bd89-185">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="1bd89-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="1bd89-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bd89-186">[C#], F#, VB</span></span> | <span data-ttu-id="1bd89-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-187">Test/NUnit</span></span>                            | <span data-ttu-id="1bd89-188">2.2</span><span class="sxs-lookup"><span data-stu-id="1bd89-188">2.2</span></span>        |
| <span data-ttu-id="1bd89-189">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="1bd89-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-190">xunit</span></span>](#test)                  | <span data-ttu-id="1bd89-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bd89-191">[C#], F#, VB</span></span> | <span data-ttu-id="1bd89-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-192">Test/xUnit</span></span>                            | <span data-ttu-id="1bd89-193">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-193">1.0</span></span>        |
| <span data-ttu-id="1bd89-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="1bd89-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="1bd89-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-195">[C#]</span></span>         | <span data-ttu-id="1bd89-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bd89-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bd89-197">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-197">3.0</span></span>        |
| <span data-ttu-id="1bd89-198">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="1bd89-198">Razor Page</span></span>                                   | [<span data-ttu-id="1bd89-199">pagina</span><span class="sxs-lookup"><span data-stu-id="1bd89-199">page</span></span>](#page)                   | <span data-ttu-id="1bd89-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-200">[C#]</span></span>         | <span data-ttu-id="1bd89-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bd89-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bd89-202">2.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-202">2.0</span></span>        |
| <span data-ttu-id="1bd89-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="1bd89-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="1bd89-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="1bd89-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="1bd89-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-205">[C#]</span></span>         | <span data-ttu-id="1bd89-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bd89-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bd89-207">2.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-207">2.0</span></span>        |
| <span data-ttu-id="1bd89-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="1bd89-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="1bd89-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-209">[C#]</span></span>         | <span data-ttu-id="1bd89-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bd89-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bd89-211">2.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-211">2.0</span></span>        |
| <span data-ttu-id="1bd89-212">App Server Blazer</span><span class="sxs-lookup"><span data-stu-id="1bd89-212">Blazor Server App</span></span>                            | [<span data-ttu-id="1bd89-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="1bd89-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="1bd89-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-214">[C#]</span></span>         | <span data-ttu-id="1bd89-215">Web/Blazer</span><span class="sxs-lookup"><span data-stu-id="1bd89-215">Web/Blazor</span></span>                            | <span data-ttu-id="1bd89-216">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-216">3.0</span></span>        |
| <span data-ttu-id="1bd89-217">App webassembly Blazer</span><span class="sxs-lookup"><span data-stu-id="1bd89-217">Blazor WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="1bd89-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-218">[C#]</span></span>         | <span data-ttu-id="1bd89-219">Web/Blazer/webassembly</span><span class="sxs-lookup"><span data-stu-id="1bd89-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="1bd89-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="1bd89-220">3.1.300</span></span>    |
| <span data-ttu-id="1bd89-221">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="1bd89-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="1bd89-222">Web</span><span class="sxs-lookup"><span data-stu-id="1bd89-222">web</span></span>](#web)                     | <span data-ttu-id="1bd89-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1bd89-223">[C#], F#</span></span>     | <span data-ttu-id="1bd89-224">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="1bd89-224">Web/Empty</span></span>                             | <span data-ttu-id="1bd89-225">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-225">1.0</span></span>        |
| <span data-ttu-id="1bd89-226">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="1bd89-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="1bd89-227">MVC</span><span class="sxs-lookup"><span data-stu-id="1bd89-227">mvc</span></span>](#web-options)             | <span data-ttu-id="1bd89-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1bd89-228">[C#], F#</span></span>     | <span data-ttu-id="1bd89-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="1bd89-229">Web/MVC</span></span>                               | <span data-ttu-id="1bd89-230">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-230">1.0</span></span>        |
| <span data-ttu-id="1bd89-231">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1bd89-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="1bd89-232">WebApp, Razor</span><span class="sxs-lookup"><span data-stu-id="1bd89-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="1bd89-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-233">[C#]</span></span>         | <span data-ttu-id="1bd89-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="1bd89-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="1bd89-235">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="1bd89-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="1bd89-236">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="1bd89-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="1bd89-237">angolare</span><span class="sxs-lookup"><span data-stu-id="1bd89-237">angular</span></span>](#spa)                 | <span data-ttu-id="1bd89-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-238">[C#]</span></span>         | <span data-ttu-id="1bd89-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="1bd89-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1bd89-240">2.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-240">2.0</span></span>        |
| <span data-ttu-id="1bd89-241">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="1bd89-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="1bd89-242">React</span><span class="sxs-lookup"><span data-stu-id="1bd89-242">react</span></span>](#spa)                   | <span data-ttu-id="1bd89-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-243">[C#]</span></span>         | <span data-ttu-id="1bd89-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="1bd89-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1bd89-245">2.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-245">2.0</span></span>        |
| <span data-ttu-id="1bd89-246">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="1bd89-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="1bd89-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="1bd89-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="1bd89-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-248">[C#]</span></span>         | <span data-ttu-id="1bd89-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="1bd89-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1bd89-250">2.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-250">2.0</span></span>        |
| <span data-ttu-id="1bd89-251">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="1bd89-251">Razor Class Library</span></span>                          | [<span data-ttu-id="1bd89-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="1bd89-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="1bd89-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-253">[C#]</span></span>         | <span data-ttu-id="1bd89-254">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="1bd89-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="1bd89-255">2.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-255">2.1</span></span>        |
| <span data-ttu-id="1bd89-256">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1bd89-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="1bd89-257">WebAPI</span><span class="sxs-lookup"><span data-stu-id="1bd89-257">webapi</span></span>](#webapi)               | <span data-ttu-id="1bd89-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1bd89-258">[C#], F#</span></span>     | <span data-ttu-id="1bd89-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="1bd89-259">Web/WebAPI</span></span>                            | <span data-ttu-id="1bd89-260">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-260">1.0</span></span>        |
| <span data-ttu-id="1bd89-261">Servizio ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="1bd89-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="1bd89-262">grpc</span><span class="sxs-lookup"><span data-stu-id="1bd89-262">grpc</span></span>](#web-others)             | <span data-ttu-id="1bd89-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bd89-263">[C#]</span></span>         | <span data-ttu-id="1bd89-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="1bd89-264">Web/gRPC</span></span>                              | <span data-ttu-id="1bd89-265">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-265">3.0</span></span>        |
| <span data-ttu-id="1bd89-266">file gitignore DotNet</span><span class="sxs-lookup"><span data-stu-id="1bd89-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="1bd89-267">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bd89-267">Config</span></span>                                | <span data-ttu-id="1bd89-268">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-268">3.0</span></span>        |
| <span data-ttu-id="1bd89-269">File global.json</span><span class="sxs-lookup"><span data-stu-id="1bd89-269">global.json file</span></span>                             | [<span data-ttu-id="1bd89-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="1bd89-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="1bd89-271">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bd89-271">Config</span></span>                                | <span data-ttu-id="1bd89-272">2.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-272">2.0</span></span>        |
| <span data-ttu-id="1bd89-273">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="1bd89-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="1bd89-274">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bd89-274">Config</span></span>                                | <span data-ttu-id="1bd89-275">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-275">1.0</span></span>        |
| <span data-ttu-id="1bd89-276">File manifesto dello strumento locale DotNet</span><span class="sxs-lookup"><span data-stu-id="1bd89-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="1bd89-277">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bd89-277">Config</span></span>                                | <span data-ttu-id="1bd89-278">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-278">3.0</span></span>        |
| <span data-ttu-id="1bd89-279">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="1bd89-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="1bd89-280">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bd89-280">Config</span></span>                                | <span data-ttu-id="1bd89-281">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-281">1.0</span></span>        |
| <span data-ttu-id="1bd89-282">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="1bd89-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="1bd89-283">Soluzione</span><span class="sxs-lookup"><span data-stu-id="1bd89-283">Solution</span></span>                              | <span data-ttu-id="1bd89-284">1.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-284">1.0</span></span>        |
| <span data-ttu-id="1bd89-285">File buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="1bd89-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="1bd89-286">proto</span><span class="sxs-lookup"><span data-stu-id="1bd89-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="1bd89-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="1bd89-287">Web/gRPC</span></span>                              | <span data-ttu-id="1bd89-288">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="1bd89-289">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1bd89-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="1bd89-290">Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.</span><span class="sxs-lookup"><span data-stu-id="1bd89-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="1bd89-291">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="1bd89-292">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="1bd89-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="1bd89-293">Questa operazione è necessaria quando il modello scelto sostituisce i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="1bd89-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1bd89-294">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1bd89-294">Prints out help for the command.</span></span> <span data-ttu-id="1bd89-295">Può essere richiamato per il `dotnet new` comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="1bd89-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="1bd89-296">Ad esempio: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="1bd89-297">Installa un pacchetto di modelli dall'oggetto `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="1bd89-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1bd89-298">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="1bd89-299">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione stabile più recente del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="1bd89-300">Vedere un esempio nella sezione degli [esempi](#examples) .</span><span class="sxs-lookup"><span data-stu-id="1bd89-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="1bd89-301">Se una versione del modello è già installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente, se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="1bd89-302">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="1bd89-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="1bd89-303">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="1bd89-304">Se non viene specificato alcun nome, elenca tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="1bd89-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="1bd89-305">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="1bd89-305">The language of the template to create.</span></span> <span data-ttu-id="1bd89-306">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="1bd89-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="1bd89-307">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="1bd89-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1bd89-308">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="1bd89-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="1bd89-309">In questi casi, racchiudere il valore del parametro Language tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="1bd89-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="1bd89-310">Ad esempio: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="1bd89-311">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-311">The name for the created output.</span></span> <span data-ttu-id="1bd89-312">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1bd89-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="1bd89-313">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="1bd89-314">Disponibile a partire da .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="1bd89-315">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-315">Location to place the generated output.</span></span> <span data-ttu-id="1bd89-316">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1bd89-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="1bd89-317">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="1bd89-317">Filters templates based on available types.</span></span> <span data-ttu-id="1bd89-318">I valori predefiniti sono `project` , `item` e `other` .</span><span class="sxs-lookup"><span data-stu-id="1bd89-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="1bd89-319">Disinstalla un pacchetto di modelli in `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="1bd89-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1bd89-320">Quando il `<PATH|NUGET_ID>` valore non è specificato, vengono visualizzati tutti i pacchetti di modelli attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="1bd89-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="1bd89-321">Quando si specifica `NUGET_ID` , non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="1bd89-322">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="1bd89-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1bd89-323">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="1bd89-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="1bd89-324">Ad esempio, *C:/Users/ \<USER> /Documents/templates/GarciaSoftware.ConsoleTemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1bd89-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="1bd89-325">Non includere una barra di directory finale terminata nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="1bd89-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="1bd89-326">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="1bd89-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="1bd89-327">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="1bd89-328">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="1bd89-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="1bd89-329">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="1bd89-330">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="1bd89-330">Template options</span></span>

<span data-ttu-id="1bd89-331">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="1bd89-331">Each project template may have additional options available.</span></span> <span data-ttu-id="1bd89-332">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bd89-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="1bd89-333">console</span><span class="sxs-lookup"><span data-stu-id="1bd89-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-334">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-335">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1bd89-336">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-337">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-337">SDK version</span></span> | <span data-ttu-id="1bd89-338">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-339">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-340">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bd89-341">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bd89-342">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bd89-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="1bd89-343">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="1bd89-343">Not supported for F#.</span></span> <span data-ttu-id="1bd89-344">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bd89-345">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bd89-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-346">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="1bd89-347">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="1bd89-348">classlib</span><span class="sxs-lookup"><span data-stu-id="1bd89-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-349">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-350">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="1bd89-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="1bd89-351">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bd89-352">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bd89-353">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bd89-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="1bd89-354">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="1bd89-354">Not supported for F#.</span></span> <span data-ttu-id="1bd89-355">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bd89-356">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bd89-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-357">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a><span data-ttu-id="1bd89-358">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="1bd89-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-359">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-360">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="1bd89-361">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bd89-362">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bd89-363">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bd89-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="1bd89-364">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bd89-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-365">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a><span data-ttu-id="1bd89-366">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="1bd89-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bd89-367">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bd89-368">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bd89-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="1bd89-369">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bd89-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-370">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a><span data-ttu-id="1bd89-371">Worker, grpc</span><span class="sxs-lookup"><span data-stu-id="1bd89-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-372">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-373">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="1bd89-374">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bd89-375">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-376">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="1bd89-377">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-378">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-379">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1bd89-380">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-381">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-381">SDK version</span></span> | <span data-ttu-id="1bd89-382">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-383">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-384">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="1bd89-385">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="1bd89-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-386">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="1bd89-387">NUnit</span><span class="sxs-lookup"><span data-stu-id="1bd89-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-388">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="1bd89-389">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-390">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-390">SDK version</span></span> | <span data-ttu-id="1bd89-391">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-392">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-393">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bd89-394">2.2</span><span class="sxs-lookup"><span data-stu-id="1bd89-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="1bd89-395">2.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="1bd89-396">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="1bd89-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-397">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="1bd89-398">pagina</span><span class="sxs-lookup"><span data-stu-id="1bd89-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="1bd89-399">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-399">Namespace for the generated code.</span></span> <span data-ttu-id="1bd89-400">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="1bd89-401">Crea la pagina senza PageModel.</span><span class="sxs-lookup"><span data-stu-id="1bd89-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a><span data-ttu-id="1bd89-402">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="1bd89-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="1bd89-403">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-403">Namespace for the generated code.</span></span> <span data-ttu-id="1bd89-404">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="1bd89-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="1bd89-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bd89-406">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bd89-406">The type of authentication to use.</span></span> <span data-ttu-id="1bd89-407">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bd89-407">The possible values are:</span></span>

  - <span data-ttu-id="1bd89-408">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bd89-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bd89-409">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="1bd89-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="1bd89-410">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1bd89-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1bd89-411">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="1bd89-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1bd89-412">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="1bd89-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="1bd89-413">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1bd89-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1bd89-414">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1bd89-415">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-416">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1bd89-417">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1bd89-418">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="1bd89-419">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="1bd89-420">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="1bd89-421">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="1bd89-422">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1bd89-423">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1bd89-424">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bd89-425">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1bd89-426">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-426">The Client ID for this project.</span></span> <span data-ttu-id="1bd89-427">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bd89-428">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1bd89-429">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="1bd89-429">The domain for the directory tenant.</span></span> <span data-ttu-id="1bd89-430">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-431">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1bd89-432">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1bd89-433">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bd89-434">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="1bd89-435">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="1bd89-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1bd89-436">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-437">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1bd89-438">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="1bd89-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1bd89-439">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bd89-440">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bd89-441">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bd89-441">Turns off HTTPS.</span></span> <span data-ttu-id="1bd89-442">Questa opzione si applica solo se `Individual` ,, `IndividualB2C` `SingleOrg` o `MultiOrg` non vengono utilizzati per `--auth` .</span><span class="sxs-lookup"><span data-stu-id="1bd89-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bd89-443">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bd89-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bd89-444">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-445">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="1bd89-446">Web</span><span class="sxs-lookup"><span data-stu-id="1bd89-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bd89-447">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-448">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-449">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bd89-450">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-451">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-451">SDK version</span></span> | <span data-ttu-id="1bd89-452">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-453">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-454">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bd89-455">2.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="1bd89-456">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bd89-457">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bd89-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a><span data-ttu-id="1bd89-458">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="1bd89-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bd89-459">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bd89-459">The type of authentication to use.</span></span> <span data-ttu-id="1bd89-460">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bd89-460">The possible values are:</span></span>

  - <span data-ttu-id="1bd89-461">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bd89-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bd89-462">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="1bd89-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="1bd89-463">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1bd89-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1bd89-464">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="1bd89-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1bd89-465">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="1bd89-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="1bd89-466">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1bd89-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1bd89-467">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1bd89-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-469">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1bd89-470">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1bd89-471">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="1bd89-472">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="1bd89-473">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="1bd89-474">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="1bd89-475">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1bd89-476">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1bd89-477">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bd89-478">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1bd89-479">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-479">The Client ID for this project.</span></span> <span data-ttu-id="1bd89-480">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bd89-481">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1bd89-482">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="1bd89-482">The domain for the directory tenant.</span></span> <span data-ttu-id="1bd89-483">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-484">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1bd89-485">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1bd89-486">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bd89-487">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="1bd89-488">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="1bd89-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1bd89-489">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-490">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1bd89-491">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="1bd89-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1bd89-492">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bd89-493">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bd89-494">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bd89-494">Turns off HTTPS.</span></span> <span data-ttu-id="1bd89-495">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="1bd89-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bd89-496">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bd89-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bd89-497">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-498">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-499">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1bd89-500">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-501">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-501">SDK version</span></span> | <span data-ttu-id="1bd89-502">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-503">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-504">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="1bd89-505">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="1bd89-506">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="1bd89-507">Opzione non disponibile in .NET Core 2,2 e 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="1bd89-508">Determina se il progetto è configurato per usare la [compilazione del runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle build di debug.</span><span class="sxs-lookup"><span data-stu-id="1bd89-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="1bd89-509">Opzione disponibile a partire da .NET Core 3.1.201 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a><span data-ttu-id="1bd89-510">angolare, React</span><span class="sxs-lookup"><span data-stu-id="1bd89-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bd89-511">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bd89-511">The type of authentication to use.</span></span> <span data-ttu-id="1bd89-512">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="1bd89-513">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bd89-513">The possible values are:</span></span>

  - <span data-ttu-id="1bd89-514">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bd89-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bd89-515">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="1bd89-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bd89-516">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-517">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bd89-518">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bd89-518">Turns off HTTPS.</span></span> <span data-ttu-id="1bd89-519">Questa opzione si applica solo se l'autenticazione è `None` .</span><span class="sxs-lookup"><span data-stu-id="1bd89-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bd89-520">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bd89-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bd89-521">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-522">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-523">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-524">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bd89-525">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-526">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-526">SDK version</span></span> | <span data-ttu-id="1bd89-527">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-528">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-529">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bd89-530">2.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="1bd89-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="1bd89-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bd89-532">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-533">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-534">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bd89-535">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-536">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-536">SDK version</span></span> | <span data-ttu-id="1bd89-537">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-538">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-539">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bd89-540">2.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="1bd89-541">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bd89-542">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bd89-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="1bd89-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="1bd89-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bd89-544">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="1bd89-545">Supporta l'aggiunta di pagine e visualizzazioni tradizionali Razor oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="1bd89-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="1bd89-546">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="1bd89-547">webapi</span><span class="sxs-lookup"><span data-stu-id="1bd89-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bd89-548">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bd89-548">The type of authentication to use.</span></span> <span data-ttu-id="1bd89-549">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bd89-549">The possible values are:</span></span>

  - <span data-ttu-id="1bd89-550">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bd89-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bd89-551">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1bd89-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1bd89-552">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="1bd89-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1bd89-553">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1bd89-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1bd89-554">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1bd89-555">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bd89-556">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1bd89-557">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1bd89-558">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1bd89-559">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1bd89-560">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bd89-561">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1bd89-562">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-562">The Client ID for this project.</span></span> <span data-ttu-id="1bd89-563">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1bd89-564">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1bd89-565">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="1bd89-565">The domain for the directory tenant.</span></span> <span data-ttu-id="1bd89-566">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1bd89-567">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1bd89-568">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bd89-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1bd89-569">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bd89-570">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1bd89-571">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="1bd89-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1bd89-572">Si applica solo all' `SingleOrg` autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="1bd89-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bd89-573">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bd89-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bd89-574">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bd89-574">Turns off HTTPS.</span></span> <span data-ttu-id="1bd89-575">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="1bd89-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="1bd89-576">Questa opzione si applica solo se `IndividualB2C` o `SingleOrg` non vengono usati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bd89-577">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bd89-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bd89-578">Si applica solo all' `IndividualB2C` autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="1bd89-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bd89-579">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bd89-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bd89-580">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bd89-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bd89-581">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bd89-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bd89-582">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bd89-582">SDK version</span></span> | <span data-ttu-id="1bd89-583">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bd89-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bd89-584">3.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bd89-585">3.0</span><span class="sxs-lookup"><span data-stu-id="1bd89-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bd89-586">2.1</span><span class="sxs-lookup"><span data-stu-id="1bd89-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="1bd89-587">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bd89-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="1bd89-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="1bd89-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="1bd89-589">Specifica la versione del .NET Core SDK da usare nel file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="1bd89-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="1bd89-590">Esempi</span><span class="sxs-lookup"><span data-stu-id="1bd89-590">Examples</span></span>

- <span data-ttu-id="1bd89-591">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="1bd89-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="1bd89-592">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1bd89-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="1bd89-593">Creare un progetto libreria di classi .NET Standard nella directory specificata:</span><span class="sxs-lookup"><span data-stu-id="1bd89-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="1bd89-594">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="1bd89-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="1bd89-595">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="1bd89-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="1bd89-596">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="1bd89-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="1bd89-597">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="1bd89-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="1bd89-598">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="1bd89-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="1bd89-599">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="1bd89-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="1bd89-600">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="1bd89-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="1bd89-601">Installare la versione 2,0 dei modelli di SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="1bd89-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="1bd89-602">Elencare i modelli e i dettagli installati, inclusa la modalità di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="1bd89-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="1bd89-603">Creare un file *Global. JSON* nella directory corrente impostando la versione dell'SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="1bd89-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="1bd89-604">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bd89-604">See also</span></span>

- [<span data-ttu-id="1bd89-605">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bd89-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="1bd89-606">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bd89-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="1bd89-607">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="1bd89-607">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="1bd89-608">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bd89-608">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
