---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 04/10/2020
ms.openlocfilehash: 9a68baafa7ac3e6ad2fdc8f1c6e8621d6e15f1ff
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506857"
---
# <a name="dotnet-new"></a><span data-ttu-id="67974-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="67974-103">dotnet new</span></span>

<span data-ttu-id="67974-104">**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="67974-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="67974-105">Name</span><span class="sxs-lookup"><span data-stu-id="67974-105">Name</span></span>

<span data-ttu-id="67974-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="67974-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="67974-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="67974-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="67974-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67974-108">Description</span></span>

<span data-ttu-id="67974-109">Il `dotnet new` comando crea un progetto .NET Core o altri artefatti in base a un modello.</span><span class="sxs-lookup"><span data-stu-id="67974-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="67974-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="67974-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="67974-111">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="67974-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="67974-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="67974-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="67974-113">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="67974-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="67974-114">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="67974-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="67974-115">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="67974-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="67974-116">È possibile eseguire `dotnet new --list` o `dotnet new -l` per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="67974-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="67974-117">Se il `TEMPLATE` valore non corrisponde esattamente al testo presente nella colonna **modelli** o **nome breve** della tabella restituita, viene eseguita una corrispondenza della sottostringa su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="67974-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="67974-118">A partire da .NET Core 3,0 SDK, l'interfaccia della riga di comando Cerca i modelli in `dotnet new` NuGet.org quando si richiama il comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="67974-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="67974-119">Se l'interfaccia della riga di comando non riesce a trovare `dotnet new`una corrispondenza del modello durante la chiamata, non anche parziale.</span><span class="sxs-lookup"><span data-stu-id="67974-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="67974-120">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="67974-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="67974-121">In questo caso, il progetto o l'artefatto viene creato, ma l'interfaccia della riga di comando segnala una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="67974-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="67974-122">Nella tabella seguente sono illustrati i modelli preinstallati con la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="67974-123">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="67974-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="67974-124">Fare clic sul collegamento nome breve per visualizzare le opzioni specifiche del modello.</span><span class="sxs-lookup"><span data-stu-id="67974-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="67974-125">Modelli</span><span class="sxs-lookup"><span data-stu-id="67974-125">Templates</span></span>                                    | <span data-ttu-id="67974-126">Nome breve</span><span class="sxs-lookup"><span data-stu-id="67974-126">Short name</span></span>                      | <span data-ttu-id="67974-127">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="67974-127">Language</span></span>     | <span data-ttu-id="67974-128">Tag</span><span class="sxs-lookup"><span data-stu-id="67974-128">Tags</span></span>                                  | <span data-ttu-id="67974-129">Introdotte</span><span class="sxs-lookup"><span data-stu-id="67974-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="67974-130">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="67974-130">Console Application</span></span>                          | [<span data-ttu-id="67974-131">Console</span><span class="sxs-lookup"><span data-stu-id="67974-131">console</span></span>](#console)             | <span data-ttu-id="67974-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="67974-132">[C#], F#, VB</span></span> | <span data-ttu-id="67974-133">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="67974-133">Common/Console</span></span>                        | <span data-ttu-id="67974-134">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-134">1.0</span></span>        |
| <span data-ttu-id="67974-135">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="67974-135">Class library</span></span>                                | [<span data-ttu-id="67974-136">classlib</span><span class="sxs-lookup"><span data-stu-id="67974-136">classlib</span></span>](#classlib)           | <span data-ttu-id="67974-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="67974-137">[C#], F#, VB</span></span> | <span data-ttu-id="67974-138">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="67974-138">Common/Library</span></span>                        | <span data-ttu-id="67974-139">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-139">1.0</span></span>        |
| <span data-ttu-id="67974-140">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="67974-140">WPF Application</span></span>                              | [<span data-ttu-id="67974-141">WPF</span><span class="sxs-lookup"><span data-stu-id="67974-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="67974-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-142">[C#]</span></span>         | <span data-ttu-id="67974-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="67974-143">Common/WPF</span></span>                            | <span data-ttu-id="67974-144">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-144">3.0</span></span>        |
| <span data-ttu-id="67974-145">Libreria di classi WPF</span><span class="sxs-lookup"><span data-stu-id="67974-145">WPF Class library</span></span>                            | [<span data-ttu-id="67974-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="67974-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="67974-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-147">[C#]</span></span>         | <span data-ttu-id="67974-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="67974-148">Common/WPF</span></span>                            | <span data-ttu-id="67974-149">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-149">3.0</span></span>        |
| <span data-ttu-id="67974-150">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="67974-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="67974-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="67974-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="67974-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-152">[C#]</span></span>         | <span data-ttu-id="67974-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="67974-153">Common/WPF</span></span>                            | <span data-ttu-id="67974-154">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-154">3.0</span></span>        |
| <span data-ttu-id="67974-155">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="67974-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="67974-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="67974-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="67974-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-157">[C#]</span></span>         | <span data-ttu-id="67974-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="67974-158">Common/WPF</span></span>                            | <span data-ttu-id="67974-159">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-159">3.0</span></span>        |
| <span data-ttu-id="67974-160">Applicazione Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="67974-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="67974-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="67974-161">winforms</span></span>](#winforms)           | <span data-ttu-id="67974-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-162">[C#]</span></span>         | <span data-ttu-id="67974-163">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="67974-163">Common/WinForms</span></span>                       | <span data-ttu-id="67974-164">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-164">3.0</span></span>        |
| <span data-ttu-id="67974-165">Libreria di classi Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="67974-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="67974-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="67974-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="67974-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-167">[C#]</span></span>         | <span data-ttu-id="67974-168">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="67974-168">Common/WinForms</span></span>                       | <span data-ttu-id="67974-169">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-169">3.0</span></span>        |
| <span data-ttu-id="67974-170">Servizio ruolo di lavoro</span><span class="sxs-lookup"><span data-stu-id="67974-170">Worker Service</span></span>                               | [<span data-ttu-id="67974-171">lavoro</span><span class="sxs-lookup"><span data-stu-id="67974-171">worker</span></span>](#web-others)           | <span data-ttu-id="67974-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-172">[C#]</span></span>         | <span data-ttu-id="67974-173">Comune/di lavoro/Web</span><span class="sxs-lookup"><span data-stu-id="67974-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="67974-174">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-174">3.0</span></span>        |
| <span data-ttu-id="67974-175">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="67974-175">Unit Test Project</span></span>                            | [<span data-ttu-id="67974-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="67974-176">mstest</span></span>](#test)                 | <span data-ttu-id="67974-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="67974-177">[C#], F#, VB</span></span> | <span data-ttu-id="67974-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="67974-178">Test/MSTest</span></span>                           | <span data-ttu-id="67974-179">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-179">1.0</span></span>        |
| <span data-ttu-id="67974-180">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="67974-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="67974-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="67974-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="67974-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="67974-182">[C#], F#, VB</span></span> | <span data-ttu-id="67974-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="67974-183">Test/NUnit</span></span>                            | <span data-ttu-id="67974-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="67974-184">2.1.400</span></span>    |
| <span data-ttu-id="67974-185">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="67974-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="67974-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="67974-186">[C#], F#, VB</span></span> | <span data-ttu-id="67974-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="67974-187">Test/NUnit</span></span>                            | <span data-ttu-id="67974-188">2.2</span><span class="sxs-lookup"><span data-stu-id="67974-188">2.2</span></span>        |
| <span data-ttu-id="67974-189">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="67974-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="67974-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="67974-190">xunit</span></span>](#test)                  | <span data-ttu-id="67974-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="67974-191">[C#], F#, VB</span></span> | <span data-ttu-id="67974-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="67974-192">Test/xUnit</span></span>                            | <span data-ttu-id="67974-193">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-193">1.0</span></span>        |
| <span data-ttu-id="67974-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="67974-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="67974-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-195">[C#]</span></span>         | <span data-ttu-id="67974-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="67974-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="67974-197">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-197">3.0</span></span>        |
| <span data-ttu-id="67974-198">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="67974-198">Razor Page</span></span>                                   | [<span data-ttu-id="67974-199">pagina</span><span class="sxs-lookup"><span data-stu-id="67974-199">page</span></span>](#page)                   | <span data-ttu-id="67974-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-200">[C#]</span></span>         | <span data-ttu-id="67974-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="67974-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="67974-202">2.0</span><span class="sxs-lookup"><span data-stu-id="67974-202">2.0</span></span>        |
| <span data-ttu-id="67974-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="67974-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="67974-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="67974-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="67974-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-205">[C#]</span></span>         | <span data-ttu-id="67974-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="67974-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="67974-207">2.0</span><span class="sxs-lookup"><span data-stu-id="67974-207">2.0</span></span>        |
| <span data-ttu-id="67974-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="67974-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="67974-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-209">[C#]</span></span>         | <span data-ttu-id="67974-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="67974-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="67974-211">2.0</span><span class="sxs-lookup"><span data-stu-id="67974-211">2.0</span></span>        |
| <span data-ttu-id="67974-212">App Server Blazer</span><span class="sxs-lookup"><span data-stu-id="67974-212">Blazor Server App</span></span>                            | [<span data-ttu-id="67974-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="67974-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="67974-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-214">[C#]</span></span>         | <span data-ttu-id="67974-215">Web/Blazer</span><span class="sxs-lookup"><span data-stu-id="67974-215">Web/Blazor</span></span>                            | <span data-ttu-id="67974-216">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-216">3.0</span></span>        |
| <span data-ttu-id="67974-217">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="67974-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="67974-218">Web</span><span class="sxs-lookup"><span data-stu-id="67974-218">web</span></span>](#web)                     | <span data-ttu-id="67974-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="67974-219">[C#], F#</span></span>     | <span data-ttu-id="67974-220">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="67974-220">Web/Empty</span></span>                             | <span data-ttu-id="67974-221">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-221">1.0</span></span>        |
| <span data-ttu-id="67974-222">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="67974-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="67974-223">MVC</span><span class="sxs-lookup"><span data-stu-id="67974-223">mvc</span></span>](#web-options)             | <span data-ttu-id="67974-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="67974-224">[C#], F#</span></span>     | <span data-ttu-id="67974-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="67974-225">Web/MVC</span></span>                               | <span data-ttu-id="67974-226">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-226">1.0</span></span>        |
| <span data-ttu-id="67974-227">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="67974-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="67974-228">WebApp, Razor</span><span class="sxs-lookup"><span data-stu-id="67974-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="67974-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-229">[C#]</span></span>         | <span data-ttu-id="67974-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="67974-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="67974-231">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="67974-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="67974-232">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="67974-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="67974-233">angolare</span><span class="sxs-lookup"><span data-stu-id="67974-233">angular</span></span>](#spa)                 | <span data-ttu-id="67974-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-234">[C#]</span></span>         | <span data-ttu-id="67974-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="67974-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="67974-236">2.0</span><span class="sxs-lookup"><span data-stu-id="67974-236">2.0</span></span>        |
| <span data-ttu-id="67974-237">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="67974-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="67974-238">React</span><span class="sxs-lookup"><span data-stu-id="67974-238">react</span></span>](#spa)                   | <span data-ttu-id="67974-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-239">[C#]</span></span>         | <span data-ttu-id="67974-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="67974-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="67974-241">2.0</span><span class="sxs-lookup"><span data-stu-id="67974-241">2.0</span></span>        |
| <span data-ttu-id="67974-242">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="67974-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="67974-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="67974-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="67974-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-244">[C#]</span></span>         | <span data-ttu-id="67974-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="67974-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="67974-246">2.0</span><span class="sxs-lookup"><span data-stu-id="67974-246">2.0</span></span>        |
| <span data-ttu-id="67974-247">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="67974-247">Razor Class Library</span></span>                          | [<span data-ttu-id="67974-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="67974-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="67974-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-249">[C#]</span></span>         | <span data-ttu-id="67974-250">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="67974-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="67974-251">2.1</span><span class="sxs-lookup"><span data-stu-id="67974-251">2.1</span></span>        |
| <span data-ttu-id="67974-252">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="67974-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="67974-253">WebAPI</span><span class="sxs-lookup"><span data-stu-id="67974-253">webapi</span></span>](#webapi)               | <span data-ttu-id="67974-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="67974-254">[C#], F#</span></span>     | <span data-ttu-id="67974-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="67974-255">Web/WebAPI</span></span>                            | <span data-ttu-id="67974-256">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-256">1.0</span></span>        |
| <span data-ttu-id="67974-257">Servizio ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="67974-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="67974-258">grpc</span><span class="sxs-lookup"><span data-stu-id="67974-258">grpc</span></span>](#web-others)             | <span data-ttu-id="67974-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="67974-259">[C#]</span></span>         | <span data-ttu-id="67974-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="67974-260">Web/gRPC</span></span>                              | <span data-ttu-id="67974-261">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-261">3.0</span></span>        |
| <span data-ttu-id="67974-262">file gitignore DotNet</span><span class="sxs-lookup"><span data-stu-id="67974-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="67974-263">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="67974-263">Config</span></span>                                | <span data-ttu-id="67974-264">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-264">3.0</span></span>        |
| <span data-ttu-id="67974-265">File global.json</span><span class="sxs-lookup"><span data-stu-id="67974-265">global.json file</span></span>                             | [<span data-ttu-id="67974-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="67974-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="67974-267">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="67974-267">Config</span></span>                                | <span data-ttu-id="67974-268">2.0</span><span class="sxs-lookup"><span data-stu-id="67974-268">2.0</span></span>        |
| <span data-ttu-id="67974-269">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="67974-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="67974-270">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="67974-270">Config</span></span>                                | <span data-ttu-id="67974-271">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-271">1.0</span></span>        |
| <span data-ttu-id="67974-272">File manifesto dello strumento locale DotNet</span><span class="sxs-lookup"><span data-stu-id="67974-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="67974-273">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="67974-273">Config</span></span>                                | <span data-ttu-id="67974-274">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-274">3.0</span></span>        |
| <span data-ttu-id="67974-275">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="67974-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="67974-276">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="67974-276">Config</span></span>                                | <span data-ttu-id="67974-277">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-277">1.0</span></span>        |
| <span data-ttu-id="67974-278">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="67974-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="67974-279">Soluzione</span><span class="sxs-lookup"><span data-stu-id="67974-279">Solution</span></span>                              | <span data-ttu-id="67974-280">1.0</span><span class="sxs-lookup"><span data-stu-id="67974-280">1.0</span></span>        |
| <span data-ttu-id="67974-281">File buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="67974-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="67974-282">proto</span><span class="sxs-lookup"><span data-stu-id="67974-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="67974-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="67974-283">Web/gRPC</span></span>                              | <span data-ttu-id="67974-284">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="67974-285">Opzioni</span><span class="sxs-lookup"><span data-stu-id="67974-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="67974-286">Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.</span><span class="sxs-lookup"><span data-stu-id="67974-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="67974-287">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="67974-288">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="67974-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="67974-289">Questa operazione è necessaria quando il modello scelto sostituisce i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="67974-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="67974-290">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="67974-290">Prints out help for the command.</span></span> <span data-ttu-id="67974-291">Può essere richiamato per il `dotnet new` comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="67974-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="67974-292">Ad esempio: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="67974-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="67974-293">Installa un pacchetto di modelli dall' `PATH` oggetto `NUGET_ID` o fornito.</span><span class="sxs-lookup"><span data-stu-id="67974-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="67974-294">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="67974-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="67974-295">Per impostazione predefinita `dotnet new` , \* passa per la versione, che rappresenta la versione stabile più recente del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="67974-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="67974-296">Vedere un esempio nella sezione degli [esempi](#examples) .</span><span class="sxs-lookup"><span data-stu-id="67974-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="67974-297">Se una versione del modello è già installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente, se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="67974-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="67974-298">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="67974-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="67974-299">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="67974-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="67974-300">Se non viene specificato alcun nome, elenca tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="67974-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="67974-301">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="67974-301">The language of the template to create.</span></span> <span data-ttu-id="67974-302">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="67974-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="67974-303">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="67974-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="67974-304">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="67974-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="67974-305">In questi casi, racchiudere il valore del parametro Language tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="67974-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="67974-306">Ad esempio: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="67974-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="67974-307">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="67974-307">The name for the created output.</span></span> <span data-ttu-id="67974-308">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="67974-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="67974-309">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="67974-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="67974-310">Disponibile a partire da .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="67974-311">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="67974-311">Location to place the generated output.</span></span> <span data-ttu-id="67974-312">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="67974-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="67974-313">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="67974-313">Filters templates based on available types.</span></span> <span data-ttu-id="67974-314">I valori predefiniti sono `project`, `item`e `other`.</span><span class="sxs-lookup"><span data-stu-id="67974-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="67974-315">Disinstalla un pacchetto di modelli in `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="67974-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="67974-316">Quando il `<PATH|NUGET_ID>` valore non è specificato, vengono visualizzati tutti i pacchetti di modelli attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="67974-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="67974-317">Quando si `NUGET_ID`specifica, non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="67974-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="67974-318">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="67974-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="67974-319">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="67974-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="67974-320">Ad esempio, *C:/Users\</User>/Documents/templates/garciasoftware.consoletemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="67974-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="67974-321">Non includere una barra di directory finale terminata nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="67974-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="67974-322">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="67974-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="67974-323">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="67974-324">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="67974-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="67974-325">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="67974-326">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="67974-326">Template options</span></span>

<span data-ttu-id="67974-327">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="67974-327">Each project template may have additional options available.</span></span> <span data-ttu-id="67974-328">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="67974-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="67974-329">console</span><span class="sxs-lookup"><span data-stu-id="67974-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-330">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-331">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="67974-332">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-333">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-333">SDK version</span></span> | <span data-ttu-id="67974-334">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-335">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-336">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="67974-337">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="67974-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="67974-338">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="67974-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="67974-339">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="67974-339">Not supported for F#.</span></span> <span data-ttu-id="67974-340">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="67974-341">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="67974-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-342">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="67974-343">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="67974-344">classlib</span><span class="sxs-lookup"><span data-stu-id="67974-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-345">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-346">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="67974-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="67974-347">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="67974-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="67974-348">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="67974-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="67974-349">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="67974-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="67974-350">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="67974-350">Not supported for F#.</span></span> <span data-ttu-id="67974-351">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="67974-352">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="67974-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-353">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a><span data-ttu-id="67974-354">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="67974-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-355">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-356">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="67974-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="67974-357">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="67974-358">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="67974-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="67974-359">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="67974-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="67974-360">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="67974-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-361">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a><span data-ttu-id="67974-362">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="67974-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="67974-363">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="67974-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="67974-364">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="67974-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="67974-365">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="67974-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-366">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a><span data-ttu-id="67974-367">Worker, grpc</span><span class="sxs-lookup"><span data-stu-id="67974-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-368">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-369">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="67974-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="67974-370">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="67974-371">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="67974-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-372">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="67974-373">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="67974-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-374">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-375">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="67974-376">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-377">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-377">SDK version</span></span> | <span data-ttu-id="67974-378">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-379">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-380">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="67974-381">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="67974-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-382">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="67974-383">NUnit</span><span class="sxs-lookup"><span data-stu-id="67974-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-384">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="67974-385">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-386">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-386">SDK version</span></span> | <span data-ttu-id="67974-387">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-388">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-389">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="67974-390">2.2</span><span class="sxs-lookup"><span data-stu-id="67974-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="67974-391">2.1</span><span class="sxs-lookup"><span data-stu-id="67974-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="67974-392">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="67974-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-393">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="67974-394">pagina</span><span class="sxs-lookup"><span data-stu-id="67974-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="67974-395">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="67974-395">Namespace for the generated code.</span></span> <span data-ttu-id="67974-396">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="67974-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="67974-397">Crea la pagina senza PageModel.</span><span class="sxs-lookup"><span data-stu-id="67974-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a><span data-ttu-id="67974-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="67974-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="67974-399">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="67974-399">Namespace for the generated code.</span></span> <span data-ttu-id="67974-400">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="67974-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="67974-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="67974-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="67974-402">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="67974-402">The type of authentication to use.</span></span> <span data-ttu-id="67974-403">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="67974-403">The possible values are:</span></span>

  - <span data-ttu-id="67974-404">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="67974-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="67974-405">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="67974-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="67974-406">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="67974-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="67974-407">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="67974-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="67974-408">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="67974-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="67974-409">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="67974-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="67974-410">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="67974-411">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-412">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="67974-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="67974-413">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="67974-414">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="67974-415">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="67974-416">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="67974-417">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="67974-418">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="67974-419">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="67974-420">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="67974-421">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="67974-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="67974-422">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-422">The Client ID for this project.</span></span> <span data-ttu-id="67974-423">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="67974-424">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="67974-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="67974-425">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="67974-425">The domain for the directory tenant.</span></span> <span data-ttu-id="67974-426">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-427">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="67974-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="67974-428">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="67974-429">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="67974-430">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="67974-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="67974-431">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="67974-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="67974-432">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-433">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="67974-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="67974-434">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="67974-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="67974-435">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="67974-436">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="67974-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="67974-437">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="67974-437">Turns off HTTPS.</span></span> <span data-ttu-id="67974-438">Questa opzione si applica solo `Individual`se `IndividualB2C`, `SingleOrg`, o `MultiOrg` non vengono utilizzati per `--auth`.</span><span class="sxs-lookup"><span data-stu-id="67974-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="67974-439">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="67974-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="67974-440">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-441">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="67974-442">Web</span><span class="sxs-lookup"><span data-stu-id="67974-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="67974-443">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="67974-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-444">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-445">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="67974-446">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-447">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-447">SDK version</span></span> | <span data-ttu-id="67974-448">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-449">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-450">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="67974-451">2.1</span><span class="sxs-lookup"><span data-stu-id="67974-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="67974-452">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="67974-453">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="67974-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a><span data-ttu-id="67974-454">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="67974-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="67974-455">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="67974-455">The type of authentication to use.</span></span> <span data-ttu-id="67974-456">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="67974-456">The possible values are:</span></span>

  - <span data-ttu-id="67974-457">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="67974-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="67974-458">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="67974-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="67974-459">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="67974-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="67974-460">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="67974-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="67974-461">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="67974-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="67974-462">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="67974-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="67974-463">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="67974-464">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-465">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="67974-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="67974-466">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="67974-467">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="67974-468">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="67974-469">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="67974-470">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="67974-471">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="67974-472">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="67974-473">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="67974-474">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="67974-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="67974-475">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-475">The Client ID for this project.</span></span> <span data-ttu-id="67974-476">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="67974-477">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="67974-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="67974-478">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="67974-478">The domain for the directory tenant.</span></span> <span data-ttu-id="67974-479">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-480">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="67974-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="67974-481">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="67974-482">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="67974-483">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="67974-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="67974-484">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="67974-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="67974-485">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-486">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="67974-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="67974-487">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="67974-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="67974-488">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="67974-489">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="67974-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="67974-490">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="67974-490">Turns off HTTPS.</span></span> <span data-ttu-id="67974-491">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="67974-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="67974-492">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="67974-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="67974-493">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-494">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-495">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="67974-496">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-497">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-497">SDK version</span></span> | <span data-ttu-id="67974-498">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-499">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-500">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="67974-501">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="67974-502">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="67974-503">Opzione non disponibile in .NET Core 2,2 e 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="67974-504">Determina se il progetto è configurato per usare la [compilazione del runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle build di debug.</span><span class="sxs-lookup"><span data-stu-id="67974-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="67974-505">Opzione disponibile a partire da .NET Core 3.1.201 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a><span data-ttu-id="67974-506">angolare, React</span><span class="sxs-lookup"><span data-stu-id="67974-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="67974-507">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="67974-507">The type of authentication to use.</span></span> <span data-ttu-id="67974-508">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="67974-509">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="67974-509">The possible values are:</span></span>

  - <span data-ttu-id="67974-510">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="67974-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="67974-511">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="67974-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="67974-512">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="67974-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-513">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="67974-514">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="67974-514">Turns off HTTPS.</span></span> <span data-ttu-id="67974-515">Questa opzione si applica solo se l' `None`autenticazione è.</span><span class="sxs-lookup"><span data-stu-id="67974-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="67974-516">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="67974-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="67974-517">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-518">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-519">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-520">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="67974-521">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-522">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-522">SDK version</span></span> | <span data-ttu-id="67974-523">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-524">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-525">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="67974-526">2.1</span><span class="sxs-lookup"><span data-stu-id="67974-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="67974-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="67974-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="67974-528">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="67974-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-529">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-530">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="67974-531">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-532">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-532">SDK version</span></span> | <span data-ttu-id="67974-533">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-534">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-535">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="67974-536">2.1</span><span class="sxs-lookup"><span data-stu-id="67974-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="67974-537">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="67974-538">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="67974-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="67974-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="67974-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="67974-540">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="67974-541">Supporta l'aggiunta di pagine e visualizzazioni tradizionali Razor oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="67974-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="67974-542">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="67974-543">webapi</span><span class="sxs-lookup"><span data-stu-id="67974-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="67974-544">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="67974-544">The type of authentication to use.</span></span> <span data-ttu-id="67974-545">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="67974-545">The possible values are:</span></span>

  - <span data-ttu-id="67974-546">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="67974-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="67974-547">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="67974-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="67974-548">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="67974-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="67974-549">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="67974-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="67974-550">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="67974-551">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="67974-552">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="67974-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="67974-553">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="67974-554">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="67974-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="67974-555">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="67974-556">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="67974-557">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="67974-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="67974-558">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-558">The Client ID for this project.</span></span> <span data-ttu-id="67974-559">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="67974-560">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="67974-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="67974-561">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="67974-561">The domain for the directory tenant.</span></span> <span data-ttu-id="67974-562">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="67974-563">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="67974-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="67974-564">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="67974-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="67974-565">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="67974-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="67974-566">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="67974-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="67974-567">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="67974-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="67974-568">Si applica solo `SingleOrg` all'autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="67974-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="67974-569">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="67974-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="67974-570">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="67974-570">Turns off HTTPS.</span></span> <span data-ttu-id="67974-571">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="67974-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="67974-572">Questa opzione si applica solo `IndividualB2C` se `SingleOrg` o non vengono usati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="67974-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="67974-573">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="67974-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="67974-574">Si applica solo `IndividualB2C` all'autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="67974-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67974-575">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="67974-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="67974-576">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="67974-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="67974-577">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="67974-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="67974-578">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="67974-578">SDK version</span></span> | <span data-ttu-id="67974-579">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="67974-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="67974-580">3.1</span><span class="sxs-lookup"><span data-stu-id="67974-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="67974-581">3.0</span><span class="sxs-lookup"><span data-stu-id="67974-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="67974-582">2.1</span><span class="sxs-lookup"><span data-stu-id="67974-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="67974-583">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="67974-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="67974-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="67974-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="67974-585">Specifica la versione del .NET Core SDK da usare nel file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="67974-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="67974-586">Esempi</span><span class="sxs-lookup"><span data-stu-id="67974-586">Examples</span></span>

- <span data-ttu-id="67974-587">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="67974-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="67974-588">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="67974-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="67974-589">Creare un progetto libreria di classi .NET Standard nella directory specificata:</span><span class="sxs-lookup"><span data-stu-id="67974-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="67974-590">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="67974-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="67974-591">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="67974-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="67974-592">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="67974-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="67974-593">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="67974-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="67974-594">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="67974-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="67974-595">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="67974-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="67974-596">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="67974-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="67974-597">Installare la versione 2,0 dei modelli di SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="67974-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="67974-598">Elencare i modelli e i dettagli installati, inclusa la modalità di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="67974-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="67974-599">Creare un file *Global. JSON* nella directory corrente impostando la versione dell'SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="67974-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="67974-600">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67974-600">See also</span></span>

- [<span data-ttu-id="67974-601">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="67974-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="67974-602">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="67974-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="67974-603">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="67974-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="67974-604">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="67974-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
