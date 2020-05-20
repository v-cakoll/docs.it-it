---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 04/10/2020
ms.openlocfilehash: 1544f519f2a5f6a1a6e042c1db720eff45f5d98c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442241"
---
# <a name="dotnet-new"></a><span data-ttu-id="53466-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="53466-103">dotnet new</span></span>

<span data-ttu-id="53466-104">**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="53466-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="53466-105">Nome</span><span class="sxs-lookup"><span data-stu-id="53466-105">Name</span></span>

<span data-ttu-id="53466-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="53466-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="53466-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="53466-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="53466-108">Description</span><span class="sxs-lookup"><span data-stu-id="53466-108">Description</span></span>

<span data-ttu-id="53466-109">Il `dotnet new` comando crea un progetto .NET Core o altri artefatti in base a un modello.</span><span class="sxs-lookup"><span data-stu-id="53466-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="53466-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="53466-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="53466-111">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="53466-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="53466-112">Arguments</span><span class="sxs-lookup"><span data-stu-id="53466-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="53466-113">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="53466-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="53466-114">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="53466-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="53466-115">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="53466-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="53466-116">È possibile eseguire `dotnet new --list` o `dotnet new -l` per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="53466-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="53466-117">Se il `TEMPLATE` valore non corrisponde esattamente al testo presente nella colonna **modelli** o **nome breve** della tabella restituita, viene eseguita una corrispondenza della sottostringa su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="53466-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="53466-118">A partire da .NET Core 3,0 SDK, l'interfaccia della riga di comando Cerca i modelli in NuGet.org quando si richiama il `dotnet new` comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="53466-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="53466-119">Se l'interfaccia della riga di comando non riesce a trovare una corrispondenza del modello durante la chiamata `dotnet new` , non anche parziale.</span><span class="sxs-lookup"><span data-stu-id="53466-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="53466-120">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="53466-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="53466-121">In questo caso, il progetto o l'artefatto viene creato, ma l'interfaccia della riga di comando segnala una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="53466-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="53466-122">Nella tabella seguente sono illustrati i modelli preinstallati con la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="53466-123">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="53466-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="53466-124">Fare clic sul collegamento nome breve per visualizzare le opzioni specifiche del modello.</span><span class="sxs-lookup"><span data-stu-id="53466-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="53466-125">Modelli</span><span class="sxs-lookup"><span data-stu-id="53466-125">Templates</span></span>                                    | <span data-ttu-id="53466-126">Nome breve</span><span class="sxs-lookup"><span data-stu-id="53466-126">Short name</span></span>                      | <span data-ttu-id="53466-127">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="53466-127">Language</span></span>     | <span data-ttu-id="53466-128">Tag</span><span class="sxs-lookup"><span data-stu-id="53466-128">Tags</span></span>                                  | <span data-ttu-id="53466-129">Introdotte</span><span class="sxs-lookup"><span data-stu-id="53466-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="53466-130">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="53466-130">Console Application</span></span>                          | [<span data-ttu-id="53466-131">Console</span><span class="sxs-lookup"><span data-stu-id="53466-131">console</span></span>](#console)             | <span data-ttu-id="53466-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="53466-132">[C#], F#, VB</span></span> | <span data-ttu-id="53466-133">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="53466-133">Common/Console</span></span>                        | <span data-ttu-id="53466-134">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-134">1.0</span></span>        |
| <span data-ttu-id="53466-135">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="53466-135">Class library</span></span>                                | [<span data-ttu-id="53466-136">classlib</span><span class="sxs-lookup"><span data-stu-id="53466-136">classlib</span></span>](#classlib)           | <span data-ttu-id="53466-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="53466-137">[C#], F#, VB</span></span> | <span data-ttu-id="53466-138">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="53466-138">Common/Library</span></span>                        | <span data-ttu-id="53466-139">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-139">1.0</span></span>        |
| <span data-ttu-id="53466-140">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="53466-140">WPF Application</span></span>                              | [<span data-ttu-id="53466-141">WPF</span><span class="sxs-lookup"><span data-stu-id="53466-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="53466-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-142">[C#]</span></span>         | <span data-ttu-id="53466-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="53466-143">Common/WPF</span></span>                            | <span data-ttu-id="53466-144">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-144">3.0</span></span>        |
| <span data-ttu-id="53466-145">Libreria di classi WPF</span><span class="sxs-lookup"><span data-stu-id="53466-145">WPF Class library</span></span>                            | [<span data-ttu-id="53466-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="53466-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="53466-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-147">[C#]</span></span>         | <span data-ttu-id="53466-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="53466-148">Common/WPF</span></span>                            | <span data-ttu-id="53466-149">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-149">3.0</span></span>        |
| <span data-ttu-id="53466-150">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="53466-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="53466-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="53466-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="53466-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-152">[C#]</span></span>         | <span data-ttu-id="53466-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="53466-153">Common/WPF</span></span>                            | <span data-ttu-id="53466-154">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-154">3.0</span></span>        |
| <span data-ttu-id="53466-155">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="53466-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="53466-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="53466-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="53466-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-157">[C#]</span></span>         | <span data-ttu-id="53466-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="53466-158">Common/WPF</span></span>                            | <span data-ttu-id="53466-159">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-159">3.0</span></span>        |
| <span data-ttu-id="53466-160">Applicazione Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="53466-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="53466-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="53466-161">winforms</span></span>](#winforms)           | <span data-ttu-id="53466-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-162">[C#]</span></span>         | <span data-ttu-id="53466-163">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="53466-163">Common/WinForms</span></span>                       | <span data-ttu-id="53466-164">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-164">3.0</span></span>        |
| <span data-ttu-id="53466-165">Libreria di classi Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="53466-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="53466-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="53466-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="53466-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-167">[C#]</span></span>         | <span data-ttu-id="53466-168">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="53466-168">Common/WinForms</span></span>                       | <span data-ttu-id="53466-169">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-169">3.0</span></span>        |
| <span data-ttu-id="53466-170">Servizio ruolo di lavoro</span><span class="sxs-lookup"><span data-stu-id="53466-170">Worker Service</span></span>                               | [<span data-ttu-id="53466-171">lavoro</span><span class="sxs-lookup"><span data-stu-id="53466-171">worker</span></span>](#web-others)           | <span data-ttu-id="53466-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-172">[C#]</span></span>         | <span data-ttu-id="53466-173">Comune/di lavoro/Web</span><span class="sxs-lookup"><span data-stu-id="53466-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="53466-174">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-174">3.0</span></span>        |
| <span data-ttu-id="53466-175">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="53466-175">Unit Test Project</span></span>                            | [<span data-ttu-id="53466-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="53466-176">mstest</span></span>](#test)                 | <span data-ttu-id="53466-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="53466-177">[C#], F#, VB</span></span> | <span data-ttu-id="53466-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="53466-178">Test/MSTest</span></span>                           | <span data-ttu-id="53466-179">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-179">1.0</span></span>        |
| <span data-ttu-id="53466-180">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="53466-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="53466-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="53466-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="53466-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="53466-182">[C#], F#, VB</span></span> | <span data-ttu-id="53466-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="53466-183">Test/NUnit</span></span>                            | <span data-ttu-id="53466-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="53466-184">2.1.400</span></span>    |
| <span data-ttu-id="53466-185">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="53466-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="53466-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="53466-186">[C#], F#, VB</span></span> | <span data-ttu-id="53466-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="53466-187">Test/NUnit</span></span>                            | <span data-ttu-id="53466-188">2.2</span><span class="sxs-lookup"><span data-stu-id="53466-188">2.2</span></span>        |
| <span data-ttu-id="53466-189">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="53466-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="53466-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="53466-190">xunit</span></span>](#test)                  | <span data-ttu-id="53466-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="53466-191">[C#], F#, VB</span></span> | <span data-ttu-id="53466-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="53466-192">Test/xUnit</span></span>                            | <span data-ttu-id="53466-193">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-193">1.0</span></span>        |
| <span data-ttu-id="53466-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="53466-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="53466-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-195">[C#]</span></span>         | <span data-ttu-id="53466-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="53466-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="53466-197">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-197">3.0</span></span>        |
| <span data-ttu-id="53466-198">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="53466-198">Razor Page</span></span>                                   | [<span data-ttu-id="53466-199">pagina</span><span class="sxs-lookup"><span data-stu-id="53466-199">page</span></span>](#page)                   | <span data-ttu-id="53466-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-200">[C#]</span></span>         | <span data-ttu-id="53466-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="53466-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="53466-202">2.0</span><span class="sxs-lookup"><span data-stu-id="53466-202">2.0</span></span>        |
| <span data-ttu-id="53466-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="53466-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="53466-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="53466-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="53466-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-205">[C#]</span></span>         | <span data-ttu-id="53466-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="53466-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="53466-207">2.0</span><span class="sxs-lookup"><span data-stu-id="53466-207">2.0</span></span>        |
| <span data-ttu-id="53466-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="53466-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="53466-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-209">[C#]</span></span>         | <span data-ttu-id="53466-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="53466-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="53466-211">2.0</span><span class="sxs-lookup"><span data-stu-id="53466-211">2.0</span></span>        |
| <span data-ttu-id="53466-212">App Server Blazer</span><span class="sxs-lookup"><span data-stu-id="53466-212">Blazor Server App</span></span>                            | [<span data-ttu-id="53466-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="53466-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="53466-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-214">[C#]</span></span>         | <span data-ttu-id="53466-215">Web/Blazer</span><span class="sxs-lookup"><span data-stu-id="53466-215">Web/Blazor</span></span>                            | <span data-ttu-id="53466-216">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-216">3.0</span></span>        |
| <span data-ttu-id="53466-217">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="53466-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="53466-218">Web</span><span class="sxs-lookup"><span data-stu-id="53466-218">web</span></span>](#web)                     | <span data-ttu-id="53466-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="53466-219">[C#], F#</span></span>     | <span data-ttu-id="53466-220">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="53466-220">Web/Empty</span></span>                             | <span data-ttu-id="53466-221">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-221">1.0</span></span>        |
| <span data-ttu-id="53466-222">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="53466-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="53466-223">MVC</span><span class="sxs-lookup"><span data-stu-id="53466-223">mvc</span></span>](#web-options)             | <span data-ttu-id="53466-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="53466-224">[C#], F#</span></span>     | <span data-ttu-id="53466-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="53466-225">Web/MVC</span></span>                               | <span data-ttu-id="53466-226">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-226">1.0</span></span>        |
| <span data-ttu-id="53466-227">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="53466-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="53466-228">WebApp, Razor</span><span class="sxs-lookup"><span data-stu-id="53466-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="53466-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-229">[C#]</span></span>         | <span data-ttu-id="53466-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="53466-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="53466-231">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="53466-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="53466-232">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="53466-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="53466-233">angolare</span><span class="sxs-lookup"><span data-stu-id="53466-233">angular</span></span>](#spa)                 | <span data-ttu-id="53466-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-234">[C#]</span></span>         | <span data-ttu-id="53466-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="53466-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="53466-236">2.0</span><span class="sxs-lookup"><span data-stu-id="53466-236">2.0</span></span>        |
| <span data-ttu-id="53466-237">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="53466-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="53466-238">React</span><span class="sxs-lookup"><span data-stu-id="53466-238">react</span></span>](#spa)                   | <span data-ttu-id="53466-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-239">[C#]</span></span>         | <span data-ttu-id="53466-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="53466-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="53466-241">2.0</span><span class="sxs-lookup"><span data-stu-id="53466-241">2.0</span></span>        |
| <span data-ttu-id="53466-242">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="53466-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="53466-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="53466-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="53466-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-244">[C#]</span></span>         | <span data-ttu-id="53466-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="53466-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="53466-246">2.0</span><span class="sxs-lookup"><span data-stu-id="53466-246">2.0</span></span>        |
| <span data-ttu-id="53466-247">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="53466-247">Razor Class Library</span></span>                          | [<span data-ttu-id="53466-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="53466-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="53466-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-249">[C#]</span></span>         | <span data-ttu-id="53466-250">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="53466-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="53466-251">2.1</span><span class="sxs-lookup"><span data-stu-id="53466-251">2.1</span></span>        |
| <span data-ttu-id="53466-252">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="53466-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="53466-253">WebAPI</span><span class="sxs-lookup"><span data-stu-id="53466-253">webapi</span></span>](#webapi)               | <span data-ttu-id="53466-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="53466-254">[C#], F#</span></span>     | <span data-ttu-id="53466-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="53466-255">Web/WebAPI</span></span>                            | <span data-ttu-id="53466-256">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-256">1.0</span></span>        |
| <span data-ttu-id="53466-257">Servizio ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="53466-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="53466-258">grpc</span><span class="sxs-lookup"><span data-stu-id="53466-258">grpc</span></span>](#web-others)             | <span data-ttu-id="53466-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="53466-259">[C#]</span></span>         | <span data-ttu-id="53466-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="53466-260">Web/gRPC</span></span>                              | <span data-ttu-id="53466-261">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-261">3.0</span></span>        |
| <span data-ttu-id="53466-262">file gitignore DotNet</span><span class="sxs-lookup"><span data-stu-id="53466-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="53466-263">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="53466-263">Config</span></span>                                | <span data-ttu-id="53466-264">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-264">3.0</span></span>        |
| <span data-ttu-id="53466-265">File global.json</span><span class="sxs-lookup"><span data-stu-id="53466-265">global.json file</span></span>                             | [<span data-ttu-id="53466-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="53466-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="53466-267">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="53466-267">Config</span></span>                                | <span data-ttu-id="53466-268">2.0</span><span class="sxs-lookup"><span data-stu-id="53466-268">2.0</span></span>        |
| <span data-ttu-id="53466-269">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="53466-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="53466-270">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="53466-270">Config</span></span>                                | <span data-ttu-id="53466-271">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-271">1.0</span></span>        |
| <span data-ttu-id="53466-272">File manifesto dello strumento locale DotNet</span><span class="sxs-lookup"><span data-stu-id="53466-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="53466-273">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="53466-273">Config</span></span>                                | <span data-ttu-id="53466-274">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-274">3.0</span></span>        |
| <span data-ttu-id="53466-275">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="53466-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="53466-276">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="53466-276">Config</span></span>                                | <span data-ttu-id="53466-277">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-277">1.0</span></span>        |
| <span data-ttu-id="53466-278">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="53466-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="53466-279">Soluzione</span><span class="sxs-lookup"><span data-stu-id="53466-279">Solution</span></span>                              | <span data-ttu-id="53466-280">1.0</span><span class="sxs-lookup"><span data-stu-id="53466-280">1.0</span></span>        |
| <span data-ttu-id="53466-281">File buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="53466-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="53466-282">proto</span><span class="sxs-lookup"><span data-stu-id="53466-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="53466-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="53466-283">Web/gRPC</span></span>                              | <span data-ttu-id="53466-284">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="53466-285">Opzioni</span><span class="sxs-lookup"><span data-stu-id="53466-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="53466-286">Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.</span><span class="sxs-lookup"><span data-stu-id="53466-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="53466-287">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="53466-288">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="53466-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="53466-289">Questa operazione è necessaria quando il modello scelto sostituisce i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="53466-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="53466-290">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="53466-290">Prints out help for the command.</span></span> <span data-ttu-id="53466-291">Può essere richiamato per il `dotnet new` comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="53466-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="53466-292">Ad esempio: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="53466-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="53466-293">Installa un pacchetto di modelli dall'oggetto `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="53466-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="53466-294">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="53466-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="53466-295">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione stabile più recente del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="53466-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="53466-296">Vedere un esempio nella sezione degli [esempi](#examples) .</span><span class="sxs-lookup"><span data-stu-id="53466-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="53466-297">Se una versione del modello è già installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente, se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="53466-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="53466-298">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="53466-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="53466-299">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="53466-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="53466-300">Se non viene specificato alcun nome, elenca tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="53466-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="53466-301">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="53466-301">The language of the template to create.</span></span> <span data-ttu-id="53466-302">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="53466-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="53466-303">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="53466-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="53466-304">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="53466-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="53466-305">In questi casi, racchiudere il valore del parametro Language tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="53466-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="53466-306">Ad esempio: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="53466-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="53466-307">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="53466-307">The name for the created output.</span></span> <span data-ttu-id="53466-308">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="53466-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="53466-309">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="53466-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="53466-310">Disponibile a partire da .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="53466-311">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="53466-311">Location to place the generated output.</span></span> <span data-ttu-id="53466-312">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="53466-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="53466-313">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="53466-313">Filters templates based on available types.</span></span> <span data-ttu-id="53466-314">I valori predefiniti sono `project` , `item` e `other` .</span><span class="sxs-lookup"><span data-stu-id="53466-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="53466-315">Disinstalla un pacchetto di modelli in `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="53466-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="53466-316">Quando il `<PATH|NUGET_ID>` valore non è specificato, vengono visualizzati tutti i pacchetti di modelli attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="53466-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="53466-317">Quando si specifica `NUGET_ID` , non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="53466-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="53466-318">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="53466-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="53466-319">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="53466-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="53466-320">Ad esempio, *C:/Users/ \< User>/Documents/templates/garciasoftware.consoletemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="53466-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="53466-321">Non includere una barra di directory finale terminata nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="53466-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="53466-322">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="53466-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="53466-323">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="53466-324">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="53466-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="53466-325">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="53466-326">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="53466-326">Template options</span></span>

<span data-ttu-id="53466-327">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="53466-327">Each project template may have additional options available.</span></span> <span data-ttu-id="53466-328">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="53466-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="53466-329">console</span><span class="sxs-lookup"><span data-stu-id="53466-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-330">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-331">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="53466-332">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-333">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-333">SDK version</span></span> | <span data-ttu-id="53466-334">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-335">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-336">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="53466-337">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="53466-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="53466-338">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="53466-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="53466-339">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="53466-339">Not supported for F#.</span></span> <span data-ttu-id="53466-340">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="53466-341">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="53466-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-342">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="53466-343">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="53466-344">classlib</span><span class="sxs-lookup"><span data-stu-id="53466-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-345">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-346">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="53466-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="53466-347">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="53466-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="53466-348">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="53466-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="53466-349">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="53466-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="53466-350">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="53466-350">Not supported for F#.</span></span> <span data-ttu-id="53466-351">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="53466-352">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="53466-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-353">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a><span data-ttu-id="53466-354">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="53466-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-355">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-356">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="53466-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="53466-357">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="53466-358">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="53466-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="53466-359">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="53466-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="53466-360">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="53466-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-361">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a><span data-ttu-id="53466-362">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="53466-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="53466-363">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="53466-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="53466-364">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="53466-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="53466-365">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="53466-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-366">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a><span data-ttu-id="53466-367">Worker, grpc</span><span class="sxs-lookup"><span data-stu-id="53466-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-368">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-369">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="53466-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="53466-370">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="53466-371">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="53466-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-372">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="53466-373">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="53466-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-374">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-375">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="53466-376">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-377">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-377">SDK version</span></span> | <span data-ttu-id="53466-378">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-379">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-380">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="53466-381">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="53466-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-382">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="53466-383">NUnit</span><span class="sxs-lookup"><span data-stu-id="53466-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-384">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="53466-385">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-386">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-386">SDK version</span></span> | <span data-ttu-id="53466-387">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-388">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-389">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="53466-390">2.2</span><span class="sxs-lookup"><span data-stu-id="53466-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="53466-391">2.1</span><span class="sxs-lookup"><span data-stu-id="53466-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="53466-392">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="53466-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-393">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="53466-394">pagina</span><span class="sxs-lookup"><span data-stu-id="53466-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="53466-395">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="53466-395">Namespace for the generated code.</span></span> <span data-ttu-id="53466-396">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="53466-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="53466-397">Crea la pagina senza PageModel.</span><span class="sxs-lookup"><span data-stu-id="53466-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a><span data-ttu-id="53466-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="53466-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="53466-399">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="53466-399">Namespace for the generated code.</span></span> <span data-ttu-id="53466-400">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="53466-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="53466-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="53466-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="53466-402">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="53466-402">The type of authentication to use.</span></span> <span data-ttu-id="53466-403">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="53466-403">The possible values are:</span></span>

  - <span data-ttu-id="53466-404">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="53466-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="53466-405">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="53466-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="53466-406">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="53466-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="53466-407">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="53466-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="53466-408">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="53466-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="53466-409">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="53466-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="53466-410">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="53466-411">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-412">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="53466-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="53466-413">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="53466-414">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="53466-415">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="53466-416">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="53466-417">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="53466-418">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="53466-419">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="53466-420">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="53466-421">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="53466-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="53466-422">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-422">The Client ID for this project.</span></span> <span data-ttu-id="53466-423">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="53466-424">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="53466-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="53466-425">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="53466-425">The domain for the directory tenant.</span></span> <span data-ttu-id="53466-426">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-427">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="53466-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="53466-428">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="53466-429">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="53466-430">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="53466-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="53466-431">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="53466-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="53466-432">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-433">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="53466-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="53466-434">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="53466-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="53466-435">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="53466-436">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="53466-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="53466-437">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="53466-437">Turns off HTTPS.</span></span> <span data-ttu-id="53466-438">Questa opzione si applica solo se `Individual` ,, `IndividualB2C` `SingleOrg` o `MultiOrg` non vengono utilizzati per `--auth` .</span><span class="sxs-lookup"><span data-stu-id="53466-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="53466-439">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="53466-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="53466-440">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-441">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="53466-442">Web</span><span class="sxs-lookup"><span data-stu-id="53466-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="53466-443">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="53466-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-444">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-445">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="53466-446">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-447">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-447">SDK version</span></span> | <span data-ttu-id="53466-448">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-449">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-450">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="53466-451">2.1</span><span class="sxs-lookup"><span data-stu-id="53466-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="53466-452">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="53466-453">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="53466-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a><span data-ttu-id="53466-454">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="53466-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="53466-455">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="53466-455">The type of authentication to use.</span></span> <span data-ttu-id="53466-456">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="53466-456">The possible values are:</span></span>

  - <span data-ttu-id="53466-457">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="53466-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="53466-458">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="53466-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="53466-459">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="53466-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="53466-460">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="53466-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="53466-461">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="53466-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="53466-462">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="53466-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="53466-463">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="53466-464">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-465">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="53466-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="53466-466">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="53466-467">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="53466-468">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="53466-469">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="53466-470">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="53466-471">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="53466-472">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="53466-473">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="53466-474">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="53466-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="53466-475">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-475">The Client ID for this project.</span></span> <span data-ttu-id="53466-476">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="53466-477">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="53466-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="53466-478">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="53466-478">The domain for the directory tenant.</span></span> <span data-ttu-id="53466-479">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-480">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="53466-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="53466-481">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="53466-482">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="53466-483">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="53466-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="53466-484">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="53466-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="53466-485">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-486">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="53466-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="53466-487">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="53466-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="53466-488">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="53466-489">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="53466-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="53466-490">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="53466-490">Turns off HTTPS.</span></span> <span data-ttu-id="53466-491">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="53466-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="53466-492">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="53466-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="53466-493">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-494">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-495">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="53466-496">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-497">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-497">SDK version</span></span> | <span data-ttu-id="53466-498">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-499">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-500">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="53466-501">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="53466-502">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="53466-503">Opzione non disponibile in .NET Core 2,2 e 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="53466-504">Determina se il progetto è configurato per usare la [compilazione del runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle build di debug.</span><span class="sxs-lookup"><span data-stu-id="53466-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="53466-505">Opzione disponibile a partire da .NET Core 3.1.201 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a><span data-ttu-id="53466-506">angolare, React</span><span class="sxs-lookup"><span data-stu-id="53466-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="53466-507">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="53466-507">The type of authentication to use.</span></span> <span data-ttu-id="53466-508">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="53466-509">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="53466-509">The possible values are:</span></span>

  - <span data-ttu-id="53466-510">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="53466-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="53466-511">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="53466-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="53466-512">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="53466-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-513">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="53466-514">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="53466-514">Turns off HTTPS.</span></span> <span data-ttu-id="53466-515">Questa opzione si applica solo se l'autenticazione è `None` .</span><span class="sxs-lookup"><span data-stu-id="53466-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="53466-516">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="53466-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="53466-517">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-518">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-519">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-520">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="53466-521">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-522">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-522">SDK version</span></span> | <span data-ttu-id="53466-523">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-524">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-525">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="53466-526">2.1</span><span class="sxs-lookup"><span data-stu-id="53466-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="53466-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="53466-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="53466-528">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="53466-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-529">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-530">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="53466-531">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-532">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-532">SDK version</span></span> | <span data-ttu-id="53466-533">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-534">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-535">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="53466-536">2.1</span><span class="sxs-lookup"><span data-stu-id="53466-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="53466-537">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="53466-538">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="53466-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="53466-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="53466-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="53466-540">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="53466-541">Supporta l'aggiunta di pagine e visualizzazioni tradizionali Razor oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="53466-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="53466-542">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="53466-543">webapi</span><span class="sxs-lookup"><span data-stu-id="53466-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="53466-544">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="53466-544">The type of authentication to use.</span></span> <span data-ttu-id="53466-545">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="53466-545">The possible values are:</span></span>

  - <span data-ttu-id="53466-546">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="53466-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="53466-547">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="53466-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="53466-548">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="53466-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="53466-549">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="53466-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="53466-550">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="53466-551">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="53466-552">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="53466-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="53466-553">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="53466-554">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="53466-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="53466-555">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="53466-556">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="53466-557">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="53466-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="53466-558">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-558">The Client ID for this project.</span></span> <span data-ttu-id="53466-559">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="53466-560">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="53466-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="53466-561">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="53466-561">The domain for the directory tenant.</span></span> <span data-ttu-id="53466-562">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="53466-563">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="53466-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="53466-564">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="53466-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="53466-565">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="53466-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="53466-566">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="53466-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="53466-567">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="53466-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="53466-568">Si applica solo all' `SingleOrg` autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="53466-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="53466-569">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="53466-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="53466-570">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="53466-570">Turns off HTTPS.</span></span> <span data-ttu-id="53466-571">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="53466-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="53466-572">Questa opzione si applica solo se `IndividualB2C` o `SingleOrg` non vengono usati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="53466-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="53466-573">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="53466-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="53466-574">Si applica solo all' `IndividualB2C` autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="53466-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="53466-575">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53466-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="53466-576">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="53466-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="53466-577">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="53466-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="53466-578">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="53466-578">SDK version</span></span> | <span data-ttu-id="53466-579">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="53466-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="53466-580">3.1</span><span class="sxs-lookup"><span data-stu-id="53466-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="53466-581">3.0</span><span class="sxs-lookup"><span data-stu-id="53466-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="53466-582">2.1</span><span class="sxs-lookup"><span data-stu-id="53466-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="53466-583">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="53466-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="53466-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="53466-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="53466-585">Specifica la versione del .NET Core SDK da usare nel file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="53466-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="53466-586">Esempi</span><span class="sxs-lookup"><span data-stu-id="53466-586">Examples</span></span>

- <span data-ttu-id="53466-587">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="53466-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="53466-588">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="53466-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="53466-589">Creare un progetto libreria di classi .NET Standard nella directory specificata:</span><span class="sxs-lookup"><span data-stu-id="53466-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="53466-590">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="53466-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="53466-591">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="53466-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="53466-592">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="53466-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="53466-593">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="53466-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="53466-594">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="53466-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="53466-595">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="53466-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="53466-596">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="53466-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="53466-597">Installare la versione 2,0 dei modelli di SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="53466-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="53466-598">Elencare i modelli e i dettagli installati, inclusa la modalità di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="53466-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="53466-599">Creare un file *Global. JSON* nella directory corrente impostando la versione dell'SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="53466-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="53466-600">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53466-600">See also</span></span>

- [<span data-ttu-id="53466-601">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="53466-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="53466-602">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="53466-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="53466-603">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="53466-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="53466-604">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="53466-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
