---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 04/10/2020
ms.openlocfilehash: 1979f98a6005a414acc64c5eaa086a88aca9f033
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102827"
---
# <a name="dotnet-new"></a><span data-ttu-id="805fd-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="805fd-103">dotnet new</span></span>

<span data-ttu-id="805fd-104">**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="805fd-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="805fd-105">Nome</span><span class="sxs-lookup"><span data-stu-id="805fd-105">Name</span></span>

<span data-ttu-id="805fd-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="805fd-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="805fd-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="805fd-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="805fd-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="805fd-108">Description</span></span>

<span data-ttu-id="805fd-109">Il `dotnet new` comando crea un progetto .NET Core o altri elementi basati su un modello.</span><span class="sxs-lookup"><span data-stu-id="805fd-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="805fd-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="805fd-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="805fd-111">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="805fd-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="805fd-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="805fd-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="805fd-113">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="805fd-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="805fd-114">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="805fd-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="805fd-115">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="805fd-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="805fd-116">È possibile `dotnet new --list` eseguire per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="805fd-116">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="805fd-117">Se `TEMPLATE` il valore non corrisponde esattamente al testo nella colonna **Templates** o **Short Name** della tabella restituita, viene eseguita una corrispondenza di sottostringhe su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="805fd-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="805fd-118">A partire da .NET Core 3.0 SDK, l'interfaccia `dotnet new` della riga di comando cerca i modelli in NuGet.org quando si richiama il comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="805fd-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="805fd-119">Se l'interfaccia della riga di comando `dotnet new`non riesce a trovare una corrispondenza del modello quando si richiama , nemmeno parziale.</span><span class="sxs-lookup"><span data-stu-id="805fd-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="805fd-120">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="805fd-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="805fd-121">In questo caso, il progetto o l'elemento viene creato, ma l'interfaccia della riga di comando avvisa l'utente di una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="805fd-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="805fd-122">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="805fd-122">The command contains a default list of templates.</span></span> <span data-ttu-id="805fd-123">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="805fd-123">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="805fd-124">Nella tabella seguente vengono illustrati i modelli preinstallati con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-124">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="805fd-125">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="805fd-125">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="805fd-126">Fare clic sul collegamento del nome breve per visualizzare le opzioni del modello specifico.</span><span class="sxs-lookup"><span data-stu-id="805fd-126">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="805fd-127">Modelli</span><span class="sxs-lookup"><span data-stu-id="805fd-127">Templates</span></span>                                    | <span data-ttu-id="805fd-128">Nome breve</span><span class="sxs-lookup"><span data-stu-id="805fd-128">Short name</span></span>                      | <span data-ttu-id="805fd-129">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="805fd-129">Language</span></span>     | <span data-ttu-id="805fd-130">Tag</span><span class="sxs-lookup"><span data-stu-id="805fd-130">Tags</span></span>                                  | <span data-ttu-id="805fd-131">Presentare</span><span class="sxs-lookup"><span data-stu-id="805fd-131">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="805fd-132">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="805fd-132">Console Application</span></span>                          | [<span data-ttu-id="805fd-133">Console</span><span class="sxs-lookup"><span data-stu-id="805fd-133">console</span></span>](#console)             | <span data-ttu-id="805fd-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="805fd-134">[C#], F#, VB</span></span> | <span data-ttu-id="805fd-135">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="805fd-135">Common/Console</span></span>                        | <span data-ttu-id="805fd-136">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-136">1.0</span></span>        |
| <span data-ttu-id="805fd-137">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="805fd-137">Class library</span></span>                                | [<span data-ttu-id="805fd-138">classlib</span><span class="sxs-lookup"><span data-stu-id="805fd-138">classlib</span></span>](#classlib)           | <span data-ttu-id="805fd-139">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="805fd-139">[C#], F#, VB</span></span> | <span data-ttu-id="805fd-140">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="805fd-140">Common/Library</span></span>                        | <span data-ttu-id="805fd-141">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-141">1.0</span></span>        |
| <span data-ttu-id="805fd-142">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="805fd-142">WPF Application</span></span>                              | [<span data-ttu-id="805fd-143">Wpf</span><span class="sxs-lookup"><span data-stu-id="805fd-143">wpf</span></span>](#wpf)                     | <span data-ttu-id="805fd-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-144">[C#]</span></span>         | <span data-ttu-id="805fd-145">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="805fd-145">Common/WPF</span></span>                            | <span data-ttu-id="805fd-146">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-146">3.0</span></span>        |
| <span data-ttu-id="805fd-147">Libreria di classi WPFWPF Class library</span><span class="sxs-lookup"><span data-stu-id="805fd-147">WPF Class library</span></span>                            | [<span data-ttu-id="805fd-148">wpflib (libreria)</span><span class="sxs-lookup"><span data-stu-id="805fd-148">wpflib</span></span>](#wpf)                  | <span data-ttu-id="805fd-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-149">[C#]</span></span>         | <span data-ttu-id="805fd-150">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="805fd-150">Common/WPF</span></span>                            | <span data-ttu-id="805fd-151">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-151">3.0</span></span>        |
| <span data-ttu-id="805fd-152">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="805fd-152">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="805fd-153">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="805fd-153">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="805fd-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-154">[C#]</span></span>         | <span data-ttu-id="805fd-155">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="805fd-155">Common/WPF</span></span>                            | <span data-ttu-id="805fd-156">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-156">3.0</span></span>        |
| <span data-ttu-id="805fd-157">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="805fd-157">WPF User Control Library</span></span>                     | [<span data-ttu-id="805fd-158">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="805fd-158">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="805fd-159">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-159">[C#]</span></span>         | <span data-ttu-id="805fd-160">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="805fd-160">Common/WPF</span></span>                            | <span data-ttu-id="805fd-161">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-161">3.0</span></span>        |
| <span data-ttu-id="805fd-162">Applicazione Windows Form (WinForms)</span><span class="sxs-lookup"><span data-stu-id="805fd-162">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="805fd-163">Winforms</span><span class="sxs-lookup"><span data-stu-id="805fd-163">winforms</span></span>](#winforms)           | <span data-ttu-id="805fd-164">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-164">[C#]</span></span>         | <span data-ttu-id="805fd-165">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="805fd-165">Common/WinForms</span></span>                       | <span data-ttu-id="805fd-166">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-166">3.0</span></span>        |
| <span data-ttu-id="805fd-167">Libreria di classi Windows Form (WindowsForms)</span><span class="sxs-lookup"><span data-stu-id="805fd-167">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="805fd-168">winformslib</span><span class="sxs-lookup"><span data-stu-id="805fd-168">winformslib</span></span>](#winforms)        | <span data-ttu-id="805fd-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-169">[C#]</span></span>         | <span data-ttu-id="805fd-170">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="805fd-170">Common/WinForms</span></span>                       | <span data-ttu-id="805fd-171">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-171">3.0</span></span>        |
| <span data-ttu-id="805fd-172">Servizio di lavoro</span><span class="sxs-lookup"><span data-stu-id="805fd-172">Worker Service</span></span>                               | [<span data-ttu-id="805fd-173">Lavoratore</span><span class="sxs-lookup"><span data-stu-id="805fd-173">worker</span></span>](#web-others)           | <span data-ttu-id="805fd-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-174">[C#]</span></span>         | <span data-ttu-id="805fd-175">Comune/Lavoratore/Web</span><span class="sxs-lookup"><span data-stu-id="805fd-175">Common/Worker/Web</span></span>                     | <span data-ttu-id="805fd-176">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-176">3.0</span></span>        |
| <span data-ttu-id="805fd-177">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="805fd-177">Unit Test Project</span></span>                            | [<span data-ttu-id="805fd-178">Mstest</span><span class="sxs-lookup"><span data-stu-id="805fd-178">mstest</span></span>](#test)                 | <span data-ttu-id="805fd-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="805fd-179">[C#], F#, VB</span></span> | <span data-ttu-id="805fd-180">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="805fd-180">Test/MSTest</span></span>                           | <span data-ttu-id="805fd-181">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-181">1.0</span></span>        |
| <span data-ttu-id="805fd-182">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="805fd-182">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="805fd-183">Nunit</span><span class="sxs-lookup"><span data-stu-id="805fd-183">nunit</span></span>](#nunit)                  | <span data-ttu-id="805fd-184">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="805fd-184">[C#], F#, VB</span></span> | <span data-ttu-id="805fd-185">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="805fd-185">Test/NUnit</span></span>                            | <span data-ttu-id="805fd-186">2.1.400</span><span class="sxs-lookup"><span data-stu-id="805fd-186">2.1.400</span></span>    |
| <span data-ttu-id="805fd-187">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="805fd-187">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="805fd-188">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="805fd-188">[C#], F#, VB</span></span> | <span data-ttu-id="805fd-189">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="805fd-189">Test/NUnit</span></span>                            | <span data-ttu-id="805fd-190">2.2</span><span class="sxs-lookup"><span data-stu-id="805fd-190">2.2</span></span>        |
| <span data-ttu-id="805fd-191">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="805fd-191">xUnit Test Project</span></span>                           | [<span data-ttu-id="805fd-192">xunit</span><span class="sxs-lookup"><span data-stu-id="805fd-192">xunit</span></span>](#test)                  | <span data-ttu-id="805fd-193">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="805fd-193">[C#], F#, VB</span></span> | <span data-ttu-id="805fd-194">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="805fd-194">Test/xUnit</span></span>                            | <span data-ttu-id="805fd-195">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-195">1.0</span></span>        |
| <span data-ttu-id="805fd-196">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="805fd-196">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="805fd-197">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-197">[C#]</span></span>         | <span data-ttu-id="805fd-198">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="805fd-198">Web/ASP.NET</span></span>                           | <span data-ttu-id="805fd-199">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-199">3.0</span></span>        |
| <span data-ttu-id="805fd-200">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="805fd-200">Razor Page</span></span>                                   | [<span data-ttu-id="805fd-201">Pagina</span><span class="sxs-lookup"><span data-stu-id="805fd-201">page</span></span>](#page)                   | <span data-ttu-id="805fd-202">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-202">[C#]</span></span>         | <span data-ttu-id="805fd-203">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="805fd-203">Web/ASP.NET</span></span>                           | <span data-ttu-id="805fd-204">2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-204">2.0</span></span>        |
| <span data-ttu-id="805fd-205">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="805fd-205">MVC ViewImports</span></span>                              | [<span data-ttu-id="805fd-206">viewimports</span><span class="sxs-lookup"><span data-stu-id="805fd-206">viewimports</span></span>](#namespace)       | <span data-ttu-id="805fd-207">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-207">[C#]</span></span>         | <span data-ttu-id="805fd-208">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="805fd-208">Web/ASP.NET</span></span>                           | <span data-ttu-id="805fd-209">2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-209">2.0</span></span>        |
| <span data-ttu-id="805fd-210">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="805fd-210">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="805fd-211">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-211">[C#]</span></span>         | <span data-ttu-id="805fd-212">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="805fd-212">Web/ASP.NET</span></span>                           | <span data-ttu-id="805fd-213">2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-213">2.0</span></span>        |
| <span data-ttu-id="805fd-214">Blazor Server App</span><span class="sxs-lookup"><span data-stu-id="805fd-214">Blazor Server App</span></span>                            | [<span data-ttu-id="805fd-215">blazorservere</span><span class="sxs-lookup"><span data-stu-id="805fd-215">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="805fd-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-216">[C#]</span></span>         | <span data-ttu-id="805fd-217">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="805fd-217">Web/Blazor</span></span>                            | <span data-ttu-id="805fd-218">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-218">3.0</span></span>        |
| <span data-ttu-id="805fd-219">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="805fd-219">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="805fd-220">Web</span><span class="sxs-lookup"><span data-stu-id="805fd-220">web</span></span>](#web)                     | <span data-ttu-id="805fd-221">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="805fd-221">[C#], F#</span></span>     | <span data-ttu-id="805fd-222">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="805fd-222">Web/Empty</span></span>                             | <span data-ttu-id="805fd-223">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-223">1.0</span></span>        |
| <span data-ttu-id="805fd-224">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="805fd-224">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="805fd-225">Mvc</span><span class="sxs-lookup"><span data-stu-id="805fd-225">mvc</span></span>](#web-options)             | <span data-ttu-id="805fd-226">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="805fd-226">[C#], F#</span></span>     | <span data-ttu-id="805fd-227">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="805fd-227">Web/MVC</span></span>                               | <span data-ttu-id="805fd-228">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-228">1.0</span></span>        |
| <span data-ttu-id="805fd-229">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="805fd-229">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="805fd-230">webapp, rasoio</span><span class="sxs-lookup"><span data-stu-id="805fd-230">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="805fd-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-231">[C#]</span></span>         | <span data-ttu-id="805fd-232">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="805fd-232">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="805fd-233">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-233">2.2, 2.0</span></span>   |
| <span data-ttu-id="805fd-234">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="805fd-234">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="805fd-235">Angolare</span><span class="sxs-lookup"><span data-stu-id="805fd-235">angular</span></span>](#spa)                 | <span data-ttu-id="805fd-236">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-236">[C#]</span></span>         | <span data-ttu-id="805fd-237">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="805fd-237">Web/MVC/SPA</span></span>                           | <span data-ttu-id="805fd-238">2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-238">2.0</span></span>        |
| <span data-ttu-id="805fd-239">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="805fd-239">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="805fd-240">Reagire</span><span class="sxs-lookup"><span data-stu-id="805fd-240">react</span></span>](#spa)                   | <span data-ttu-id="805fd-241">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-241">[C#]</span></span>         | <span data-ttu-id="805fd-242">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="805fd-242">Web/MVC/SPA</span></span>                           | <span data-ttu-id="805fd-243">2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-243">2.0</span></span>        |
| <span data-ttu-id="805fd-244">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="805fd-244">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="805fd-245">reactredux</span><span class="sxs-lookup"><span data-stu-id="805fd-245">reactredux</span></span>](#reactredux)       | <span data-ttu-id="805fd-246">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-246">[C#]</span></span>         | <span data-ttu-id="805fd-247">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="805fd-247">Web/MVC/SPA</span></span>                           | <span data-ttu-id="805fd-248">2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-248">2.0</span></span>        |
| <span data-ttu-id="805fd-249">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="805fd-249">Razor Class Library</span></span>                          | [<span data-ttu-id="805fd-250">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="805fd-250">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="805fd-251">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-251">[C#]</span></span>         | <span data-ttu-id="805fd-252">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="805fd-252">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="805fd-253">2.1</span><span class="sxs-lookup"><span data-stu-id="805fd-253">2.1</span></span>        |
| <span data-ttu-id="805fd-254">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="805fd-254">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="805fd-255">webapi</span><span class="sxs-lookup"><span data-stu-id="805fd-255">webapi</span></span>](#webapi)               | <span data-ttu-id="805fd-256">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="805fd-256">[C#], F#</span></span>     | <span data-ttu-id="805fd-257">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="805fd-257">Web/WebAPI</span></span>                            | <span data-ttu-id="805fd-258">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-258">1.0</span></span>        |
| <span data-ttu-id="805fd-259">ASP.NET core del servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="805fd-259">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="805fd-260">grpc</span><span class="sxs-lookup"><span data-stu-id="805fd-260">grpc</span></span>](#web-others)             | <span data-ttu-id="805fd-261">[C#]</span><span class="sxs-lookup"><span data-stu-id="805fd-261">[C#]</span></span>         | <span data-ttu-id="805fd-262">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="805fd-262">Web/gRPC</span></span>                              | <span data-ttu-id="805fd-263">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-263">3.0</span></span>        |
| <span data-ttu-id="805fd-264">File buffer protocollo</span><span class="sxs-lookup"><span data-stu-id="805fd-264">Protocol Buffer File</span></span>                         | [<span data-ttu-id="805fd-265">Proto</span><span class="sxs-lookup"><span data-stu-id="805fd-265">proto</span></span>](#namespace)             |              | <span data-ttu-id="805fd-266">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="805fd-266">Web/gRPC</span></span>                              | <span data-ttu-id="805fd-267">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-267">3.0</span></span>        |
| <span data-ttu-id="805fd-268">file gitignore dotnet</span><span class="sxs-lookup"><span data-stu-id="805fd-268">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="805fd-269">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="805fd-269">Config</span></span>                                | <span data-ttu-id="805fd-270">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-270">3.0</span></span>        |
| <span data-ttu-id="805fd-271">File global.json</span><span class="sxs-lookup"><span data-stu-id="805fd-271">global.json file</span></span>                             | [<span data-ttu-id="805fd-272">globaljson</span><span class="sxs-lookup"><span data-stu-id="805fd-272">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="805fd-273">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="805fd-273">Config</span></span>                                | <span data-ttu-id="805fd-274">2.0</span><span class="sxs-lookup"><span data-stu-id="805fd-274">2.0</span></span>        |
| <span data-ttu-id="805fd-275">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="805fd-275">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="805fd-276">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="805fd-276">Config</span></span>                                | <span data-ttu-id="805fd-277">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-277">1.0</span></span>        |
| <span data-ttu-id="805fd-278">dotnet file manifesto dello strumento locale</span><span class="sxs-lookup"><span data-stu-id="805fd-278">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="805fd-279">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="805fd-279">Config</span></span>                                | <span data-ttu-id="805fd-280">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-280">3.0</span></span>        |
| <span data-ttu-id="805fd-281">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="805fd-281">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="805fd-282">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="805fd-282">Config</span></span>                                | <span data-ttu-id="805fd-283">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-283">1.0</span></span>        |
| <span data-ttu-id="805fd-284">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="805fd-284">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="805fd-285">Soluzione</span><span class="sxs-lookup"><span data-stu-id="805fd-285">Solution</span></span>                              | <span data-ttu-id="805fd-286">1.0</span><span class="sxs-lookup"><span data-stu-id="805fd-286">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="805fd-287">Opzioni</span><span class="sxs-lookup"><span data-stu-id="805fd-287">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="805fd-288">Visualizza un riepilogo di ciò che accadrebbe se il comando specificato venisse eseguito.</span><span class="sxs-lookup"><span data-stu-id="805fd-288">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="805fd-289">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-289">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="805fd-290">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="805fd-290">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="805fd-291">Questa operazione è necessaria quando il modello scelto sovrascriverà i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="805fd-291">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="805fd-292">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="805fd-292">Prints out help for the command.</span></span> <span data-ttu-id="805fd-293">Può essere richiamato `dotnet new` per il comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="805fd-293">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="805fd-294">Ad esempio: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="805fd-294">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="805fd-295">Installa un pacchetto di `PATH` `NUGET_ID` modelli da o fornito.</span><span class="sxs-lookup"><span data-stu-id="805fd-295">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="805fd-296">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="805fd-296">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="805fd-297">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione del pacchetto stabile più recente.</span><span class="sxs-lookup"><span data-stu-id="805fd-297">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="805fd-298">Vedere un esempio nella sezione [Esempi.See](#examples) an example in the Examples section.</span><span class="sxs-lookup"><span data-stu-id="805fd-298">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="805fd-299">Se una versione del modello è già stata installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="805fd-299">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="805fd-300">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="805fd-300">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="805fd-301">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="805fd-301">Lists templates containing the specified name.</span></span> <span data-ttu-id="805fd-302">Se non viene specificato alcun nome, vengono elencati tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="805fd-302">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="805fd-303">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="805fd-303">The language of the template to create.</span></span> <span data-ttu-id="805fd-304">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="805fd-304">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="805fd-305">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="805fd-305">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="805fd-306">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="805fd-306">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="805fd-307">In questi casi, racchiudere il valore del parametro del linguaggio tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="805fd-307">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="805fd-308">Ad esempio: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="805fd-308">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="805fd-309">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="805fd-309">The name for the created output.</span></span> <span data-ttu-id="805fd-310">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="805fd-310">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="805fd-311">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-311">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="805fd-312">Disponibile da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-312">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="805fd-313">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-313">Location to place the generated output.</span></span> <span data-ttu-id="805fd-314">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="805fd-314">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="805fd-315">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="805fd-315">Filters templates based on available types.</span></span> <span data-ttu-id="805fd-316">I valori `project`predefiniti `item`sono `other`, , o .</span><span class="sxs-lookup"><span data-stu-id="805fd-316">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="805fd-317">Disinstalla un pacchetto di `PATH` `NUGET_ID` modelli nel file o fornito.</span><span class="sxs-lookup"><span data-stu-id="805fd-317">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="805fd-318">Quando `<PATH|NUGET_ID>` il valore non è specificato, vengono visualizzati tutti i modelli di modello attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="805fd-318">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="805fd-319">Quando si `NUGET_ID`specifica , non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="805fd-319">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="805fd-320">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="805fd-320">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="805fd-321">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="805fd-321">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="805fd-322">Ad esempio, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che la contiene non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="805fd-322">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="805fd-323">Non includere una barra di terminazione finale nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="805fd-323">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="805fd-324">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="805fd-324">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="805fd-325">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-325">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="805fd-326">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="805fd-326">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="805fd-327">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-327">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="805fd-328">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="805fd-328">Template options</span></span>

<span data-ttu-id="805fd-329">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="805fd-329">Each project template may have additional options available.</span></span> <span data-ttu-id="805fd-330">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="805fd-330">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="805fd-331">console</span><span class="sxs-lookup"><span data-stu-id="805fd-331">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-332">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-332">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-333">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-333">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="805fd-334">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-334">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-335">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-335">SDK version</span></span> | <span data-ttu-id="805fd-336">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-336">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-337">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-337">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-338">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-338">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="805fd-339">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="805fd-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="805fd-340">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="805fd-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="805fd-341">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="805fd-341">Not supported for F#.</span></span> <span data-ttu-id="805fd-342">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-342">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="805fd-343">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="805fd-343">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-344">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-344">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="805fd-345">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-345">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="805fd-346">classlib</span><span class="sxs-lookup"><span data-stu-id="805fd-346">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-347">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-347">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-348">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="805fd-348">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="805fd-349">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="805fd-349">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="805fd-350">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="805fd-350">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="805fd-351">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="805fd-351">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="805fd-352">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="805fd-352">Not supported for F#.</span></span> <span data-ttu-id="805fd-353">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-353">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="805fd-354">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="805fd-354">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-355">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-355">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a><span data-ttu-id="805fd-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="805fd-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-357">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-357">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-358">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="805fd-358">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="805fd-359">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-359">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="805fd-360">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="805fd-360">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="805fd-361">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="805fd-361">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="805fd-362">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="805fd-362">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-363">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-363">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a><span data-ttu-id="805fd-364">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="805fd-364">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="805fd-365">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="805fd-365">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="805fd-366">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="805fd-366">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="805fd-367">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="805fd-367">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-368">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-368">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a><span data-ttu-id="805fd-369">lavoratore, grpc</span><span class="sxs-lookup"><span data-stu-id="805fd-369">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-370">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-370">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-371">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="805fd-371">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="805fd-372">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-372">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="805fd-373">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-373">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-374">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-374">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="805fd-375">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="805fd-375">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-376">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-376">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-377">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-377">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="805fd-378">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-378">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-379">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-379">SDK version</span></span> | <span data-ttu-id="805fd-380">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-380">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-381">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-381">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-382">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-382">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="805fd-383">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="805fd-383">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-384">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-384">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="805fd-385">Nunit</span><span class="sxs-lookup"><span data-stu-id="805fd-385">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-386">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-386">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="805fd-387">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-387">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-388">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-388">SDK version</span></span> | <span data-ttu-id="805fd-389">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-389">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-390">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-390">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-391">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-391">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="805fd-392">2.2</span><span class="sxs-lookup"><span data-stu-id="805fd-392">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="805fd-393">2.1</span><span class="sxs-lookup"><span data-stu-id="805fd-393">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="805fd-394">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="805fd-394">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-395">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-395">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="805fd-396">pagina</span><span class="sxs-lookup"><span data-stu-id="805fd-396">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="805fd-397">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-397">Namespace for the generated code.</span></span> <span data-ttu-id="805fd-398">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="805fd-398">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="805fd-399">Crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="805fd-399">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a><span data-ttu-id="805fd-400">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="805fd-400">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="805fd-401">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-401">Namespace for the generated code.</span></span> <span data-ttu-id="805fd-402">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="805fd-402">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="805fd-403">blazorservere</span><span class="sxs-lookup"><span data-stu-id="805fd-403">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="805fd-404">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="805fd-404">The type of authentication to use.</span></span> <span data-ttu-id="805fd-405">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="805fd-405">The possible values are:</span></span>

  - <span data-ttu-id="805fd-406">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="805fd-406">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="805fd-407">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="805fd-407">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="805fd-408">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="805fd-408">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="805fd-409">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="805fd-409">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="805fd-410">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="805fd-410">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="805fd-411">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="805fd-411">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="805fd-412">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-412">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="805fd-413">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-413">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-414">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="805fd-414">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="805fd-415">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-415">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="805fd-416">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-416">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="805fd-417">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-417">The reset password policy ID for this project.</span></span> <span data-ttu-id="805fd-418">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-418">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="805fd-419">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-419">The edit profile policy ID for this project.</span></span> <span data-ttu-id="805fd-420">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-420">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="805fd-421">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-421">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="805fd-422">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-422">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="805fd-423">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="805fd-423">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="805fd-424">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-424">The Client ID for this project.</span></span> <span data-ttu-id="805fd-425">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-425">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="805fd-426">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="805fd-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="805fd-427">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="805fd-427">The domain for the directory tenant.</span></span> <span data-ttu-id="805fd-428">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-429">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="805fd-429">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="805fd-430">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-430">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="805fd-431">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="805fd-432">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="805fd-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="805fd-433">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="805fd-433">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="805fd-434">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-434">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-435">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="805fd-435">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="805fd-436">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="805fd-436">Allows this application read-access to the directory.</span></span> <span data-ttu-id="805fd-437">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-437">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="805fd-438">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-438">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="805fd-439">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="805fd-439">Turns off HTTPS.</span></span> <span data-ttu-id="805fd-440">Questa opzione si `Individual` `IndividualB2C`applica `SingleOrg`solo `MultiOrg` se , , `--auth`o non vengono utilizzati per .</span><span class="sxs-lookup"><span data-stu-id="805fd-440">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="805fd-441">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="805fd-441">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="805fd-442">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-442">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-443">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-443">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="805fd-444">Web</span><span class="sxs-lookup"><span data-stu-id="805fd-444">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="805fd-445">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-445">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-446">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-446">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-447">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-447">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="805fd-448">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-448">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-449">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-449">SDK version</span></span> | <span data-ttu-id="805fd-450">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-450">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-451">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-451">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-452">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-452">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="805fd-453">2.1</span><span class="sxs-lookup"><span data-stu-id="805fd-453">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="805fd-454">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-454">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="805fd-455">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="805fd-455">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a><span data-ttu-id="805fd-456">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="805fd-456">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="805fd-457">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="805fd-457">The type of authentication to use.</span></span> <span data-ttu-id="805fd-458">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="805fd-458">The possible values are:</span></span>

  - <span data-ttu-id="805fd-459">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="805fd-459">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="805fd-460">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="805fd-460">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="805fd-461">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="805fd-461">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="805fd-462">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="805fd-462">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="805fd-463">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="805fd-463">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="805fd-464">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="805fd-464">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="805fd-465">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-465">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="805fd-466">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-466">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-467">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="805fd-467">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="805fd-468">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-468">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="805fd-469">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-469">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="805fd-470">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-470">The reset password policy ID for this project.</span></span> <span data-ttu-id="805fd-471">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-471">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="805fd-472">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-472">The edit profile policy ID for this project.</span></span> <span data-ttu-id="805fd-473">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-473">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="805fd-474">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-474">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="805fd-475">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-475">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="805fd-476">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="805fd-476">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="805fd-477">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-477">The Client ID for this project.</span></span> <span data-ttu-id="805fd-478">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-478">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="805fd-479">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="805fd-479">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="805fd-480">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="805fd-480">The domain for the directory tenant.</span></span> <span data-ttu-id="805fd-481">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-481">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-482">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="805fd-482">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="805fd-483">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-483">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="805fd-484">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-484">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="805fd-485">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="805fd-485">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="805fd-486">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="805fd-486">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="805fd-487">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-487">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-488">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="805fd-488">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="805fd-489">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="805fd-489">Allows this application read-access to the directory.</span></span> <span data-ttu-id="805fd-490">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-490">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="805fd-491">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-491">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="805fd-492">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="805fd-492">Turns off HTTPS.</span></span> <span data-ttu-id="805fd-493">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="805fd-493">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="805fd-494">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="805fd-494">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="805fd-495">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-495">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-496">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-496">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-497">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-497">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="805fd-498">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-498">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-499">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-499">SDK version</span></span> | <span data-ttu-id="805fd-500">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-500">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-501">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-501">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-502">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-502">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="805fd-503">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-503">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="805fd-504">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-504">Includes BrowserLink in the project.</span></span> <span data-ttu-id="805fd-505">Opzione non disponibile in .NET Core 2.2 e 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-505">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="805fd-506">Determina se il progetto è configurato per utilizzare la compilazione di [runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle compilazioni di debug.</span><span class="sxs-lookup"><span data-stu-id="805fd-506">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="805fd-507">Opzione disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-507">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a><span data-ttu-id="805fd-508">angolare, reagire</span><span class="sxs-lookup"><span data-stu-id="805fd-508">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="805fd-509">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="805fd-509">The type of authentication to use.</span></span> <span data-ttu-id="805fd-510">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-510">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="805fd-511">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="805fd-511">The possible values are:</span></span>

  - <span data-ttu-id="805fd-512">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="805fd-512">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="805fd-513">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="805fd-513">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="805fd-514">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-514">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-515">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-515">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="805fd-516">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="805fd-516">Turns off HTTPS.</span></span> <span data-ttu-id="805fd-517">Questa opzione si applica `None`solo se l'autenticazione è .</span><span class="sxs-lookup"><span data-stu-id="805fd-517">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="805fd-518">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="805fd-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="805fd-519">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-520">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-520">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-521">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-521">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-522">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-522">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="805fd-523">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-523">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-524">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-524">SDK version</span></span> | <span data-ttu-id="805fd-525">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-525">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-526">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-526">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-527">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-527">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="805fd-528">2.1</span><span class="sxs-lookup"><span data-stu-id="805fd-528">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="805fd-529">reactredux</span><span class="sxs-lookup"><span data-stu-id="805fd-529">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="805fd-530">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-531">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-532">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="805fd-533">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-534">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-534">SDK version</span></span> | <span data-ttu-id="805fd-535">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-536">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-537">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="805fd-538">2.1</span><span class="sxs-lookup"><span data-stu-id="805fd-538">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="805fd-539">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="805fd-540">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="805fd-540">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="805fd-541">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="805fd-541">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="805fd-542">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="805fd-543">Supporta l'aggiunta di pagine e viste Razor tradizionali oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="805fd-543">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="805fd-544">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-544">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="805fd-545">webapi</span><span class="sxs-lookup"><span data-stu-id="805fd-545">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="805fd-546">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="805fd-546">The type of authentication to use.</span></span> <span data-ttu-id="805fd-547">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="805fd-547">The possible values are:</span></span>

  - <span data-ttu-id="805fd-548">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="805fd-548">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="805fd-549">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="805fd-549">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="805fd-550">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="805fd-550">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="805fd-551">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="805fd-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="805fd-552">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="805fd-553">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="805fd-554">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="805fd-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="805fd-555">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="805fd-556">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="805fd-556">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="805fd-557">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-557">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="805fd-558">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="805fd-559">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="805fd-559">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="805fd-560">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-560">The Client ID for this project.</span></span> <span data-ttu-id="805fd-561">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="805fd-562">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="805fd-562">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="805fd-563">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="805fd-563">The domain for the directory tenant.</span></span> <span data-ttu-id="805fd-564">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-564">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="805fd-565">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="805fd-565">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="805fd-566">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="805fd-566">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="805fd-567">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="805fd-567">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="805fd-568">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="805fd-568">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="805fd-569">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="805fd-569">Allows this application read-access to the directory.</span></span> <span data-ttu-id="805fd-570">Si applica `SingleOrg` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-570">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="805fd-571">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="805fd-571">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="805fd-572">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="805fd-572">Turns off HTTPS.</span></span> <span data-ttu-id="805fd-573">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="805fd-573">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="805fd-574">Questa opzione si `IndividualB2C` `SingleOrg` applica solo se o non vengono utilizzati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-574">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="805fd-575">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="805fd-575">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="805fd-576">Si applica `IndividualB2C` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-576">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="805fd-577">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="805fd-577">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="805fd-578">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="805fd-578">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="805fd-579">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="805fd-579">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="805fd-580">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="805fd-580">SDK version</span></span> | <span data-ttu-id="805fd-581">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="805fd-581">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="805fd-582">3.1</span><span class="sxs-lookup"><span data-stu-id="805fd-582">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="805fd-583">3.0</span><span class="sxs-lookup"><span data-stu-id="805fd-583">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="805fd-584">2.1</span><span class="sxs-lookup"><span data-stu-id="805fd-584">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="805fd-585">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="805fd-585">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="805fd-586">globaljson</span><span class="sxs-lookup"><span data-stu-id="805fd-586">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="805fd-587">Specifica la versione di .NET Core SDK da utilizzare nel file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="805fd-587">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="805fd-588">Esempi</span><span class="sxs-lookup"><span data-stu-id="805fd-588">Examples</span></span>

- <span data-ttu-id="805fd-589">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="805fd-589">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="805fd-590">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="805fd-590">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="805fd-591">Creare un progetto di libreria di classi .NET Standard nella directory specificata:Create a .NET Standard class library project in the specified directory:</span><span class="sxs-lookup"><span data-stu-id="805fd-591">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="805fd-592">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="805fd-592">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="805fd-593">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="805fd-593">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="805fd-594">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="805fd-594">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="805fd-595">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="805fd-595">List all templates matching the *we* substring.</span></span> <span data-ttu-id="805fd-596">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="805fd-596">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="805fd-597">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="805fd-597">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="805fd-598">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="805fd-598">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="805fd-599">Installare la versione 2.0 dei modelli SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="805fd-599">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="805fd-600">Elencare i modelli installati e i dettagli su di essi, tra cui come disinstallarli:</span><span class="sxs-lookup"><span data-stu-id="805fd-600">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="805fd-601">Creare un *file global.json* nella directory corrente impostando la versione SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="805fd-601">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="805fd-602">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="805fd-602">See also</span></span>

- [<span data-ttu-id="805fd-603">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="805fd-603">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="805fd-604">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="805fd-604">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="805fd-605">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="805fd-605">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="805fd-606">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="805fd-606">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
