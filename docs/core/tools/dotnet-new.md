---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399126"
---
# <a name="dotnet-new"></a><span data-ttu-id="c5781-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c5781-103">dotnet new</span></span>

<span data-ttu-id="c5781-104">**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c5781-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c5781-105">Nome</span><span class="sxs-lookup"><span data-stu-id="c5781-105">Name</span></span>

<span data-ttu-id="c5781-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="c5781-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c5781-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c5781-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c5781-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5781-108">Description</span></span>

<span data-ttu-id="c5781-109">Il `dotnet new` comando crea un progetto .NET Core o altri elementi basati su un modello.</span><span class="sxs-lookup"><span data-stu-id="c5781-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="c5781-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="c5781-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="c5781-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c5781-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="c5781-112">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="c5781-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c5781-113">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="c5781-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c5781-114">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="c5781-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="c5781-115">È possibile `dotnet new --list` eseguire per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="c5781-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="c5781-116">Se `TEMPLATE` il valore non corrisponde esattamente al testo nella colonna **Templates** o **Short Name** della tabella restituita, viene eseguita una corrispondenza di sottostringhe su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="c5781-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="c5781-117">A partire da .NET Core 3.0 SDK, l'interfaccia `dotnet new` della riga di comando cerca i modelli in NuGet.org quando si richiama il comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5781-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="c5781-118">Se l'interfaccia della riga di comando `dotnet new`non riesce a trovare una corrispondenza del modello quando si richiama , nemmeno parziale.</span><span class="sxs-lookup"><span data-stu-id="c5781-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="c5781-119">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="c5781-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="c5781-120">In questo caso, il progetto o l'elemento viene creato, ma l'interfaccia della riga di comando avvisa l'utente di una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="c5781-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="c5781-121">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="c5781-121">The command contains a default list of templates.</span></span> <span data-ttu-id="c5781-122">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="c5781-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c5781-123">Nella tabella seguente vengono illustrati i modelli preinstallati con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="c5781-124">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="c5781-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="c5781-125">Fare clic sul collegamento del nome breve per visualizzare le opzioni del modello specifico.</span><span class="sxs-lookup"><span data-stu-id="c5781-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="c5781-126">Modelli</span><span class="sxs-lookup"><span data-stu-id="c5781-126">Templates</span></span>                                    | <span data-ttu-id="c5781-127">Nome breve</span><span class="sxs-lookup"><span data-stu-id="c5781-127">Short name</span></span>                      | <span data-ttu-id="c5781-128">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="c5781-128">Language</span></span>     | <span data-ttu-id="c5781-129">Tag</span><span class="sxs-lookup"><span data-stu-id="c5781-129">Tags</span></span>                                  | <span data-ttu-id="c5781-130">Presentare</span><span class="sxs-lookup"><span data-stu-id="c5781-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="c5781-131">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="c5781-131">Console Application</span></span>                          | [<span data-ttu-id="c5781-132">console</span><span class="sxs-lookup"><span data-stu-id="c5781-132">console</span></span>](#console)             | <span data-ttu-id="c5781-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c5781-133">[C#], F#, VB</span></span> | <span data-ttu-id="c5781-134">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="c5781-134">Common/Console</span></span>                        | <span data-ttu-id="c5781-135">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-135">1.0</span></span>        |
| <span data-ttu-id="c5781-136">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="c5781-136">Class library</span></span>                                | [<span data-ttu-id="c5781-137">classlib</span><span class="sxs-lookup"><span data-stu-id="c5781-137">classlib</span></span>](#classlib)           | <span data-ttu-id="c5781-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c5781-138">[C#], F#, VB</span></span> | <span data-ttu-id="c5781-139">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="c5781-139">Common/Library</span></span>                        | <span data-ttu-id="c5781-140">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-140">1.0</span></span>        |
| <span data-ttu-id="c5781-141">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="c5781-141">WPF Application</span></span>                              | [<span data-ttu-id="c5781-142">Wpf</span><span class="sxs-lookup"><span data-stu-id="c5781-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="c5781-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-143">[C#]</span></span>         | <span data-ttu-id="c5781-144">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="c5781-144">Common/WPF</span></span>                            | <span data-ttu-id="c5781-145">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-145">3.0</span></span>        |
| <span data-ttu-id="c5781-146">Libreria di classi WPFWPF Class library</span><span class="sxs-lookup"><span data-stu-id="c5781-146">WPF Class library</span></span>                            | [<span data-ttu-id="c5781-147">wpflib (libreria)</span><span class="sxs-lookup"><span data-stu-id="c5781-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="c5781-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-148">[C#]</span></span>         | <span data-ttu-id="c5781-149">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="c5781-149">Common/WPF</span></span>                            | <span data-ttu-id="c5781-150">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-150">3.0</span></span>        |
| <span data-ttu-id="c5781-151">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="c5781-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="c5781-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="c5781-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="c5781-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-153">[C#]</span></span>         | <span data-ttu-id="c5781-154">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="c5781-154">Common/WPF</span></span>                            | <span data-ttu-id="c5781-155">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-155">3.0</span></span>        |
| <span data-ttu-id="c5781-156">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="c5781-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="c5781-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="c5781-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="c5781-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-158">[C#]</span></span>         | <span data-ttu-id="c5781-159">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="c5781-159">Common/WPF</span></span>                            | <span data-ttu-id="c5781-160">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-160">3.0</span></span>        |
| <span data-ttu-id="c5781-161">Applicazione Windows Form (WinForms)</span><span class="sxs-lookup"><span data-stu-id="c5781-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="c5781-162">Winforms</span><span class="sxs-lookup"><span data-stu-id="c5781-162">winforms</span></span>](#winforms)           | <span data-ttu-id="c5781-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-163">[C#]</span></span>         | <span data-ttu-id="c5781-164">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="c5781-164">Common/WinForms</span></span>                       | <span data-ttu-id="c5781-165">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-165">3.0</span></span>        |
| <span data-ttu-id="c5781-166">Libreria di classi Windows Form (WindowsForms)</span><span class="sxs-lookup"><span data-stu-id="c5781-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="c5781-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="c5781-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="c5781-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-168">[C#]</span></span>         | <span data-ttu-id="c5781-169">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="c5781-169">Common/WinForms</span></span>                       | <span data-ttu-id="c5781-170">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-170">3.0</span></span>        |
| <span data-ttu-id="c5781-171">Servizio di lavoro</span><span class="sxs-lookup"><span data-stu-id="c5781-171">Worker Service</span></span>                               | [<span data-ttu-id="c5781-172">Lavoratore</span><span class="sxs-lookup"><span data-stu-id="c5781-172">worker</span></span>](#web-others)           | <span data-ttu-id="c5781-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-173">[C#]</span></span>         | <span data-ttu-id="c5781-174">Comune/Lavoratore/Web</span><span class="sxs-lookup"><span data-stu-id="c5781-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="c5781-175">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-175">3.0</span></span>        |
| <span data-ttu-id="c5781-176">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="c5781-176">Unit Test Project</span></span>                            | [<span data-ttu-id="c5781-177">Mstest</span><span class="sxs-lookup"><span data-stu-id="c5781-177">mstest</span></span>](#test)                 | <span data-ttu-id="c5781-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c5781-178">[C#], F#, VB</span></span> | <span data-ttu-id="c5781-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="c5781-179">Test/MSTest</span></span>                           | <span data-ttu-id="c5781-180">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-180">1.0</span></span>        |
| <span data-ttu-id="c5781-181">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="c5781-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="c5781-182">Nunit</span><span class="sxs-lookup"><span data-stu-id="c5781-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="c5781-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c5781-183">[C#], F#, VB</span></span> | <span data-ttu-id="c5781-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c5781-184">Test/NUnit</span></span>                            | <span data-ttu-id="c5781-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="c5781-185">2.1.400</span></span>    |
| <span data-ttu-id="c5781-186">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="c5781-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="c5781-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c5781-187">[C#], F#, VB</span></span> | <span data-ttu-id="c5781-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c5781-188">Test/NUnit</span></span>                            | <span data-ttu-id="c5781-189">2.2</span><span class="sxs-lookup"><span data-stu-id="c5781-189">2.2</span></span>        |
| <span data-ttu-id="c5781-190">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="c5781-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="c5781-191">xunit</span><span class="sxs-lookup"><span data-stu-id="c5781-191">xunit</span></span>](#test)                  | <span data-ttu-id="c5781-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c5781-192">[C#], F#, VB</span></span> | <span data-ttu-id="c5781-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="c5781-193">Test/xUnit</span></span>                            | <span data-ttu-id="c5781-194">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-194">1.0</span></span>        |
| <span data-ttu-id="c5781-195">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="c5781-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="c5781-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-196">[C#]</span></span>         | <span data-ttu-id="c5781-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c5781-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="c5781-198">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-198">3.0</span></span>        |
| <span data-ttu-id="c5781-199">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="c5781-199">Razor Page</span></span>                                   | [<span data-ttu-id="c5781-200">Pagina</span><span class="sxs-lookup"><span data-stu-id="c5781-200">page</span></span>](#page)                   | <span data-ttu-id="c5781-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-201">[C#]</span></span>         | <span data-ttu-id="c5781-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c5781-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="c5781-203">2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-203">2.0</span></span>        |
| <span data-ttu-id="c5781-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c5781-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="c5781-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="c5781-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="c5781-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-206">[C#]</span></span>         | <span data-ttu-id="c5781-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c5781-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="c5781-208">2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-208">2.0</span></span>        |
| <span data-ttu-id="c5781-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c5781-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="c5781-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-210">[C#]</span></span>         | <span data-ttu-id="c5781-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c5781-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="c5781-212">2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-212">2.0</span></span>        |
| <span data-ttu-id="c5781-213">Blazor Server App</span><span class="sxs-lookup"><span data-stu-id="c5781-213">Blazor Server App</span></span>                            | [<span data-ttu-id="c5781-214">blazorservere</span><span class="sxs-lookup"><span data-stu-id="c5781-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="c5781-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-215">[C#]</span></span>         | <span data-ttu-id="c5781-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="c5781-216">Web/Blazor</span></span>                            | <span data-ttu-id="c5781-217">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-217">3.0</span></span>        |
| <span data-ttu-id="c5781-218">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="c5781-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="c5781-219">Web</span><span class="sxs-lookup"><span data-stu-id="c5781-219">web</span></span>](#web)                     | <span data-ttu-id="c5781-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c5781-220">[C#], F#</span></span>     | <span data-ttu-id="c5781-221">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="c5781-221">Web/Empty</span></span>                             | <span data-ttu-id="c5781-222">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-222">1.0</span></span>        |
| <span data-ttu-id="c5781-223">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c5781-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="c5781-224">Mvc</span><span class="sxs-lookup"><span data-stu-id="c5781-224">mvc</span></span>](#web-options)             | <span data-ttu-id="c5781-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c5781-225">[C#], F#</span></span>     | <span data-ttu-id="c5781-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="c5781-226">Web/MVC</span></span>                               | <span data-ttu-id="c5781-227">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-227">1.0</span></span>        |
| <span data-ttu-id="c5781-228">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5781-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="c5781-229">webapp, rasoio</span><span class="sxs-lookup"><span data-stu-id="c5781-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="c5781-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-230">[C#]</span></span>         | <span data-ttu-id="c5781-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="c5781-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="c5781-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="c5781-233">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="c5781-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="c5781-234">Angolare</span><span class="sxs-lookup"><span data-stu-id="c5781-234">angular</span></span>](#spa)                 | <span data-ttu-id="c5781-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-235">[C#]</span></span>         | <span data-ttu-id="c5781-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c5781-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c5781-237">2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-237">2.0</span></span>        |
| <span data-ttu-id="c5781-238">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="c5781-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="c5781-239">Reagire</span><span class="sxs-lookup"><span data-stu-id="c5781-239">react</span></span>](#spa)                   | <span data-ttu-id="c5781-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-240">[C#]</span></span>         | <span data-ttu-id="c5781-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c5781-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c5781-242">2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-242">2.0</span></span>        |
| <span data-ttu-id="c5781-243">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="c5781-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="c5781-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="c5781-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="c5781-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-245">[C#]</span></span>         | <span data-ttu-id="c5781-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c5781-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c5781-247">2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-247">2.0</span></span>        |
| <span data-ttu-id="c5781-248">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="c5781-248">Razor Class Library</span></span>                          | [<span data-ttu-id="c5781-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c5781-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="c5781-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-250">[C#]</span></span>         | <span data-ttu-id="c5781-251">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="c5781-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="c5781-252">2.1</span><span class="sxs-lookup"><span data-stu-id="c5781-252">2.1</span></span>        |
| <span data-ttu-id="c5781-253">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c5781-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="c5781-254">webapi</span><span class="sxs-lookup"><span data-stu-id="c5781-254">webapi</span></span>](#webapi)               | <span data-ttu-id="c5781-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c5781-255">[C#], F#</span></span>     | <span data-ttu-id="c5781-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="c5781-256">Web/WebAPI</span></span>                            | <span data-ttu-id="c5781-257">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-257">1.0</span></span>        |
| <span data-ttu-id="c5781-258">ASP.NET core del servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="c5781-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="c5781-259">grpc</span><span class="sxs-lookup"><span data-stu-id="c5781-259">grpc</span></span>](#web-others)             | <span data-ttu-id="c5781-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="c5781-260">[C#]</span></span>         | <span data-ttu-id="c5781-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c5781-261">Web/gRPC</span></span>                              | <span data-ttu-id="c5781-262">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-262">3.0</span></span>        |
| <span data-ttu-id="c5781-263">File buffer protocollo</span><span class="sxs-lookup"><span data-stu-id="c5781-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="c5781-264">Proto</span><span class="sxs-lookup"><span data-stu-id="c5781-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="c5781-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c5781-265">Web/gRPC</span></span>                              | <span data-ttu-id="c5781-266">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-266">3.0</span></span>        |
| <span data-ttu-id="c5781-267">file gitignore dotnet</span><span class="sxs-lookup"><span data-stu-id="c5781-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="c5781-268">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c5781-268">Config</span></span>                                | <span data-ttu-id="c5781-269">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-269">3.0</span></span>        |
| <span data-ttu-id="c5781-270">File global.json</span><span class="sxs-lookup"><span data-stu-id="c5781-270">global.json file</span></span>                             | [<span data-ttu-id="c5781-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="c5781-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="c5781-272">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c5781-272">Config</span></span>                                | <span data-ttu-id="c5781-273">2.0</span><span class="sxs-lookup"><span data-stu-id="c5781-273">2.0</span></span>        |
| <span data-ttu-id="c5781-274">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="c5781-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="c5781-275">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c5781-275">Config</span></span>                                | <span data-ttu-id="c5781-276">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-276">1.0</span></span>        |
| <span data-ttu-id="c5781-277">dotnet file manifesto dello strumento locale</span><span class="sxs-lookup"><span data-stu-id="c5781-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="c5781-278">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c5781-278">Config</span></span>                                | <span data-ttu-id="c5781-279">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-279">3.0</span></span>        |
| <span data-ttu-id="c5781-280">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="c5781-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="c5781-281">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c5781-281">Config</span></span>                                | <span data-ttu-id="c5781-282">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-282">1.0</span></span>        |
| <span data-ttu-id="c5781-283">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="c5781-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="c5781-284">Soluzione</span><span class="sxs-lookup"><span data-stu-id="c5781-284">Solution</span></span>                              | <span data-ttu-id="c5781-285">1.0</span><span class="sxs-lookup"><span data-stu-id="c5781-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="c5781-286">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c5781-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="c5781-287">Visualizza un riepilogo di ciò che accadrebbe se il comando specificato venisse eseguito.</span><span class="sxs-lookup"><span data-stu-id="c5781-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="c5781-288">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="c5781-289">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="c5781-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c5781-290">Questa operazione è necessaria quando il modello scelto sovrascriverà i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="c5781-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c5781-291">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c5781-291">Prints out help for the command.</span></span> <span data-ttu-id="c5781-292">Può essere richiamato `dotnet new` per il comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="c5781-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="c5781-293">Ad esempio: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c5781-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="c5781-294">Installa un pacchetto di `PATH` `NUGET_ID` modelli da o fornito.</span><span class="sxs-lookup"><span data-stu-id="c5781-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c5781-295">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="c5781-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c5781-296">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione del pacchetto stabile più recente.</span><span class="sxs-lookup"><span data-stu-id="c5781-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="c5781-297">Vedere un esempio nella sezione [Esempi.See](#examples) an example in the Examples section.</span><span class="sxs-lookup"><span data-stu-id="c5781-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="c5781-298">Se una versione del modello è già stata installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="c5781-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="c5781-299">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c5781-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="c5781-300">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="c5781-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="c5781-301">Se non viene specificato alcun nome, vengono elencati tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="c5781-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="c5781-302">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="c5781-302">The language of the template to create.</span></span> <span data-ttu-id="c5781-303">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="c5781-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c5781-304">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="c5781-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5781-305">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="c5781-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c5781-306">In questi casi, racchiudere il valore del parametro del linguaggio tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="c5781-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="c5781-307">Ad esempio: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c5781-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="c5781-308">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="c5781-308">The name for the created output.</span></span> <span data-ttu-id="c5781-309">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c5781-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="c5781-310">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="c5781-311">Disponibile da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c5781-312">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-312">Location to place the generated output.</span></span> <span data-ttu-id="c5781-313">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c5781-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="c5781-314">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="c5781-314">Filters templates based on available types.</span></span> <span data-ttu-id="c5781-315">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="c5781-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="c5781-316">Disinstalla un pacchetto di `PATH` `NUGET_ID` modelli nel file o fornito.</span><span class="sxs-lookup"><span data-stu-id="c5781-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c5781-317">Quando `<PATH|NUGET_ID>` il valore non è specificato, vengono visualizzati tutti i modelli di modello attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="c5781-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="c5781-318">Quando si `NUGET_ID`specifica , non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="c5781-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="c5781-319">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="c5781-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5781-320">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="c5781-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c5781-321">Ad esempio, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che la contiene non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="c5781-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="c5781-322">Non includere una barra di terminazione finale nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="c5781-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="c5781-323">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="c5781-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="c5781-324">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="c5781-325">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="c5781-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="c5781-326">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="c5781-327">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="c5781-327">Template options</span></span>

<span data-ttu-id="c5781-328">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c5781-328">Each project template may have additional options available.</span></span> <span data-ttu-id="c5781-329">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5781-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="c5781-330">console</span><span class="sxs-lookup"><span data-stu-id="c5781-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-331">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-332">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c5781-333">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-334">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-334">SDK version</span></span> | <span data-ttu-id="c5781-335">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-336">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-337">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c5781-338">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="c5781-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c5781-339">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c5781-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c5781-340">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="c5781-340">Not supported for F#.</span></span> <span data-ttu-id="c5781-341">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c5781-342">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c5781-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-343">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="c5781-344">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="c5781-345">classlib</span><span class="sxs-lookup"><span data-stu-id="c5781-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-346">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-347">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c5781-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c5781-348">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c5781-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c5781-349">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="c5781-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c5781-350">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c5781-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c5781-351">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="c5781-351">Not supported for F#.</span></span> <span data-ttu-id="c5781-352">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c5781-353">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c5781-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-354">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a><span data-ttu-id="c5781-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="c5781-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-356">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-357">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="c5781-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c5781-358">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c5781-359">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="c5781-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c5781-360">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c5781-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c5781-361">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c5781-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-362">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a><span data-ttu-id="c5781-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="c5781-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c5781-364">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="c5781-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c5781-365">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c5781-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c5781-366">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c5781-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-367">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a><span data-ttu-id="c5781-368">lavoratore, grpc</span><span class="sxs-lookup"><span data-stu-id="c5781-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-369">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-370">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="c5781-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c5781-371">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c5781-372">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-373">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a><span data-ttu-id="c5781-374">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="c5781-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-375">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-376">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c5781-377">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-378">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-378">SDK version</span></span> | <span data-ttu-id="c5781-379">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-380">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-381">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c5781-382">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c5781-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-383">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="c5781-384">Nunit</span><span class="sxs-lookup"><span data-stu-id="c5781-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-385">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="c5781-386">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-387">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-387">SDK version</span></span> | <span data-ttu-id="c5781-388">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-389">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-390">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c5781-391">2.2</span><span class="sxs-lookup"><span data-stu-id="c5781-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="c5781-392">2.1</span><span class="sxs-lookup"><span data-stu-id="c5781-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c5781-393">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c5781-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-394">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="c5781-395">pagina</span><span class="sxs-lookup"><span data-stu-id="c5781-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="c5781-396">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-396">Namespace for the generated code.</span></span> <span data-ttu-id="c5781-397">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c5781-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="c5781-398">Crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="c5781-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a><span data-ttu-id="c5781-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="c5781-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="c5781-400">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-400">Namespace for the generated code.</span></span> <span data-ttu-id="c5781-401">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c5781-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="c5781-402">blazorservere</span><span class="sxs-lookup"><span data-stu-id="c5781-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c5781-403">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="c5781-403">The type of authentication to use.</span></span> <span data-ttu-id="c5781-404">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="c5781-404">The possible values are:</span></span>

  - <span data-ttu-id="c5781-405">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="c5781-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c5781-406">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="c5781-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c5781-407">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c5781-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c5781-408">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="c5781-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c5781-409">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="c5781-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c5781-410">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c5781-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c5781-411">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c5781-412">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-413">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c5781-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c5781-414">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c5781-415">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c5781-416">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="c5781-417">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c5781-418">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c5781-419">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c5781-420">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c5781-421">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5781-422">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c5781-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c5781-423">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-423">The Client ID for this project.</span></span> <span data-ttu-id="c5781-424">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5781-425">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c5781-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c5781-426">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="c5781-426">The domain for the directory tenant.</span></span> <span data-ttu-id="c5781-427">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-428">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c5781-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c5781-429">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c5781-430">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5781-431">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c5781-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c5781-432">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="c5781-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c5781-433">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-434">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c5781-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c5781-435">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="c5781-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c5781-436">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c5781-437">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c5781-438">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c5781-438">Turns off HTTPS.</span></span> <span data-ttu-id="c5781-439">Questa opzione si `Individual` `IndividualB2C`applica `SingleOrg`solo `MultiOrg` se , , `--auth`o non vengono utilizzati per .</span><span class="sxs-lookup"><span data-stu-id="c5781-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c5781-440">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="c5781-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5781-441">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-442">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="c5781-443">Web</span><span class="sxs-lookup"><span data-stu-id="c5781-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c5781-444">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-445">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-446">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c5781-447">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-448">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-448">SDK version</span></span> | <span data-ttu-id="c5781-449">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-450">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-451">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c5781-452">2.1</span><span class="sxs-lookup"><span data-stu-id="c5781-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c5781-453">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c5781-454">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c5781-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a><span data-ttu-id="c5781-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="c5781-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c5781-456">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="c5781-456">The type of authentication to use.</span></span> <span data-ttu-id="c5781-457">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="c5781-457">The possible values are:</span></span>

  - <span data-ttu-id="c5781-458">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="c5781-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c5781-459">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="c5781-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c5781-460">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c5781-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c5781-461">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="c5781-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c5781-462">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="c5781-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c5781-463">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c5781-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c5781-464">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c5781-465">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-466">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c5781-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c5781-467">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c5781-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c5781-469">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="c5781-470">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c5781-471">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c5781-472">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c5781-473">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c5781-474">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5781-475">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c5781-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c5781-476">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-476">The Client ID for this project.</span></span> <span data-ttu-id="c5781-477">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c5781-478">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c5781-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c5781-479">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="c5781-479">The domain for the directory tenant.</span></span> <span data-ttu-id="c5781-480">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-481">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c5781-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c5781-482">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c5781-483">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5781-484">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c5781-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c5781-485">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="c5781-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c5781-486">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-487">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c5781-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c5781-488">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="c5781-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c5781-489">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c5781-490">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c5781-491">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c5781-491">Turns off HTTPS.</span></span> <span data-ttu-id="c5781-492">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="c5781-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c5781-493">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="c5781-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5781-494">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-495">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-496">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c5781-497">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-498">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-498">SDK version</span></span> | <span data-ttu-id="c5781-499">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-500">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-501">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="c5781-502">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="c5781-503">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="c5781-504">Opzione non disponibile in .NET Core 2.2 e 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a><span data-ttu-id="c5781-505">angolare, reagire</span><span class="sxs-lookup"><span data-stu-id="c5781-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c5781-506">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="c5781-506">The type of authentication to use.</span></span> <span data-ttu-id="c5781-507">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-507">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="c5781-508">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="c5781-508">The possible values are:</span></span>

  - <span data-ttu-id="c5781-509">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="c5781-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c5781-510">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="c5781-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c5781-511">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-511">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-512">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c5781-513">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c5781-513">Turns off HTTPS.</span></span> <span data-ttu-id="c5781-514">Questa opzione si applica `None`solo se l'autenticazione è .</span><span class="sxs-lookup"><span data-stu-id="c5781-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c5781-515">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="c5781-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5781-516">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-517">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-518">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-519">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c5781-520">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-521">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-521">SDK version</span></span> | <span data-ttu-id="c5781-522">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-523">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-524">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c5781-525">2.1</span><span class="sxs-lookup"><span data-stu-id="c5781-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="c5781-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="c5781-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c5781-527">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-527">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-528">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-529">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c5781-530">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-531">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-531">SDK version</span></span> | <span data-ttu-id="c5781-532">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-533">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-534">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c5781-535">2.1</span><span class="sxs-lookup"><span data-stu-id="c5781-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="c5781-536">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c5781-537">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c5781-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="c5781-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c5781-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="c5781-539">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="c5781-540">Supporta l'aggiunta di pagine e viste Razor tradizionali oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="c5781-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="c5781-541">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="c5781-542">webapi</span><span class="sxs-lookup"><span data-stu-id="c5781-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c5781-543">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="c5781-543">The type of authentication to use.</span></span> <span data-ttu-id="c5781-544">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="c5781-544">The possible values are:</span></span>

  - <span data-ttu-id="c5781-545">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="c5781-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c5781-546">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c5781-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c5781-547">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="c5781-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c5781-548">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c5781-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c5781-549">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c5781-550">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c5781-551">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c5781-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c5781-552">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c5781-553">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c5781-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c5781-554">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c5781-555">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5781-556">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c5781-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c5781-557">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-557">The Client ID for this project.</span></span> <span data-ttu-id="c5781-558">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c5781-559">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c5781-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c5781-560">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="c5781-560">The domain for the directory tenant.</span></span> <span data-ttu-id="c5781-561">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c5781-562">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c5781-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c5781-563">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="c5781-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c5781-564">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c5781-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c5781-565">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c5781-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c5781-566">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="c5781-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c5781-567">Si applica `SingleOrg` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c5781-568">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="c5781-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c5781-569">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c5781-569">Turns off HTTPS.</span></span> <span data-ttu-id="c5781-570">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="c5781-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c5781-571">Questa opzione si `IndividualB2C` `SingleOrg` applica solo se o non vengono utilizzati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c5781-572">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="c5781-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c5781-573">Si applica `IndividualB2C` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c5781-574">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5781-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c5781-575">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c5781-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c5781-576">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="c5781-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c5781-577">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="c5781-577">SDK version</span></span> | <span data-ttu-id="c5781-578">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5781-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c5781-579">3.1</span><span class="sxs-lookup"><span data-stu-id="c5781-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c5781-580">3.0</span><span class="sxs-lookup"><span data-stu-id="c5781-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c5781-581">2.1</span><span class="sxs-lookup"><span data-stu-id="c5781-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c5781-582">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5781-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="c5781-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="c5781-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="c5781-584">Specifica la versione di .NET Core SDK da utilizzare nel file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="c5781-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="c5781-585">Esempi</span><span class="sxs-lookup"><span data-stu-id="c5781-585">Examples</span></span>

- <span data-ttu-id="c5781-586">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="c5781-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="c5781-587">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="c5781-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="c5781-588">Creare un progetto di libreria di classi .NET Standard nella directory specificata:Create a .NET Standard class library project in the specified directory:</span><span class="sxs-lookup"><span data-stu-id="c5781-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="c5781-589">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="c5781-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="c5781-590">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="c5781-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="c5781-591">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="c5781-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="c5781-592">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="c5781-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="c5781-593">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="c5781-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="c5781-594">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="c5781-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="c5781-595">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="c5781-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="c5781-596">Installare la versione 2.0 dei modelli SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="c5781-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="c5781-597">Elencare i modelli installati e i dettagli su di essi, tra cui come disinstallarli:</span><span class="sxs-lookup"><span data-stu-id="c5781-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="c5781-598">Creare un *file global.json* nella directory corrente impostando la versione SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="c5781-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="c5781-599">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5781-599">See also</span></span>

- [<span data-ttu-id="c5781-600">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="c5781-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="c5781-601">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="c5781-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="c5781-602">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="c5781-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="c5781-603">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="c5781-603">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
