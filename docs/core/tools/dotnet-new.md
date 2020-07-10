---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
no-loc:
- Blazor
- WebAssembly
ms.date: 04/10/2020
ms.openlocfilehash: ec41b3b79ed5eded7c9124d3e4d95c658ee39580
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173120"
---
# <a name="dotnet-new"></a><span data-ttu-id="1bf3e-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bf3e-103">dotnet new</span></span>

<span data-ttu-id="1bf3e-104">**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1bf3e-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1bf3e-105">Name (Nome)</span><span class="sxs-lookup"><span data-stu-id="1bf3e-105">Name</span></span>

<span data-ttu-id="1bf3e-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1bf3e-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1bf3e-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="1bf3e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-108">Description</span></span>

<span data-ttu-id="1bf3e-109">Il `dotnet new` comando crea un progetto .NET Core o altri artefatti in base a un modello.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="1bf3e-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="1bf3e-111">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="1bf3e-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1bf3e-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="1bf3e-113">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="1bf3e-114">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="1bf3e-115">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="1bf3e-116">È possibile eseguire `dotnet new --list` o `dotnet new -l` per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="1bf3e-117">Se il `TEMPLATE` valore non corrisponde esattamente al testo presente nella colonna **modelli** o **nome breve** della tabella restituita, viene eseguita una corrispondenza della sottostringa su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="1bf3e-118">A partire da .NET Core 3,0 SDK, l'interfaccia della riga di comando Cerca i modelli in NuGet.org quando si richiama il `dotnet new` comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="1bf3e-119">Se l'interfaccia della riga di comando non riesce a trovare una corrispondenza del modello durante la chiamata `dotnet new` , non anche parziale.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="1bf3e-120">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="1bf3e-121">In questo caso, il progetto o l'artefatto viene creato, ma l'interfaccia della riga di comando segnala una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="1bf3e-122">Nella tabella seguente sono illustrati i modelli preinstallati con la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="1bf3e-123">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="1bf3e-124">Fare clic sul collegamento nome breve per visualizzare le opzioni specifiche del modello.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="1bf3e-125">Modelli</span><span class="sxs-lookup"><span data-stu-id="1bf3e-125">Templates</span></span>                                    | <span data-ttu-id="1bf3e-126">Nome breve</span><span class="sxs-lookup"><span data-stu-id="1bf3e-126">Short name</span></span>                      | <span data-ttu-id="1bf3e-127">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="1bf3e-127">Language</span></span>     | <span data-ttu-id="1bf3e-128">Tag</span><span class="sxs-lookup"><span data-stu-id="1bf3e-128">Tags</span></span>                                  | <span data-ttu-id="1bf3e-129">Introdotte</span><span class="sxs-lookup"><span data-stu-id="1bf3e-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="1bf3e-130">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="1bf3e-130">Console Application</span></span>                          | [<span data-ttu-id="1bf3e-131">Console</span><span class="sxs-lookup"><span data-stu-id="1bf3e-131">console</span></span>](#console)             | <span data-ttu-id="1bf3e-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bf3e-132">[C#], F#, VB</span></span> | <span data-ttu-id="1bf3e-133">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="1bf3e-133">Common/Console</span></span>                        | <span data-ttu-id="1bf3e-134">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-134">1.0</span></span>        |
| <span data-ttu-id="1bf3e-135">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="1bf3e-135">Class library</span></span>                                | [<span data-ttu-id="1bf3e-136">classlib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-136">classlib</span></span>](#classlib)           | <span data-ttu-id="1bf3e-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bf3e-137">[C#], F#, VB</span></span> | <span data-ttu-id="1bf3e-138">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="1bf3e-138">Common/Library</span></span>                        | <span data-ttu-id="1bf3e-139">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-139">1.0</span></span>        |
| <span data-ttu-id="1bf3e-140">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-140">WPF Application</span></span>                              | [<span data-ttu-id="1bf3e-141">WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="1bf3e-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-142">[C#]</span></span>         | <span data-ttu-id="1bf3e-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-143">Common/WPF</span></span>                            | <span data-ttu-id="1bf3e-144">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-144">3.0</span></span>        |
| <span data-ttu-id="1bf3e-145">Libreria di classi WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-145">WPF Class library</span></span>                            | [<span data-ttu-id="1bf3e-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="1bf3e-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-147">[C#]</span></span>         | <span data-ttu-id="1bf3e-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-148">Common/WPF</span></span>                            | <span data-ttu-id="1bf3e-149">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-149">3.0</span></span>        |
| <span data-ttu-id="1bf3e-150">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="1bf3e-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="1bf3e-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-152">[C#]</span></span>         | <span data-ttu-id="1bf3e-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-153">Common/WPF</span></span>                            | <span data-ttu-id="1bf3e-154">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-154">3.0</span></span>        |
| <span data-ttu-id="1bf3e-155">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="1bf3e-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="1bf3e-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-157">[C#]</span></span>         | <span data-ttu-id="1bf3e-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="1bf3e-158">Common/WPF</span></span>                            | <span data-ttu-id="1bf3e-159">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-159">3.0</span></span>        |
| <span data-ttu-id="1bf3e-160">Applicazione Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1bf3e-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="1bf3e-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="1bf3e-161">winforms</span></span>](#winforms)           | <span data-ttu-id="1bf3e-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-162">[C#]</span></span>         | <span data-ttu-id="1bf3e-163">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bf3e-163">Common/WinForms</span></span>                       | <span data-ttu-id="1bf3e-164">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-164">3.0</span></span>        |
| <span data-ttu-id="1bf3e-165">Libreria di classi Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="1bf3e-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="1bf3e-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="1bf3e-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-167">[C#]</span></span>         | <span data-ttu-id="1bf3e-168">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="1bf3e-168">Common/WinForms</span></span>                       | <span data-ttu-id="1bf3e-169">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-169">3.0</span></span>        |
| <span data-ttu-id="1bf3e-170">Servizio ruolo di lavoro</span><span class="sxs-lookup"><span data-stu-id="1bf3e-170">Worker Service</span></span>                               | [<span data-ttu-id="1bf3e-171">lavoro</span><span class="sxs-lookup"><span data-stu-id="1bf3e-171">worker</span></span>](#web-others)           | <span data-ttu-id="1bf3e-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-172">[C#]</span></span>         | <span data-ttu-id="1bf3e-173">Comune/di lavoro/Web</span><span class="sxs-lookup"><span data-stu-id="1bf3e-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="1bf3e-174">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-174">3.0</span></span>        |
| <span data-ttu-id="1bf3e-175">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="1bf3e-175">Unit Test Project</span></span>                            | [<span data-ttu-id="1bf3e-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="1bf3e-176">mstest</span></span>](#test)                 | <span data-ttu-id="1bf3e-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bf3e-177">[C#], F#, VB</span></span> | <span data-ttu-id="1bf3e-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="1bf3e-178">Test/MSTest</span></span>                           | <span data-ttu-id="1bf3e-179">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-179">1.0</span></span>        |
| <span data-ttu-id="1bf3e-180">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="1bf3e-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="1bf3e-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="1bf3e-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bf3e-182">[C#], F#, VB</span></span> | <span data-ttu-id="1bf3e-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-183">Test/NUnit</span></span>                            | <span data-ttu-id="1bf3e-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="1bf3e-184">2.1.400</span></span>    |
| <span data-ttu-id="1bf3e-185">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="1bf3e-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="1bf3e-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bf3e-186">[C#], F#, VB</span></span> | <span data-ttu-id="1bf3e-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-187">Test/NUnit</span></span>                            | <span data-ttu-id="1bf3e-188">2.2</span><span class="sxs-lookup"><span data-stu-id="1bf3e-188">2.2</span></span>        |
| <span data-ttu-id="1bf3e-189">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="1bf3e-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-190">xunit</span></span>](#test)                  | <span data-ttu-id="1bf3e-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="1bf3e-191">[C#], F#, VB</span></span> | <span data-ttu-id="1bf3e-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-192">Test/xUnit</span></span>                            | <span data-ttu-id="1bf3e-193">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-193">1.0</span></span>        |
| <span data-ttu-id="1bf3e-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="1bf3e-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="1bf3e-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-195">[C#]</span></span>         | <span data-ttu-id="1bf3e-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bf3e-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bf3e-197">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-197">3.0</span></span>        |
| <span data-ttu-id="1bf3e-198">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="1bf3e-198">Razor Page</span></span>                                   | [<span data-ttu-id="1bf3e-199">pagina</span><span class="sxs-lookup"><span data-stu-id="1bf3e-199">page</span></span>](#page)                   | <span data-ttu-id="1bf3e-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-200">[C#]</span></span>         | <span data-ttu-id="1bf3e-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bf3e-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bf3e-202">2.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-202">2.0</span></span>        |
| <span data-ttu-id="1bf3e-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="1bf3e-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="1bf3e-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="1bf3e-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="1bf3e-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-205">[C#]</span></span>         | <span data-ttu-id="1bf3e-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bf3e-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bf3e-207">2.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-207">2.0</span></span>        |
| <span data-ttu-id="1bf3e-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="1bf3e-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="1bf3e-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-209">[C#]</span></span>         | <span data-ttu-id="1bf3e-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1bf3e-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="1bf3e-211">2.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-211">2.0</span></span>        |
| Blazor<span data-ttu-id="1bf3e-212">App Server</span><span class="sxs-lookup"><span data-stu-id="1bf3e-212"> Server App</span></span>                            | [<span data-ttu-id="1bf3e-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="1bf3e-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="1bf3e-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-214">[C#]</span></span>         | <span data-ttu-id="1bf3e-215">WebBlazor</span><span class="sxs-lookup"><span data-stu-id="1bf3e-215">Web/Blazor</span></span>                            | <span data-ttu-id="1bf3e-216">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-216">3.0</span></span>        |
| Blazor<span data-ttu-id="1bf3e-217">WebAssemblyApp di</span><span class="sxs-lookup"><span data-stu-id="1bf3e-217"> WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="1bf3e-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-218">[C#]</span></span>         | <span data-ttu-id="1bf3e-219">WebBlazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="1bf3e-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="1bf3e-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="1bf3e-220">3.1.300</span></span>    |
| <span data-ttu-id="1bf3e-221">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="1bf3e-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="1bf3e-222">Web</span><span class="sxs-lookup"><span data-stu-id="1bf3e-222">web</span></span>](#web)                     | <span data-ttu-id="1bf3e-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1bf3e-223">[C#], F#</span></span>     | <span data-ttu-id="1bf3e-224">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="1bf3e-224">Web/Empty</span></span>                             | <span data-ttu-id="1bf3e-225">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-225">1.0</span></span>        |
| <span data-ttu-id="1bf3e-226">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="1bf3e-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="1bf3e-227">MVC</span><span class="sxs-lookup"><span data-stu-id="1bf3e-227">mvc</span></span>](#web-options)             | <span data-ttu-id="1bf3e-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1bf3e-228">[C#], F#</span></span>     | <span data-ttu-id="1bf3e-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="1bf3e-229">Web/MVC</span></span>                               | <span data-ttu-id="1bf3e-230">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-230">1.0</span></span>        |
| <span data-ttu-id="1bf3e-231">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1bf3e-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="1bf3e-232">WebApp, Razor</span><span class="sxs-lookup"><span data-stu-id="1bf3e-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="1bf3e-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-233">[C#]</span></span>         | <span data-ttu-id="1bf3e-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="1bf3e-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="1bf3e-235">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="1bf3e-236">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="1bf3e-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="1bf3e-237">angolare</span><span class="sxs-lookup"><span data-stu-id="1bf3e-237">angular</span></span>](#spa)                 | <span data-ttu-id="1bf3e-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-238">[C#]</span></span>         | <span data-ttu-id="1bf3e-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="1bf3e-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1bf3e-240">2.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-240">2.0</span></span>        |
| <span data-ttu-id="1bf3e-241">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="1bf3e-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="1bf3e-242">React</span><span class="sxs-lookup"><span data-stu-id="1bf3e-242">react</span></span>](#spa)                   | <span data-ttu-id="1bf3e-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-243">[C#]</span></span>         | <span data-ttu-id="1bf3e-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="1bf3e-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1bf3e-245">2.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-245">2.0</span></span>        |
| <span data-ttu-id="1bf3e-246">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="1bf3e-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="1bf3e-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="1bf3e-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="1bf3e-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-248">[C#]</span></span>         | <span data-ttu-id="1bf3e-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="1bf3e-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="1bf3e-250">2.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-250">2.0</span></span>        |
| <span data-ttu-id="1bf3e-251">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="1bf3e-251">Razor Class Library</span></span>                          | [<span data-ttu-id="1bf3e-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="1bf3e-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-253">[C#]</span></span>         | <span data-ttu-id="1bf3e-254">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="1bf3e-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="1bf3e-255">2.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-255">2.1</span></span>        |
| <span data-ttu-id="1bf3e-256">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1bf3e-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="1bf3e-257">WebAPI</span><span class="sxs-lookup"><span data-stu-id="1bf3e-257">webapi</span></span>](#webapi)               | <span data-ttu-id="1bf3e-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="1bf3e-258">[C#], F#</span></span>     | <span data-ttu-id="1bf3e-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="1bf3e-259">Web/WebAPI</span></span>                            | <span data-ttu-id="1bf3e-260">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-260">1.0</span></span>        |
| <span data-ttu-id="1bf3e-261">Servizio ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="1bf3e-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="1bf3e-262">grpc</span><span class="sxs-lookup"><span data-stu-id="1bf3e-262">grpc</span></span>](#web-others)             | <span data-ttu-id="1bf3e-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="1bf3e-263">[C#]</span></span>         | <span data-ttu-id="1bf3e-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="1bf3e-264">Web/gRPC</span></span>                              | <span data-ttu-id="1bf3e-265">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-265">3.0</span></span>        |
| <span data-ttu-id="1bf3e-266">file gitignore DotNet</span><span class="sxs-lookup"><span data-stu-id="1bf3e-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="1bf3e-267">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-267">Config</span></span>                                | <span data-ttu-id="1bf3e-268">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-268">3.0</span></span>        |
| <span data-ttu-id="1bf3e-269">File global.json</span><span class="sxs-lookup"><span data-stu-id="1bf3e-269">global.json file</span></span>                             | [<span data-ttu-id="1bf3e-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="1bf3e-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="1bf3e-271">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-271">Config</span></span>                                | <span data-ttu-id="1bf3e-272">2.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-272">2.0</span></span>        |
| <span data-ttu-id="1bf3e-273">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="1bf3e-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="1bf3e-274">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-274">Config</span></span>                                | <span data-ttu-id="1bf3e-275">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-275">1.0</span></span>        |
| <span data-ttu-id="1bf3e-276">File manifesto dello strumento locale DotNet</span><span class="sxs-lookup"><span data-stu-id="1bf3e-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="1bf3e-277">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-277">Config</span></span>                                | <span data-ttu-id="1bf3e-278">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-278">3.0</span></span>        |
| <span data-ttu-id="1bf3e-279">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="1bf3e-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="1bf3e-280">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-280">Config</span></span>                                | <span data-ttu-id="1bf3e-281">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-281">1.0</span></span>        |
| <span data-ttu-id="1bf3e-282">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="1bf3e-283">Soluzione</span><span class="sxs-lookup"><span data-stu-id="1bf3e-283">Solution</span></span>                              | <span data-ttu-id="1bf3e-284">1.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-284">1.0</span></span>        |
| <span data-ttu-id="1bf3e-285">File buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="1bf3e-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="1bf3e-286">proto</span><span class="sxs-lookup"><span data-stu-id="1bf3e-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="1bf3e-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="1bf3e-287">Web/gRPC</span></span>                              | <span data-ttu-id="1bf3e-288">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="1bf3e-289">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1bf3e-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="1bf3e-290">Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="1bf3e-291">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="1bf3e-292">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="1bf3e-293">Questa operazione è necessaria quando il modello scelto sostituisce i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1bf3e-294">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-294">Prints out help for the command.</span></span> <span data-ttu-id="1bf3e-295">Può essere richiamato per il `dotnet new` comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="1bf3e-296">Ad esempio, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="1bf3e-297">Installa un pacchetto di modelli dall'oggetto `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1bf3e-298">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="1bf3e-299">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione stabile più recente del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="1bf3e-300">Vedere un esempio nella sezione degli [esempi](#examples) .</span><span class="sxs-lookup"><span data-stu-id="1bf3e-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="1bf3e-301">Se una versione del modello è già installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente, se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="1bf3e-302">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="1bf3e-303">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="1bf3e-304">Se non viene specificato alcun nome, elenca tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="1bf3e-305">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-305">The language of the template to create.</span></span> <span data-ttu-id="1bf3e-306">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="1bf3e-307">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1bf3e-308">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="1bf3e-309">In questi casi, racchiudere il valore del parametro Language tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="1bf3e-310">Ad esempio, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="1bf3e-311">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-311">The name for the created output.</span></span> <span data-ttu-id="1bf3e-312">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="1bf3e-313">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="1bf3e-314">Disponibile a partire da .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="1bf3e-315">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-315">Location to place the generated output.</span></span> <span data-ttu-id="1bf3e-316">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="1bf3e-317">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-317">Filters templates based on available types.</span></span> <span data-ttu-id="1bf3e-318">I valori predefiniti sono `project` , `item` e `other` .</span><span class="sxs-lookup"><span data-stu-id="1bf3e-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="1bf3e-319">Disinstalla un pacchetto di modelli in `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="1bf3e-320">Quando il `<PATH|NUGET_ID>` valore non è specificato, vengono visualizzati tutti i pacchetti di modelli attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="1bf3e-321">Quando si specifica `NUGET_ID` , non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="1bf3e-322">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1bf3e-323">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="1bf3e-324">Ad esempio, *C:/Users/ \<USER> /Documents/templates/GarciaSoftware.ConsoleTemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="1bf3e-325">Non includere una barra di directory finale terminata nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="1bf3e-326">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="1bf3e-327">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="1bf3e-328">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="1bf3e-329">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="1bf3e-330">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="1bf3e-330">Template options</span></span>

<span data-ttu-id="1bf3e-331">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-331">Each project template may have additional options available.</span></span> <span data-ttu-id="1bf3e-332">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="1bf3e-333">console</span><span class="sxs-lookup"><span data-stu-id="1bf3e-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-334">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-335">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1bf3e-336">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-337">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-337">SDK version</span></span> | <span data-ttu-id="1bf3e-338">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-339">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-340">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bf3e-341">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bf3e-342">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="1bf3e-343">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-343">Not supported for F#.</span></span> <span data-ttu-id="1bf3e-344">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bf3e-345">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-346">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="1bf3e-347">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="1bf3e-348">classlib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-349">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-350">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="1bf3e-351">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bf3e-352">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bf3e-353">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="1bf3e-354">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-354">Not supported for F#.</span></span> <span data-ttu-id="1bf3e-355">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bf3e-356">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-357">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a><span data-ttu-id="1bf3e-358">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-359">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-360">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="1bf3e-361">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bf3e-362">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bf3e-363">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="1bf3e-364">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-365">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a><span data-ttu-id="1bf3e-366">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="1bf3e-367">Imposta la `LangVersion` proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="1bf3e-368">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="1bf3e-369">Per un elenco delle versioni di C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-370">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a><span data-ttu-id="1bf3e-371">Worker, grpc</span><span class="sxs-lookup"><span data-stu-id="1bf3e-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-372">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-373">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="1bf3e-374">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bf3e-375">Esclude *launchSettings.js* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-376">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="1bf3e-377">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-378">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-379">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1bf3e-380">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-381">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-381">SDK version</span></span> | <span data-ttu-id="1bf3e-382">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-383">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-384">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="1bf3e-385">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-386">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="1bf3e-387">NUnit</span><span class="sxs-lookup"><span data-stu-id="1bf3e-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-388">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="1bf3e-389">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-390">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-390">SDK version</span></span> | <span data-ttu-id="1bf3e-391">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-392">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-393">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bf3e-394">2.2</span><span class="sxs-lookup"><span data-stu-id="1bf3e-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="1bf3e-395">2.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="1bf3e-396">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-397">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="1bf3e-398">pagina</span><span class="sxs-lookup"><span data-stu-id="1bf3e-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="1bf3e-399">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-399">Namespace for the generated code.</span></span> <span data-ttu-id="1bf3e-400">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="1bf3e-401">Crea la pagina senza PageModel.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a><span data-ttu-id="1bf3e-402">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="1bf3e-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="1bf3e-403">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-403">Namespace for the generated code.</span></span> <span data-ttu-id="1bf3e-404">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="1bf3e-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="1bf3e-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bf3e-406">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-406">The type of authentication to use.</span></span> <span data-ttu-id="1bf3e-407">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-407">The possible values are:</span></span>

  - <span data-ttu-id="1bf3e-408">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bf3e-409">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="1bf3e-410">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1bf3e-411">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1bf3e-412">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="1bf3e-413">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1bf3e-414">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1bf3e-415">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-416">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1bf3e-417">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1bf3e-418">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="1bf3e-419">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="1bf3e-420">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="1bf3e-421">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="1bf3e-422">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1bf3e-423">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1bf3e-424">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bf3e-425">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1bf3e-426">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-426">The Client ID for this project.</span></span> <span data-ttu-id="1bf3e-427">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bf3e-428">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1bf3e-429">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-429">The domain for the directory tenant.</span></span> <span data-ttu-id="1bf3e-430">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-431">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1bf3e-432">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1bf3e-433">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bf3e-434">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="1bf3e-435">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1bf3e-436">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-437">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1bf3e-438">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1bf3e-439">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bf3e-440">Esclude *launchSettings.js* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bf3e-441">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-441">Turns off HTTPS.</span></span> <span data-ttu-id="1bf3e-442">Questa opzione si applica solo se `Individual` ,, `IndividualB2C` `SingleOrg` o `MultiOrg` non vengono utilizzati per `--auth` .</span><span class="sxs-lookup"><span data-stu-id="1bf3e-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bf3e-443">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bf3e-444">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-445">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="1bf3e-446">Web</span><span class="sxs-lookup"><span data-stu-id="1bf3e-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bf3e-447">Esclude *launchSettings.js* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-448">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-449">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bf3e-450">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-451">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-451">SDK version</span></span> | <span data-ttu-id="1bf3e-452">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-453">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-454">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bf3e-455">2.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="1bf3e-456">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bf3e-457">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a><span data-ttu-id="1bf3e-458">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="1bf3e-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bf3e-459">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-459">The type of authentication to use.</span></span> <span data-ttu-id="1bf3e-460">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-460">The possible values are:</span></span>

  - <span data-ttu-id="1bf3e-461">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bf3e-462">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="1bf3e-463">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1bf3e-464">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1bf3e-465">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="1bf3e-466">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1bf3e-467">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1bf3e-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-469">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1bf3e-470">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1bf3e-471">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="1bf3e-472">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="1bf3e-473">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="1bf3e-474">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="1bf3e-475">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1bf3e-476">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1bf3e-477">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bf3e-478">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1bf3e-479">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-479">The Client ID for this project.</span></span> <span data-ttu-id="1bf3e-480">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="1bf3e-481">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1bf3e-482">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-482">The domain for the directory tenant.</span></span> <span data-ttu-id="1bf3e-483">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-484">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1bf3e-485">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1bf3e-486">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bf3e-487">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="1bf3e-488">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="1bf3e-489">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-490">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1bf3e-491">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1bf3e-492">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bf3e-493">Esclude *launchSettings.js* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bf3e-494">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-494">Turns off HTTPS.</span></span> <span data-ttu-id="1bf3e-495">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bf3e-496">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bf3e-497">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-498">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-499">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="1bf3e-500">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-501">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-501">SDK version</span></span> | <span data-ttu-id="1bf3e-502">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-503">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-504">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="1bf3e-505">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="1bf3e-506">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="1bf3e-507">Opzione non disponibile in .NET Core 2,2 e 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="1bf3e-508">Determina se il progetto è configurato per usare la [compilazione del runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle build di debug.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="1bf3e-509">Opzione disponibile a partire da .NET Core 3.1.201 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a><span data-ttu-id="1bf3e-510">angolare, React</span><span class="sxs-lookup"><span data-stu-id="1bf3e-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bf3e-511">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-511">The type of authentication to use.</span></span> <span data-ttu-id="1bf3e-512">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="1bf3e-513">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-513">The possible values are:</span></span>

  - <span data-ttu-id="1bf3e-514">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bf3e-515">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bf3e-516">Esclude *launchSettings.js* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-517">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bf3e-518">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-518">Turns off HTTPS.</span></span> <span data-ttu-id="1bf3e-519">Questa opzione si applica solo se l'autenticazione è `None` .</span><span class="sxs-lookup"><span data-stu-id="1bf3e-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bf3e-520">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bf3e-521">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-522">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-523">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-524">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bf3e-525">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-526">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-526">SDK version</span></span> | <span data-ttu-id="1bf3e-527">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-528">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-529">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bf3e-530">2.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="1bf3e-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="1bf3e-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bf3e-532">Esclude *launchSettings.js* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-533">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-534">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bf3e-535">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-536">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-536">SDK version</span></span> | <span data-ttu-id="1bf3e-537">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-538">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-539">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bf3e-540">2.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="1bf3e-541">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bf3e-542">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="1bf3e-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="1bf3e-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="1bf3e-544">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="1bf3e-545">Supporta l'aggiunta di pagine e visualizzazioni tradizionali Razor oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="1bf3e-546">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="1bf3e-547">webapi</span><span class="sxs-lookup"><span data-stu-id="1bf3e-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="1bf3e-548">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-548">The type of authentication to use.</span></span> <span data-ttu-id="1bf3e-549">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-549">The possible values are:</span></span>

  - <span data-ttu-id="1bf3e-550">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="1bf3e-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="1bf3e-551">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="1bf3e-552">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="1bf3e-553">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="1bf3e-554">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="1bf3e-555">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="1bf3e-556">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="1bf3e-557">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="1bf3e-558">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="1bf3e-559">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="1bf3e-560">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bf3e-561">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="1bf3e-562">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-562">The Client ID for this project.</span></span> <span data-ttu-id="1bf3e-563">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1bf3e-564">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="1bf3e-565">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-565">The domain for the directory tenant.</span></span> <span data-ttu-id="1bf3e-566">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="1bf3e-567">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="1bf3e-568">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="1bf3e-569">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="1bf3e-570">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="1bf3e-571">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="1bf3e-572">Si applica solo all' `SingleOrg` autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="1bf3e-573">Esclude *launchSettings.js* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="1bf3e-574">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-574">Turns off HTTPS.</span></span> <span data-ttu-id="1bf3e-575">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="1bf3e-576">Questa opzione si applica solo se `IndividualB2C` o `SingleOrg` non vengono usati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="1bf3e-577">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="1bf3e-578">Si applica solo all' `IndividualB2C` autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1bf3e-579">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="1bf3e-580">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="1bf3e-581">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="1bf3e-582">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="1bf3e-582">SDK version</span></span> | <span data-ttu-id="1bf3e-583">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1bf3e-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="1bf3e-584">3.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="1bf3e-585">3.0</span><span class="sxs-lookup"><span data-stu-id="1bf3e-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="1bf3e-586">2.1</span><span class="sxs-lookup"><span data-stu-id="1bf3e-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="1bf3e-587">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="1bf3e-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="1bf3e-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="1bf3e-589">Specifica la versione del .NET Core SDK da utilizzare nell' *global.jssul* file.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="1bf3e-590">Esempi</span><span class="sxs-lookup"><span data-stu-id="1bf3e-590">Examples</span></span>

- <span data-ttu-id="1bf3e-591">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="1bf3e-592">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="1bf3e-593">Creare un progetto libreria di classi .NET Standard nella directory specificata:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="1bf3e-594">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="1bf3e-595">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="1bf3e-596">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="1bf3e-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="1bf3e-597">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="1bf3e-598">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="1bf3e-599">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="1bf3e-600">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="1bf3e-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="1bf3e-601">Installare la versione 2,0 dei modelli di SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="1bf3e-602">Elencare i modelli e i dettagli installati, inclusa la modalità di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="1bf3e-603">Creare una *global.js* nella directory corrente impostando la versione dell'SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="1bf3e-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="1bf3e-604">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bf3e-604">See also</span></span>

- [<span data-ttu-id="1bf3e-605">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bf3e-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="1bf3e-606">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bf3e-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="1bf3e-607">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="1bf3e-607">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="1bf3e-608">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="1bf3e-608">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
