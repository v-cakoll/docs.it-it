---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 02/13/2020
ms.openlocfilehash: f11512acf5a1fdc4bde49b3d1212ccf6335dff8b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451330"
---
# <a name="dotnet-new"></a><span data-ttu-id="e9ada-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e9ada-103">dotnet new</span></span>

<span data-ttu-id="e9ada-104">**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="e9ada-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e9ada-105">Name</span><span class="sxs-lookup"><span data-stu-id="e9ada-105">Name</span></span>

<span data-ttu-id="e9ada-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e9ada-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e9ada-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] 
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="e9ada-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9ada-108">Description</span></span>

<span data-ttu-id="e9ada-109">Il `dotnet new` comando crea un progetto .NET Core o altri artefatti in base a un modello.</span><span class="sxs-lookup"><span data-stu-id="e9ada-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="e9ada-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="e9ada-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="e9ada-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e9ada-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="e9ada-112">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="e9ada-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e9ada-113">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="e9ada-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e9ada-114">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e9ada-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="e9ada-115">È possibile eseguire `dotnet new --list` per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="e9ada-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="e9ada-116">Se il valore `TEMPLATE` non corrisponde esattamente al testo presente nella colonna **modelli** o **nome breve** della tabella restituita, viene eseguita una corrispondenza di sottostringa su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="e9ada-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="e9ada-117">A partire da .NET Core 3,0 SDK, l'interfaccia della riga di comando Cerca i modelli in NuGet.org quando si richiama il comando `dotnet new` nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9ada-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="e9ada-118">Se l'interfaccia della riga di comando non riesce a trovare una corrispondenza del modello durante la chiamata di `dotnet new`, non anche parziale.</span><span class="sxs-lookup"><span data-stu-id="e9ada-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="e9ada-119">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="e9ada-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="e9ada-120">In questo caso, il progetto o l'artefatto viene creato, ma l'interfaccia della riga di comando segnala una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="e9ada-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="e9ada-121">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="e9ada-121">The command contains a default list of templates.</span></span> <span data-ttu-id="e9ada-122">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e9ada-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e9ada-123">Nella tabella seguente sono illustrati i modelli preinstallati con la .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="e9ada-124">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="e9ada-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="e9ada-125">Fare clic sul collegamento nome breve per visualizzare le opzioni specifiche del modello.</span><span class="sxs-lookup"><span data-stu-id="e9ada-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="e9ada-126">Modelli</span><span class="sxs-lookup"><span data-stu-id="e9ada-126">Templates</span></span>                                    | <span data-ttu-id="e9ada-127">Nome breve</span><span class="sxs-lookup"><span data-stu-id="e9ada-127">Short name</span></span>                      | <span data-ttu-id="e9ada-128">Lingua:</span><span class="sxs-lookup"><span data-stu-id="e9ada-128">Language</span></span>     | <span data-ttu-id="e9ada-129">Tag</span><span class="sxs-lookup"><span data-stu-id="e9ada-129">Tags</span></span>                                  | <span data-ttu-id="e9ada-130">Introdotte</span><span class="sxs-lookup"><span data-stu-id="e9ada-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="e9ada-131">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="e9ada-131">Console Application</span></span>                          | [<span data-ttu-id="e9ada-132">console</span><span class="sxs-lookup"><span data-stu-id="e9ada-132">console</span></span>](#console)             | <span data-ttu-id="e9ada-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e9ada-133">[C#], F#, VB</span></span> | <span data-ttu-id="e9ada-134">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="e9ada-134">Common/Console</span></span>                        | <span data-ttu-id="e9ada-135">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-135">1.0</span></span>        |
| <span data-ttu-id="e9ada-136">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e9ada-136">Class library</span></span>                                | [<span data-ttu-id="e9ada-137">classlib</span><span class="sxs-lookup"><span data-stu-id="e9ada-137">classlib</span></span>](#classlib)           | <span data-ttu-id="e9ada-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e9ada-138">[C#], F#, VB</span></span> | <span data-ttu-id="e9ada-139">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="e9ada-139">Common/Library</span></span>                        | <span data-ttu-id="e9ada-140">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-140">1.0</span></span>        |
| <span data-ttu-id="e9ada-141">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-141">WPF Application</span></span>                              | [<span data-ttu-id="e9ada-142">WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="e9ada-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-143">[C#]</span></span>         | <span data-ttu-id="e9ada-144">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-144">Common/WPF</span></span>                            | <span data-ttu-id="e9ada-145">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-145">3.0</span></span>        |
| <span data-ttu-id="e9ada-146">Libreria di classi WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-146">WPF Class library</span></span>                            | [<span data-ttu-id="e9ada-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="e9ada-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="e9ada-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-148">[C#]</span></span>         | <span data-ttu-id="e9ada-149">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-149">Common/WPF</span></span>                            | <span data-ttu-id="e9ada-150">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-150">3.0</span></span>        |
| <span data-ttu-id="e9ada-151">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="e9ada-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="e9ada-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="e9ada-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-153">[C#]</span></span>         | <span data-ttu-id="e9ada-154">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-154">Common/WPF</span></span>                            | <span data-ttu-id="e9ada-155">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-155">3.0</span></span>        |
| <span data-ttu-id="e9ada-156">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="e9ada-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e9ada-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="e9ada-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-158">[C#]</span></span>         | <span data-ttu-id="e9ada-159">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="e9ada-159">Common/WPF</span></span>                            | <span data-ttu-id="e9ada-160">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-160">3.0</span></span>        |
| <span data-ttu-id="e9ada-161">Applicazione Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e9ada-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="e9ada-162">WinForms</span><span class="sxs-lookup"><span data-stu-id="e9ada-162">winforms</span></span>](#winforms)           | <span data-ttu-id="e9ada-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-163">[C#]</span></span>         | <span data-ttu-id="e9ada-164">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="e9ada-164">Common/WinForms</span></span>                       | <span data-ttu-id="e9ada-165">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-165">3.0</span></span>        |
| <span data-ttu-id="e9ada-166">Libreria di classi Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e9ada-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="e9ada-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="e9ada-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="e9ada-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-168">[C#]</span></span>         | <span data-ttu-id="e9ada-169">Comune/Windows Form</span><span class="sxs-lookup"><span data-stu-id="e9ada-169">Common/WinForms</span></span>                       | <span data-ttu-id="e9ada-170">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-170">3.0</span></span>        |
| <span data-ttu-id="e9ada-171">Servizio ruolo di lavoro</span><span class="sxs-lookup"><span data-stu-id="e9ada-171">Worker Service</span></span>                               | [<span data-ttu-id="e9ada-172">lavoro</span><span class="sxs-lookup"><span data-stu-id="e9ada-172">worker</span></span>](#web-others)           | <span data-ttu-id="e9ada-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-173">[C#]</span></span>         | <span data-ttu-id="e9ada-174">Comune/di lavoro/Web</span><span class="sxs-lookup"><span data-stu-id="e9ada-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="e9ada-175">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-175">3.0</span></span>        |
| <span data-ttu-id="e9ada-176">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="e9ada-176">Unit Test Project</span></span>                            | [<span data-ttu-id="e9ada-177">MSTest</span><span class="sxs-lookup"><span data-stu-id="e9ada-177">mstest</span></span>](#test)                 | <span data-ttu-id="e9ada-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e9ada-178">[C#], F#, VB</span></span> | <span data-ttu-id="e9ada-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="e9ada-179">Test/MSTest</span></span>                           | <span data-ttu-id="e9ada-180">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-180">1.0</span></span>        |
| <span data-ttu-id="e9ada-181">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e9ada-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="e9ada-182">nunit</span><span class="sxs-lookup"><span data-stu-id="e9ada-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="e9ada-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e9ada-183">[C#], F#, VB</span></span> | <span data-ttu-id="e9ada-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="e9ada-184">Test/NUnit</span></span>                            | <span data-ttu-id="e9ada-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="e9ada-185">2.1.400</span></span>    |
| <span data-ttu-id="e9ada-186">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e9ada-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="e9ada-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e9ada-187">[C#], F#, VB</span></span> | <span data-ttu-id="e9ada-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="e9ada-188">Test/NUnit</span></span>                            | <span data-ttu-id="e9ada-189">2.2</span><span class="sxs-lookup"><span data-stu-id="e9ada-189">2.2</span></span>        |
| <span data-ttu-id="e9ada-190">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="e9ada-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="e9ada-191">xUnit</span><span class="sxs-lookup"><span data-stu-id="e9ada-191">xunit</span></span>](#test)                  | <span data-ttu-id="e9ada-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e9ada-192">[C#], F#, VB</span></span> | <span data-ttu-id="e9ada-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="e9ada-193">Test/xUnit</span></span>                            | <span data-ttu-id="e9ada-194">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-194">1.0</span></span>        |
| <span data-ttu-id="e9ada-195">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="e9ada-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="e9ada-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-196">[C#]</span></span>         | <span data-ttu-id="e9ada-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e9ada-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="e9ada-198">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-198">3.0</span></span>        |
| <span data-ttu-id="e9ada-199">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="e9ada-199">Razor Page</span></span>                                   | [<span data-ttu-id="e9ada-200">page</span><span class="sxs-lookup"><span data-stu-id="e9ada-200">page</span></span>](#page)                   | <span data-ttu-id="e9ada-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-201">[C#]</span></span>         | <span data-ttu-id="e9ada-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e9ada-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="e9ada-203">2</span><span class="sxs-lookup"><span data-stu-id="e9ada-203">2.0</span></span>        |
| <span data-ttu-id="e9ada-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e9ada-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="e9ada-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="e9ada-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="e9ada-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-206">[C#]</span></span>         | <span data-ttu-id="e9ada-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e9ada-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="e9ada-208">2</span><span class="sxs-lookup"><span data-stu-id="e9ada-208">2.0</span></span>        |
| <span data-ttu-id="e9ada-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e9ada-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="e9ada-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-210">[C#]</span></span>         | <span data-ttu-id="e9ada-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e9ada-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="e9ada-212">2</span><span class="sxs-lookup"><span data-stu-id="e9ada-212">2.0</span></span>        |
| <span data-ttu-id="e9ada-213">App Server Blazer</span><span class="sxs-lookup"><span data-stu-id="e9ada-213">Blazor Server App</span></span>                            | [<span data-ttu-id="e9ada-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e9ada-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="e9ada-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-215">[C#]</span></span>         | <span data-ttu-id="e9ada-216">Web/Blazer</span><span class="sxs-lookup"><span data-stu-id="e9ada-216">Web/Blazor</span></span>                            | <span data-ttu-id="e9ada-217">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-217">3.0</span></span>        |
| <span data-ttu-id="e9ada-218">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="e9ada-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="e9ada-219">web</span><span class="sxs-lookup"><span data-stu-id="e9ada-219">web</span></span>](#web)                     | <span data-ttu-id="e9ada-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e9ada-220">[C#], F#</span></span>     | <span data-ttu-id="e9ada-221">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="e9ada-221">Web/Empty</span></span>                             | <span data-ttu-id="e9ada-222">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-222">1.0</span></span>        |
| <span data-ttu-id="e9ada-223">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e9ada-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="e9ada-224">mvc</span><span class="sxs-lookup"><span data-stu-id="e9ada-224">mvc</span></span>](#web-options)             | <span data-ttu-id="e9ada-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e9ada-225">[C#], F#</span></span>     | <span data-ttu-id="e9ada-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="e9ada-226">Web/MVC</span></span>                               | <span data-ttu-id="e9ada-227">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-227">1.0</span></span>        |
| <span data-ttu-id="e9ada-228">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e9ada-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="e9ada-229">WebApp, Razor</span><span class="sxs-lookup"><span data-stu-id="e9ada-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="e9ada-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-230">[C#]</span></span>         | <span data-ttu-id="e9ada-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="e9ada-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="e9ada-232">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="e9ada-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="e9ada-233">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e9ada-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="e9ada-234">angolare</span><span class="sxs-lookup"><span data-stu-id="e9ada-234">angular</span></span>](#spa)                 | <span data-ttu-id="e9ada-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-235">[C#]</span></span>         | <span data-ttu-id="e9ada-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="e9ada-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e9ada-237">2</span><span class="sxs-lookup"><span data-stu-id="e9ada-237">2.0</span></span>        |
| <span data-ttu-id="e9ada-238">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e9ada-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="e9ada-239">React</span><span class="sxs-lookup"><span data-stu-id="e9ada-239">react</span></span>](#spa)                   | <span data-ttu-id="e9ada-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-240">[C#]</span></span>         | <span data-ttu-id="e9ada-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="e9ada-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e9ada-242">2</span><span class="sxs-lookup"><span data-stu-id="e9ada-242">2.0</span></span>        |
| <span data-ttu-id="e9ada-243">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="e9ada-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="e9ada-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="e9ada-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="e9ada-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-245">[C#]</span></span>         | <span data-ttu-id="e9ada-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="e9ada-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e9ada-247">2</span><span class="sxs-lookup"><span data-stu-id="e9ada-247">2.0</span></span>        |
| <span data-ttu-id="e9ada-248">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="e9ada-248">Razor Class Library</span></span>                          | [<span data-ttu-id="e9ada-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e9ada-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="e9ada-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-250">[C#]</span></span>         | <span data-ttu-id="e9ada-251">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="e9ada-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="e9ada-252">2.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-252">2.1</span></span>        |
| <span data-ttu-id="e9ada-253">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e9ada-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="e9ada-254">webapi</span><span class="sxs-lookup"><span data-stu-id="e9ada-254">webapi</span></span>](#webapi)               | <span data-ttu-id="e9ada-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e9ada-255">[C#], F#</span></span>     | <span data-ttu-id="e9ada-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="e9ada-256">Web/WebAPI</span></span>                            | <span data-ttu-id="e9ada-257">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-257">1.0</span></span>        |
| <span data-ttu-id="e9ada-258">Servizio ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e9ada-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="e9ada-259">grpc</span><span class="sxs-lookup"><span data-stu-id="e9ada-259">grpc</span></span>](#web-others)             | <span data-ttu-id="e9ada-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="e9ada-260">[C#]</span></span>         | <span data-ttu-id="e9ada-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="e9ada-261">Web/gRPC</span></span>                              | <span data-ttu-id="e9ada-262">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-262">3.0</span></span>        |
| <span data-ttu-id="e9ada-263">File buffer del protocollo</span><span class="sxs-lookup"><span data-stu-id="e9ada-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="e9ada-264">proto</span><span class="sxs-lookup"><span data-stu-id="e9ada-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="e9ada-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="e9ada-265">Web/gRPC</span></span>                              | <span data-ttu-id="e9ada-266">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-266">3.0</span></span>        |
| <span data-ttu-id="e9ada-267">file gitignore DotNet</span><span class="sxs-lookup"><span data-stu-id="e9ada-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="e9ada-268">Config</span><span class="sxs-lookup"><span data-stu-id="e9ada-268">Config</span></span>                                | <span data-ttu-id="e9ada-269">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-269">3.0</span></span>        |
| <span data-ttu-id="e9ada-270">File global.json</span><span class="sxs-lookup"><span data-stu-id="e9ada-270">global.json file</span></span>                             | [<span data-ttu-id="e9ada-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="e9ada-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="e9ada-272">Config</span><span class="sxs-lookup"><span data-stu-id="e9ada-272">Config</span></span>                                | <span data-ttu-id="e9ada-273">2</span><span class="sxs-lookup"><span data-stu-id="e9ada-273">2.0</span></span>        |
| <span data-ttu-id="e9ada-274">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="e9ada-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="e9ada-275">Config</span><span class="sxs-lookup"><span data-stu-id="e9ada-275">Config</span></span>                                | <span data-ttu-id="e9ada-276">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-276">1.0</span></span>        |
| <span data-ttu-id="e9ada-277">file manifesto dello strumento locale DotNet</span><span class="sxs-lookup"><span data-stu-id="e9ada-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="e9ada-278">Config</span><span class="sxs-lookup"><span data-stu-id="e9ada-278">Config</span></span>                                | <span data-ttu-id="e9ada-279">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-279">3.0</span></span>        |
| <span data-ttu-id="e9ada-280">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="e9ada-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="e9ada-281">Config</span><span class="sxs-lookup"><span data-stu-id="e9ada-281">Config</span></span>                                | <span data-ttu-id="e9ada-282">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-282">1.0</span></span>        |
| <span data-ttu-id="e9ada-283">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="e9ada-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="e9ada-284">Soluzione</span><span class="sxs-lookup"><span data-stu-id="e9ada-284">Solution</span></span>                              | <span data-ttu-id="e9ada-285">1.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="e9ada-286">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e9ada-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="e9ada-287">Visualizza un riepilogo di ciò che accadrebbe se il comando specificato venisse eseguito.</span><span class="sxs-lookup"><span data-stu-id="e9ada-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="e9ada-288">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="e9ada-289">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="e9ada-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e9ada-290">Questa operazione è necessaria quando il modello scelto sostituisce i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="e9ada-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e9ada-291">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e9ada-291">Prints out help for the command.</span></span> <span data-ttu-id="e9ada-292">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="e9ada-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="e9ada-293">Ad esempio, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="e9ada-294">Installa un pacchetto di modelli dal `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e9ada-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e9ada-295">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e9ada-296">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione stabile più recente del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="e9ada-297">Vedere un esempio nella sezione degli [esempi](#examples) .</span><span class="sxs-lookup"><span data-stu-id="e9ada-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="e9ada-298">Se una versione del modello è già installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente, se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="e9ada-299">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e9ada-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="e9ada-300">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="e9ada-301">Se non viene specificato alcun nome, elenca tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="e9ada-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="e9ada-302">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="e9ada-302">The language of the template to create.</span></span> <span data-ttu-id="e9ada-303">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="e9ada-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e9ada-304">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="e9ada-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e9ada-305">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="e9ada-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e9ada-306">In questi casi, racchiudere il valore del parametro Language tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="e9ada-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="e9ada-307">Ad esempio, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="e9ada-308">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-308">The name for the created output.</span></span> <span data-ttu-id="e9ada-309">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e9ada-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="e9ada-310">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="e9ada-311">Disponibile a partire da .NET Core 2,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="e9ada-312">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-312">Location to place the generated output.</span></span> <span data-ttu-id="e9ada-313">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e9ada-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="e9ada-314">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="e9ada-314">Filters templates based on available types.</span></span> <span data-ttu-id="e9ada-315">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="e9ada-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="e9ada-316">Disinstalla un pacchetto di modelli in `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e9ada-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e9ada-317">Quando il valore di `<PATH|NUGET_ID>` non è specificato, vengono visualizzati tutti i pacchetti di modelli attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="e9ada-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="e9ada-318">Quando si specifica `NUGET_ID`, non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="e9ada-319">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="e9ada-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e9ada-320">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e9ada-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e9ada-321">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="e9ada-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="e9ada-322">Non includere una barra di directory finale terminata nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="e9ada-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="e9ada-323">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="e9ada-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="e9ada-324">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="e9ada-325">Verifica se sono disponibili aggiornamenti per i pacchetti di modelli attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="e9ada-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="e9ada-326">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="e9ada-327">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="e9ada-327">Template options</span></span>

<span data-ttu-id="e9ada-328">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e9ada-328">Each project template may have additional options available.</span></span> <span data-ttu-id="e9ada-329">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9ada-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="e9ada-330">del fornitore</span><span class="sxs-lookup"><span data-stu-id="e9ada-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-331">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-332">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e9ada-333">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-334">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-334">SDK version</span></span> | <span data-ttu-id="e9ada-335">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-336">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-337">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e9ada-338">Imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e9ada-339">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e9ada-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e9ada-340">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="e9ada-340">Not supported for F#.</span></span> <span data-ttu-id="e9ada-341">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e9ada-342">Per un elenco delle versioni C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e9ada-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`** 

  <span data-ttu-id="e9ada-343">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="e9ada-344">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="e9ada-345">classlib</span><span class="sxs-lookup"><span data-stu-id="e9ada-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-346">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-347">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e9ada-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e9ada-348">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e9ada-349">Imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e9ada-350">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e9ada-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e9ada-351">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="e9ada-351">Not supported for F#.</span></span> <span data-ttu-id="e9ada-352">Disponibile a partire da .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e9ada-353">Per un elenco delle versioni C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e9ada-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-354">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a><span data-ttu-id="e9ada-355">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="e9ada-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-356">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-357">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e9ada-358">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-358">Available since .NET Core 3.1 SDK.</span></span> 

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e9ada-359">Imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e9ada-360">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e9ada-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e9ada-361">Per un elenco delle versioni C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e9ada-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-362">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a><span data-ttu-id="e9ada-363">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="e9ada-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e9ada-364">Imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e9ada-365">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e9ada-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e9ada-366">Per un elenco delle versioni C# predefinite, vedere [defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e9ada-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-367">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a><span data-ttu-id="e9ada-368">Worker, grpc</span><span class="sxs-lookup"><span data-stu-id="e9ada-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-369">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-370">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e9ada-371">Disponibile a partire da .NET Core 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-371">Available since .NET Core 3.1 SDK.</span></span> 

- **`--exclude-launch-settings`**

  <span data-ttu-id="e9ada-372">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-373">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a><span data-ttu-id="e9ada-374">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="e9ada-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-375">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-376">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e9ada-377">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-378">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-378">SDK version</span></span> | <span data-ttu-id="e9ada-379">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-380">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-381">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e9ada-382">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e9ada-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-383">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="e9ada-384">NUnit</span><span class="sxs-lookup"><span data-stu-id="e9ada-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-385">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="e9ada-386">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-387">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-387">SDK version</span></span> | <span data-ttu-id="e9ada-388">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-389">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-390">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e9ada-391">2.2</span><span class="sxs-lookup"><span data-stu-id="e9ada-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="e9ada-392">2.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e9ada-393">Abilita la creazione di pacchetti per il progetto tramite [DotNet Pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e9ada-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-394">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="e9ada-395">pagina</span><span class="sxs-lookup"><span data-stu-id="e9ada-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e9ada-396">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-396">Namespace for the generated code.</span></span> <span data-ttu-id="e9ada-397">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="e9ada-398">Crea la pagina senza PageModel.</span><span class="sxs-lookup"><span data-stu-id="e9ada-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a><span data-ttu-id="e9ada-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="e9ada-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e9ada-400">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-400">Namespace for the generated code.</span></span> <span data-ttu-id="e9ada-401">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="e9ada-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="e9ada-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e9ada-403">Tipo di autenticazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e9ada-403">The type of authentication to use.</span></span> <span data-ttu-id="e9ada-404">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e9ada-404">The possible values are:</span></span>

  - <span data-ttu-id="e9ada-405">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e9ada-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e9ada-406">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="e9ada-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e9ada-407">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e9ada-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e9ada-408">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e9ada-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e9ada-409">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="e9ada-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e9ada-410">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e9ada-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e9ada-411">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e9ada-412">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-413">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e9ada-414">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e9ada-415">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e9ada-416">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="e9ada-417">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e9ada-418">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e9ada-419">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e9ada-420">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e9ada-421">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e9ada-422">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e9ada-423">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-423">The Client ID for this project.</span></span> <span data-ttu-id="e9ada-424">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e9ada-425">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e9ada-426">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="e9ada-426">The domain for the directory tenant.</span></span> <span data-ttu-id="e9ada-427">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-428">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e9ada-429">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e9ada-430">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e9ada-431">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e9ada-432">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e9ada-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e9ada-433">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-434">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e9ada-435">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="e9ada-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e9ada-436">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e9ada-437">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e9ada-438">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9ada-438">Turns off HTTPS.</span></span> <span data-ttu-id="e9ada-439">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg`o `MultiOrg` non vengono utilizzati per `--auth`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e9ada-440">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="e9ada-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e9ada-441">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-442">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="e9ada-443">Web</span><span class="sxs-lookup"><span data-stu-id="e9ada-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e9ada-444">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-445">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-446">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e9ada-447">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-448">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-448">SDK version</span></span> | <span data-ttu-id="e9ada-449">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-450">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-451">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e9ada-452">2.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e9ada-453">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e9ada-454">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9ada-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a><span data-ttu-id="e9ada-455">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="e9ada-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e9ada-456">Tipo di autenticazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e9ada-456">The type of authentication to use.</span></span> <span data-ttu-id="e9ada-457">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e9ada-457">The possible values are:</span></span>

  - <span data-ttu-id="e9ada-458">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e9ada-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e9ada-459">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="e9ada-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e9ada-460">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e9ada-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e9ada-461">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e9ada-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e9ada-462">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="e9ada-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e9ada-463">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e9ada-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e9ada-464">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e9ada-465">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-466">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e9ada-467">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e9ada-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e9ada-469">ID dei criteri di reimpostazione della password per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="e9ada-470">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e9ada-471">ID dei criteri di modifica del profilo per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e9ada-472">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e9ada-473">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e9ada-474">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e9ada-475">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e9ada-476">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-476">The Client ID for this project.</span></span> <span data-ttu-id="e9ada-477">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e9ada-478">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e9ada-479">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="e9ada-479">The domain for the directory tenant.</span></span> <span data-ttu-id="e9ada-480">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-481">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e9ada-482">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e9ada-483">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e9ada-484">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e9ada-485">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e9ada-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e9ada-486">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-487">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e9ada-488">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="e9ada-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e9ada-489">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e9ada-490">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e9ada-491">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9ada-491">Turns off HTTPS.</span></span> <span data-ttu-id="e9ada-492">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="e9ada-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e9ada-493">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="e9ada-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e9ada-494">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-495">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-496">Opzione disponibile a partire da .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e9ada-497">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-498">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-498">SDK version</span></span> | <span data-ttu-id="e9ada-499">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-500">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-501">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="e9ada-502">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="e9ada-503">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="e9ada-504">Opzione non disponibile in .NET Core 2,2 e 3,1 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a><span data-ttu-id="e9ada-505">angolare, React</span><span class="sxs-lookup"><span data-stu-id="e9ada-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e9ada-506">Tipo di autenticazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e9ada-506">The type of authentication to use.</span></span> <span data-ttu-id="e9ada-507">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-507">Available since .NET Core 3.0 SDK.</span></span> 
  
  <span data-ttu-id="e9ada-508">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e9ada-508">The possible values are:</span></span>

  - <span data-ttu-id="e9ada-509">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e9ada-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e9ada-510">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="e9ada-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e9ada-511">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-511">Excludes *launchSettings.json* from the generated template.</span></span> 

- **`--no-restore`**

  <span data-ttu-id="e9ada-512">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e9ada-513">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9ada-513">Turns off HTTPS.</span></span> <span data-ttu-id="e9ada-514">Questa opzione si applica solo se l'autenticazione è `None`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e9ada-515">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="e9ada-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e9ada-516">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-517">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-518">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-519">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e9ada-520">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-521">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-521">SDK version</span></span> | <span data-ttu-id="e9ada-522">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-523">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-524">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e9ada-525">2.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="e9ada-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="e9ada-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e9ada-527">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-527">Excludes *launchSettings.json* from the generated template.</span></span> 

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-528">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-529">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e9ada-530">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-531">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-531">SDK version</span></span> | <span data-ttu-id="e9ada-532">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-533">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-534">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e9ada-535">2.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="e9ada-536">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e9ada-537">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9ada-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="e9ada-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="e9ada-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="e9ada-539">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="e9ada-540">Supporta l'aggiunta di pagine e visualizzazioni tradizionali Razor oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="e9ada-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="e9ada-541">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="e9ada-542">webapi</span><span class="sxs-lookup"><span data-stu-id="e9ada-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e9ada-543">Tipo di autenticazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e9ada-543">The type of authentication to use.</span></span> <span data-ttu-id="e9ada-544">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e9ada-544">The possible values are:</span></span>

  - <span data-ttu-id="e9ada-545">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e9ada-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e9ada-546">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e9ada-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e9ada-547">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e9ada-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e9ada-548">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e9ada-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e9ada-549">Istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e9ada-550">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e9ada-551">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e9ada-552">ID dei criteri di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e9ada-553">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e9ada-554">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e9ada-555">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e9ada-556">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e9ada-557">ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-557">The Client ID for this project.</span></span> <span data-ttu-id="e9ada-558">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e9ada-559">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e9ada-560">Dominio del tenant di directory.</span><span class="sxs-lookup"><span data-stu-id="e9ada-560">The domain for the directory tenant.</span></span> <span data-ttu-id="e9ada-561">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e9ada-562">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e9ada-563">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e9ada-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e9ada-564">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e9ada-565">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e9ada-566">Consente all'applicazione di accedere in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="e9ada-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e9ada-567">Si applica solo all'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e9ada-568">Esclude *launchSettings. JSON* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e9ada-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e9ada-569">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9ada-569">Turns off HTTPS.</span></span> <span data-ttu-id="e9ada-570">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e9ada-571">Questa opzione si applica solo se `IndividualB2C` o `SingleOrg` non vengono utilizzate per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e9ada-572">Specifica il database locale da usare anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="e9ada-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e9ada-573">Si applica solo all'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e9ada-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e9ada-574">Specifica il [Framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9ada-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e9ada-575">Opzione non disponibile in .NET Core 2,2 SDK.</span><span class="sxs-lookup"><span data-stu-id="e9ada-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e9ada-576">La tabella seguente elenca i valori predefiniti in base al numero di versione dell'SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="e9ada-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e9ada-577">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="e9ada-577">SDK version</span></span> | <span data-ttu-id="e9ada-578">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="e9ada-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e9ada-579">3.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e9ada-580">3.0</span><span class="sxs-lookup"><span data-stu-id="e9ada-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e9ada-581">2.1</span><span class="sxs-lookup"><span data-stu-id="e9ada-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e9ada-582">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9ada-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="e9ada-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="e9ada-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="e9ada-584">Specifica la versione del .NET Core SDK da usare nel file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="e9ada-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="e9ada-585">Esempi</span><span class="sxs-lookup"><span data-stu-id="e9ada-585">Examples</span></span>

- <span data-ttu-id="e9ada-586">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="e9ada-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="e9ada-587">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="e9ada-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="e9ada-588">Creare un progetto libreria di classi .NET Standard nella directory specificata:</span><span class="sxs-lookup"><span data-stu-id="e9ada-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="e9ada-589">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="e9ada-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="e9ada-590">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="e9ada-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="e9ada-591">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="e9ada-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="e9ada-592">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="e9ada-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="e9ada-593">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="e9ada-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="e9ada-594">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="e9ada-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="e9ada-595">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="e9ada-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="e9ada-596">Installare la versione 2,0 dei modelli di SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="e9ada-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="e9ada-597">Elencare i modelli e i dettagli installati, inclusa la modalità di disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="e9ada-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="e9ada-598">Creare un file *Global. JSON* nella directory corrente impostando la versione dell'SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="e9ada-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="e9ada-599">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9ada-599">See also</span></span>

- [<span data-ttu-id="e9ada-600">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e9ada-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="e9ada-601">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e9ada-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="e9ada-602">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="e9ada-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="e9ada-603">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e9ada-603">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
