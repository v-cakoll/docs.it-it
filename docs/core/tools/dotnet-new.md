---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 04/10/2020
ms.openlocfilehash: 1b1a6efa7bf2753b6c23cc7af1e26867f8632b96
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242881"
---
# <a name="dotnet-new"></a><span data-ttu-id="724fe-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="724fe-103">dotnet new</span></span>

<span data-ttu-id="724fe-104">**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="724fe-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="724fe-105">Nome</span><span class="sxs-lookup"><span data-stu-id="724fe-105">Name</span></span>

<span data-ttu-id="724fe-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="724fe-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="724fe-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="724fe-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="724fe-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="724fe-108">Description</span></span>

<span data-ttu-id="724fe-109">Il `dotnet new` comando crea un progetto .NET Core o altri elementi basati su un modello.</span><span class="sxs-lookup"><span data-stu-id="724fe-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="724fe-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="724fe-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="724fe-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="724fe-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="724fe-112">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="724fe-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="724fe-113">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="724fe-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="724fe-114">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="724fe-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="724fe-115">È possibile `dotnet new --list` eseguire per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="724fe-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="724fe-116">Se `TEMPLATE` il valore non corrisponde esattamente al testo nella colonna **Templates** o **Short Name** della tabella restituita, viene eseguita una corrispondenza di sottostringhe su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="724fe-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="724fe-117">A partire da .NET Core 3.0 SDK, l'interfaccia `dotnet new` della riga di comando cerca i modelli in NuGet.org quando si richiama il comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="724fe-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="724fe-118">Se l'interfaccia della riga di comando `dotnet new`non riesce a trovare una corrispondenza del modello quando si richiama , nemmeno parziale.</span><span class="sxs-lookup"><span data-stu-id="724fe-118">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="724fe-119">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="724fe-119">If there's a newer version of the template available.</span></span> <span data-ttu-id="724fe-120">In questo caso, il progetto o l'elemento viene creato, ma l'interfaccia della riga di comando avvisa l'utente di una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="724fe-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="724fe-121">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="724fe-121">The command contains a default list of templates.</span></span> <span data-ttu-id="724fe-122">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="724fe-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="724fe-123">Nella tabella seguente vengono illustrati i modelli preinstallati con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="724fe-124">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="724fe-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="724fe-125">Fare clic sul collegamento del nome breve per visualizzare le opzioni del modello specifico.</span><span class="sxs-lookup"><span data-stu-id="724fe-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="724fe-126">Modelli</span><span class="sxs-lookup"><span data-stu-id="724fe-126">Templates</span></span>                                    | <span data-ttu-id="724fe-127">Nome breve</span><span class="sxs-lookup"><span data-stu-id="724fe-127">Short name</span></span>                      | <span data-ttu-id="724fe-128">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="724fe-128">Language</span></span>     | <span data-ttu-id="724fe-129">Tag</span><span class="sxs-lookup"><span data-stu-id="724fe-129">Tags</span></span>                                  | <span data-ttu-id="724fe-130">Presentare</span><span class="sxs-lookup"><span data-stu-id="724fe-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="724fe-131">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="724fe-131">Console Application</span></span>                          | [<span data-ttu-id="724fe-132">Console</span><span class="sxs-lookup"><span data-stu-id="724fe-132">console</span></span>](#console)             | <span data-ttu-id="724fe-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="724fe-133">[C#], F#, VB</span></span> | <span data-ttu-id="724fe-134">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="724fe-134">Common/Console</span></span>                        | <span data-ttu-id="724fe-135">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-135">1.0</span></span>        |
| <span data-ttu-id="724fe-136">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="724fe-136">Class library</span></span>                                | [<span data-ttu-id="724fe-137">classlib</span><span class="sxs-lookup"><span data-stu-id="724fe-137">classlib</span></span>](#classlib)           | <span data-ttu-id="724fe-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="724fe-138">[C#], F#, VB</span></span> | <span data-ttu-id="724fe-139">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="724fe-139">Common/Library</span></span>                        | <span data-ttu-id="724fe-140">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-140">1.0</span></span>        |
| <span data-ttu-id="724fe-141">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="724fe-141">WPF Application</span></span>                              | [<span data-ttu-id="724fe-142">Wpf</span><span class="sxs-lookup"><span data-stu-id="724fe-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="724fe-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-143">[C#]</span></span>         | <span data-ttu-id="724fe-144">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="724fe-144">Common/WPF</span></span>                            | <span data-ttu-id="724fe-145">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-145">3.0</span></span>        |
| <span data-ttu-id="724fe-146">Libreria di classi WPFWPF Class library</span><span class="sxs-lookup"><span data-stu-id="724fe-146">WPF Class library</span></span>                            | [<span data-ttu-id="724fe-147">wpflib (libreria)</span><span class="sxs-lookup"><span data-stu-id="724fe-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="724fe-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-148">[C#]</span></span>         | <span data-ttu-id="724fe-149">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="724fe-149">Common/WPF</span></span>                            | <span data-ttu-id="724fe-150">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-150">3.0</span></span>        |
| <span data-ttu-id="724fe-151">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="724fe-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="724fe-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="724fe-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="724fe-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-153">[C#]</span></span>         | <span data-ttu-id="724fe-154">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="724fe-154">Common/WPF</span></span>                            | <span data-ttu-id="724fe-155">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-155">3.0</span></span>        |
| <span data-ttu-id="724fe-156">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="724fe-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="724fe-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="724fe-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="724fe-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-158">[C#]</span></span>         | <span data-ttu-id="724fe-159">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="724fe-159">Common/WPF</span></span>                            | <span data-ttu-id="724fe-160">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-160">3.0</span></span>        |
| <span data-ttu-id="724fe-161">Applicazione Windows Form (WinForms)</span><span class="sxs-lookup"><span data-stu-id="724fe-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="724fe-162">Winforms</span><span class="sxs-lookup"><span data-stu-id="724fe-162">winforms</span></span>](#winforms)           | <span data-ttu-id="724fe-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-163">[C#]</span></span>         | <span data-ttu-id="724fe-164">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="724fe-164">Common/WinForms</span></span>                       | <span data-ttu-id="724fe-165">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-165">3.0</span></span>        |
| <span data-ttu-id="724fe-166">Libreria di classi Windows Form (WindowsForms)</span><span class="sxs-lookup"><span data-stu-id="724fe-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="724fe-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="724fe-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="724fe-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-168">[C#]</span></span>         | <span data-ttu-id="724fe-169">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="724fe-169">Common/WinForms</span></span>                       | <span data-ttu-id="724fe-170">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-170">3.0</span></span>        |
| <span data-ttu-id="724fe-171">Servizio di lavoro</span><span class="sxs-lookup"><span data-stu-id="724fe-171">Worker Service</span></span>                               | [<span data-ttu-id="724fe-172">Lavoratore</span><span class="sxs-lookup"><span data-stu-id="724fe-172">worker</span></span>](#web-others)           | <span data-ttu-id="724fe-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-173">[C#]</span></span>         | <span data-ttu-id="724fe-174">Comune/Lavoratore/Web</span><span class="sxs-lookup"><span data-stu-id="724fe-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="724fe-175">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-175">3.0</span></span>        |
| <span data-ttu-id="724fe-176">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="724fe-176">Unit Test Project</span></span>                            | [<span data-ttu-id="724fe-177">Mstest</span><span class="sxs-lookup"><span data-stu-id="724fe-177">mstest</span></span>](#test)                 | <span data-ttu-id="724fe-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="724fe-178">[C#], F#, VB</span></span> | <span data-ttu-id="724fe-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="724fe-179">Test/MSTest</span></span>                           | <span data-ttu-id="724fe-180">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-180">1.0</span></span>        |
| <span data-ttu-id="724fe-181">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="724fe-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="724fe-182">Nunit</span><span class="sxs-lookup"><span data-stu-id="724fe-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="724fe-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="724fe-183">[C#], F#, VB</span></span> | <span data-ttu-id="724fe-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="724fe-184">Test/NUnit</span></span>                            | <span data-ttu-id="724fe-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="724fe-185">2.1.400</span></span>    |
| <span data-ttu-id="724fe-186">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="724fe-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="724fe-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="724fe-187">[C#], F#, VB</span></span> | <span data-ttu-id="724fe-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="724fe-188">Test/NUnit</span></span>                            | <span data-ttu-id="724fe-189">2.2</span><span class="sxs-lookup"><span data-stu-id="724fe-189">2.2</span></span>        |
| <span data-ttu-id="724fe-190">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="724fe-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="724fe-191">xunit</span><span class="sxs-lookup"><span data-stu-id="724fe-191">xunit</span></span>](#test)                  | <span data-ttu-id="724fe-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="724fe-192">[C#], F#, VB</span></span> | <span data-ttu-id="724fe-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="724fe-193">Test/xUnit</span></span>                            | <span data-ttu-id="724fe-194">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-194">1.0</span></span>        |
| <span data-ttu-id="724fe-195">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="724fe-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="724fe-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-196">[C#]</span></span>         | <span data-ttu-id="724fe-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="724fe-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="724fe-198">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-198">3.0</span></span>        |
| <span data-ttu-id="724fe-199">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="724fe-199">Razor Page</span></span>                                   | [<span data-ttu-id="724fe-200">Pagina</span><span class="sxs-lookup"><span data-stu-id="724fe-200">page</span></span>](#page)                   | <span data-ttu-id="724fe-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-201">[C#]</span></span>         | <span data-ttu-id="724fe-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="724fe-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="724fe-203">2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-203">2.0</span></span>        |
| <span data-ttu-id="724fe-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="724fe-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="724fe-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="724fe-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="724fe-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-206">[C#]</span></span>         | <span data-ttu-id="724fe-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="724fe-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="724fe-208">2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-208">2.0</span></span>        |
| <span data-ttu-id="724fe-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="724fe-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="724fe-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-210">[C#]</span></span>         | <span data-ttu-id="724fe-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="724fe-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="724fe-212">2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-212">2.0</span></span>        |
| <span data-ttu-id="724fe-213">Blazor Server App</span><span class="sxs-lookup"><span data-stu-id="724fe-213">Blazor Server App</span></span>                            | [<span data-ttu-id="724fe-214">blazorservere</span><span class="sxs-lookup"><span data-stu-id="724fe-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="724fe-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-215">[C#]</span></span>         | <span data-ttu-id="724fe-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="724fe-216">Web/Blazor</span></span>                            | <span data-ttu-id="724fe-217">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-217">3.0</span></span>        |
| <span data-ttu-id="724fe-218">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="724fe-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="724fe-219">Web</span><span class="sxs-lookup"><span data-stu-id="724fe-219">web</span></span>](#web)                     | <span data-ttu-id="724fe-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="724fe-220">[C#], F#</span></span>     | <span data-ttu-id="724fe-221">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="724fe-221">Web/Empty</span></span>                             | <span data-ttu-id="724fe-222">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-222">1.0</span></span>        |
| <span data-ttu-id="724fe-223">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="724fe-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="724fe-224">Mvc</span><span class="sxs-lookup"><span data-stu-id="724fe-224">mvc</span></span>](#web-options)             | <span data-ttu-id="724fe-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="724fe-225">[C#], F#</span></span>     | <span data-ttu-id="724fe-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="724fe-226">Web/MVC</span></span>                               | <span data-ttu-id="724fe-227">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-227">1.0</span></span>        |
| <span data-ttu-id="724fe-228">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="724fe-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="724fe-229">webapp, rasoio</span><span class="sxs-lookup"><span data-stu-id="724fe-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="724fe-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-230">[C#]</span></span>         | <span data-ttu-id="724fe-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="724fe-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="724fe-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="724fe-233">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="724fe-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="724fe-234">Angolare</span><span class="sxs-lookup"><span data-stu-id="724fe-234">angular</span></span>](#spa)                 | <span data-ttu-id="724fe-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-235">[C#]</span></span>         | <span data-ttu-id="724fe-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="724fe-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="724fe-237">2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-237">2.0</span></span>        |
| <span data-ttu-id="724fe-238">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="724fe-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="724fe-239">Reagire</span><span class="sxs-lookup"><span data-stu-id="724fe-239">react</span></span>](#spa)                   | <span data-ttu-id="724fe-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-240">[C#]</span></span>         | <span data-ttu-id="724fe-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="724fe-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="724fe-242">2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-242">2.0</span></span>        |
| <span data-ttu-id="724fe-243">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="724fe-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="724fe-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="724fe-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="724fe-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-245">[C#]</span></span>         | <span data-ttu-id="724fe-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="724fe-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="724fe-247">2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-247">2.0</span></span>        |
| <span data-ttu-id="724fe-248">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="724fe-248">Razor Class Library</span></span>                          | [<span data-ttu-id="724fe-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="724fe-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="724fe-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-250">[C#]</span></span>         | <span data-ttu-id="724fe-251">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="724fe-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="724fe-252">2.1</span><span class="sxs-lookup"><span data-stu-id="724fe-252">2.1</span></span>        |
| <span data-ttu-id="724fe-253">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="724fe-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="724fe-254">webapi</span><span class="sxs-lookup"><span data-stu-id="724fe-254">webapi</span></span>](#webapi)               | <span data-ttu-id="724fe-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="724fe-255">[C#], F#</span></span>     | <span data-ttu-id="724fe-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="724fe-256">Web/WebAPI</span></span>                            | <span data-ttu-id="724fe-257">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-257">1.0</span></span>        |
| <span data-ttu-id="724fe-258">ASP.NET core del servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="724fe-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="724fe-259">grpc</span><span class="sxs-lookup"><span data-stu-id="724fe-259">grpc</span></span>](#web-others)             | <span data-ttu-id="724fe-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="724fe-260">[C#]</span></span>         | <span data-ttu-id="724fe-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="724fe-261">Web/gRPC</span></span>                              | <span data-ttu-id="724fe-262">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-262">3.0</span></span>        |
| <span data-ttu-id="724fe-263">File buffer protocollo</span><span class="sxs-lookup"><span data-stu-id="724fe-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="724fe-264">Proto</span><span class="sxs-lookup"><span data-stu-id="724fe-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="724fe-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="724fe-265">Web/gRPC</span></span>                              | <span data-ttu-id="724fe-266">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-266">3.0</span></span>        |
| <span data-ttu-id="724fe-267">file gitignore dotnet</span><span class="sxs-lookup"><span data-stu-id="724fe-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="724fe-268">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="724fe-268">Config</span></span>                                | <span data-ttu-id="724fe-269">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-269">3.0</span></span>        |
| <span data-ttu-id="724fe-270">File global.json</span><span class="sxs-lookup"><span data-stu-id="724fe-270">global.json file</span></span>                             | [<span data-ttu-id="724fe-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="724fe-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="724fe-272">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="724fe-272">Config</span></span>                                | <span data-ttu-id="724fe-273">2.0</span><span class="sxs-lookup"><span data-stu-id="724fe-273">2.0</span></span>        |
| <span data-ttu-id="724fe-274">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="724fe-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="724fe-275">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="724fe-275">Config</span></span>                                | <span data-ttu-id="724fe-276">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-276">1.0</span></span>        |
| <span data-ttu-id="724fe-277">dotnet file manifesto dello strumento locale</span><span class="sxs-lookup"><span data-stu-id="724fe-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="724fe-278">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="724fe-278">Config</span></span>                                | <span data-ttu-id="724fe-279">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-279">3.0</span></span>        |
| <span data-ttu-id="724fe-280">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="724fe-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="724fe-281">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="724fe-281">Config</span></span>                                | <span data-ttu-id="724fe-282">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-282">1.0</span></span>        |
| <span data-ttu-id="724fe-283">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="724fe-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="724fe-284">Soluzione</span><span class="sxs-lookup"><span data-stu-id="724fe-284">Solution</span></span>                              | <span data-ttu-id="724fe-285">1.0</span><span class="sxs-lookup"><span data-stu-id="724fe-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="724fe-286">Opzioni</span><span class="sxs-lookup"><span data-stu-id="724fe-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="724fe-287">Visualizza un riepilogo di ciò che accadrebbe se il comando specificato venisse eseguito.</span><span class="sxs-lookup"><span data-stu-id="724fe-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="724fe-288">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="724fe-289">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="724fe-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="724fe-290">Questa operazione è necessaria quando il modello scelto sovrascriverà i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="724fe-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="724fe-291">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="724fe-291">Prints out help for the command.</span></span> <span data-ttu-id="724fe-292">Può essere richiamato `dotnet new` per il comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="724fe-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="724fe-293">Ad esempio: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="724fe-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="724fe-294">Installa un pacchetto di `PATH` `NUGET_ID` modelli da o fornito.</span><span class="sxs-lookup"><span data-stu-id="724fe-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="724fe-295">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="724fe-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="724fe-296">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione del pacchetto stabile più recente.</span><span class="sxs-lookup"><span data-stu-id="724fe-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="724fe-297">Vedere un esempio nella sezione [Esempi.See](#examples) an example in the Examples section.</span><span class="sxs-lookup"><span data-stu-id="724fe-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="724fe-298">Se una versione del modello è già stata installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="724fe-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="724fe-299">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="724fe-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="724fe-300">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="724fe-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="724fe-301">Se non viene specificato alcun nome, vengono elencati tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="724fe-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="724fe-302">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="724fe-302">The language of the template to create.</span></span> <span data-ttu-id="724fe-303">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="724fe-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="724fe-304">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="724fe-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="724fe-305">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="724fe-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="724fe-306">In questi casi, racchiudere il valore del parametro del linguaggio tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="724fe-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="724fe-307">Ad esempio: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="724fe-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="724fe-308">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="724fe-308">The name for the created output.</span></span> <span data-ttu-id="724fe-309">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="724fe-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="724fe-310">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="724fe-311">Disponibile da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="724fe-312">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-312">Location to place the generated output.</span></span> <span data-ttu-id="724fe-313">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="724fe-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="724fe-314">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="724fe-314">Filters templates based on available types.</span></span> <span data-ttu-id="724fe-315">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="724fe-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="724fe-316">Disinstalla un pacchetto di `PATH` `NUGET_ID` modelli nel file o fornito.</span><span class="sxs-lookup"><span data-stu-id="724fe-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="724fe-317">Quando `<PATH|NUGET_ID>` il valore non è specificato, vengono visualizzati tutti i modelli di modello attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="724fe-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="724fe-318">Quando si `NUGET_ID`specifica , non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="724fe-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="724fe-319">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="724fe-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="724fe-320">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="724fe-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="724fe-321">Ad esempio, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che la contiene non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="724fe-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="724fe-322">Non includere una barra di terminazione finale nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="724fe-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="724fe-323">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="724fe-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="724fe-324">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="724fe-325">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="724fe-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="724fe-326">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="724fe-327">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="724fe-327">Template options</span></span>

<span data-ttu-id="724fe-328">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="724fe-328">Each project template may have additional options available.</span></span> <span data-ttu-id="724fe-329">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="724fe-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="724fe-330">console</span><span class="sxs-lookup"><span data-stu-id="724fe-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-331">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-332">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="724fe-333">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-334">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-334">SDK version</span></span> | <span data-ttu-id="724fe-335">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-336">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-337">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="724fe-338">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="724fe-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="724fe-339">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="724fe-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="724fe-340">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="724fe-340">Not supported for F#.</span></span> <span data-ttu-id="724fe-341">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="724fe-342">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="724fe-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-343">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="724fe-344">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="724fe-345">classlib</span><span class="sxs-lookup"><span data-stu-id="724fe-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-346">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-347">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="724fe-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="724fe-348">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="724fe-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="724fe-349">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="724fe-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="724fe-350">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="724fe-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="724fe-351">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="724fe-351">Not supported for F#.</span></span> <span data-ttu-id="724fe-352">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="724fe-353">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="724fe-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-354">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a><span data-ttu-id="724fe-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="724fe-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-356">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-357">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="724fe-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="724fe-358">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="724fe-359">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="724fe-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="724fe-360">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="724fe-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="724fe-361">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="724fe-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-362">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a><span data-ttu-id="724fe-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="724fe-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="724fe-364">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="724fe-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="724fe-365">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="724fe-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="724fe-366">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="724fe-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-367">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a><span data-ttu-id="724fe-368">lavoratore, grpc</span><span class="sxs-lookup"><span data-stu-id="724fe-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-369">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-370">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="724fe-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="724fe-371">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="724fe-372">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-373">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="724fe-374">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="724fe-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-375">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-376">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="724fe-377">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-378">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-378">SDK version</span></span> | <span data-ttu-id="724fe-379">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-380">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-381">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="724fe-382">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="724fe-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-383">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="724fe-384">Nunit</span><span class="sxs-lookup"><span data-stu-id="724fe-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-385">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="724fe-386">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-387">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-387">SDK version</span></span> | <span data-ttu-id="724fe-388">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-389">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-390">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="724fe-391">2.2</span><span class="sxs-lookup"><span data-stu-id="724fe-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="724fe-392">2.1</span><span class="sxs-lookup"><span data-stu-id="724fe-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="724fe-393">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="724fe-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-394">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="724fe-395">pagina</span><span class="sxs-lookup"><span data-stu-id="724fe-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="724fe-396">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-396">Namespace for the generated code.</span></span> <span data-ttu-id="724fe-397">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="724fe-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="724fe-398">Crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="724fe-398">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a><span data-ttu-id="724fe-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="724fe-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="724fe-400">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-400">Namespace for the generated code.</span></span> <span data-ttu-id="724fe-401">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="724fe-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="724fe-402">blazorservere</span><span class="sxs-lookup"><span data-stu-id="724fe-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="724fe-403">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="724fe-403">The type of authentication to use.</span></span> <span data-ttu-id="724fe-404">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="724fe-404">The possible values are:</span></span>

  - <span data-ttu-id="724fe-405">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="724fe-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="724fe-406">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="724fe-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="724fe-407">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="724fe-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="724fe-408">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="724fe-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="724fe-409">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="724fe-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="724fe-410">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="724fe-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="724fe-411">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="724fe-412">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-413">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="724fe-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="724fe-414">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="724fe-415">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="724fe-416">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="724fe-417">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="724fe-418">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="724fe-419">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="724fe-420">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="724fe-421">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="724fe-422">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="724fe-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="724fe-423">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-423">The Client ID for this project.</span></span> <span data-ttu-id="724fe-424">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="724fe-425">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="724fe-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="724fe-426">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="724fe-426">The domain for the directory tenant.</span></span> <span data-ttu-id="724fe-427">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-428">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="724fe-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="724fe-429">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="724fe-430">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="724fe-431">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="724fe-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="724fe-432">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="724fe-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="724fe-433">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-434">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="724fe-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="724fe-435">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="724fe-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="724fe-436">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="724fe-437">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="724fe-438">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="724fe-438">Turns off HTTPS.</span></span> <span data-ttu-id="724fe-439">Questa opzione si `Individual` `IndividualB2C`applica `SingleOrg`solo `MultiOrg` se , , `--auth`o non vengono utilizzati per .</span><span class="sxs-lookup"><span data-stu-id="724fe-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="724fe-440">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="724fe-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="724fe-441">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-442">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="724fe-443">Web</span><span class="sxs-lookup"><span data-stu-id="724fe-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="724fe-444">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-445">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-446">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="724fe-447">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-448">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-448">SDK version</span></span> | <span data-ttu-id="724fe-449">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-450">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-451">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="724fe-452">2.1</span><span class="sxs-lookup"><span data-stu-id="724fe-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="724fe-453">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="724fe-454">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="724fe-454">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a><span data-ttu-id="724fe-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="724fe-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="724fe-456">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="724fe-456">The type of authentication to use.</span></span> <span data-ttu-id="724fe-457">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="724fe-457">The possible values are:</span></span>

  - <span data-ttu-id="724fe-458">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="724fe-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="724fe-459">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="724fe-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="724fe-460">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="724fe-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="724fe-461">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="724fe-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="724fe-462">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="724fe-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="724fe-463">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="724fe-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="724fe-464">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="724fe-465">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-466">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="724fe-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="724fe-467">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="724fe-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="724fe-469">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="724fe-470">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="724fe-471">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="724fe-472">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="724fe-473">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="724fe-474">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="724fe-475">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="724fe-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="724fe-476">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-476">The Client ID for this project.</span></span> <span data-ttu-id="724fe-477">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="724fe-478">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="724fe-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="724fe-479">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="724fe-479">The domain for the directory tenant.</span></span> <span data-ttu-id="724fe-480">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-481">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="724fe-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="724fe-482">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="724fe-483">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="724fe-484">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="724fe-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="724fe-485">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="724fe-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="724fe-486">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-487">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="724fe-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="724fe-488">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="724fe-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="724fe-489">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="724fe-490">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="724fe-491">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="724fe-491">Turns off HTTPS.</span></span> <span data-ttu-id="724fe-492">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="724fe-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="724fe-493">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="724fe-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="724fe-494">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-495">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-496">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="724fe-497">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-498">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-498">SDK version</span></span> | <span data-ttu-id="724fe-499">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-500">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-501">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="724fe-502">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="724fe-503">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="724fe-504">Opzione non disponibile in .NET Core 2.2 e 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="724fe-505">Determina se il progetto è configurato per utilizzare la compilazione di [runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle compilazioni di debug.</span><span class="sxs-lookup"><span data-stu-id="724fe-505">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="724fe-506">Opzione disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-506">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a><span data-ttu-id="724fe-507">angolare, reagire</span><span class="sxs-lookup"><span data-stu-id="724fe-507">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="724fe-508">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="724fe-508">The type of authentication to use.</span></span> <span data-ttu-id="724fe-509">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-509">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="724fe-510">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="724fe-510">The possible values are:</span></span>

  - <span data-ttu-id="724fe-511">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="724fe-511">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="724fe-512">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="724fe-512">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="724fe-513">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-514">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-514">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="724fe-515">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="724fe-515">Turns off HTTPS.</span></span> <span data-ttu-id="724fe-516">Questa opzione si applica `None`solo se l'autenticazione è .</span><span class="sxs-lookup"><span data-stu-id="724fe-516">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="724fe-517">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="724fe-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="724fe-518">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-519">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-519">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-520">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-521">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-521">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="724fe-522">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-523">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-523">SDK version</span></span> | <span data-ttu-id="724fe-524">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-525">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-526">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-526">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="724fe-527">2.1</span><span class="sxs-lookup"><span data-stu-id="724fe-527">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="724fe-528">reactredux</span><span class="sxs-lookup"><span data-stu-id="724fe-528">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="724fe-529">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-529">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-530">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-530">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-531">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-531">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="724fe-532">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-532">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-533">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-533">SDK version</span></span> | <span data-ttu-id="724fe-534">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-534">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-535">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-535">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-536">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-536">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="724fe-537">2.1</span><span class="sxs-lookup"><span data-stu-id="724fe-537">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="724fe-538">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-538">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="724fe-539">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="724fe-539">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="724fe-540">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="724fe-540">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="724fe-541">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="724fe-542">Supporta l'aggiunta di pagine e viste Razor tradizionali oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="724fe-542">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="724fe-543">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-543">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="724fe-544">webapi</span><span class="sxs-lookup"><span data-stu-id="724fe-544">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="724fe-545">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="724fe-545">The type of authentication to use.</span></span> <span data-ttu-id="724fe-546">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="724fe-546">The possible values are:</span></span>

  - <span data-ttu-id="724fe-547">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="724fe-547">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="724fe-548">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="724fe-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="724fe-549">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="724fe-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="724fe-550">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="724fe-550">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="724fe-551">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-551">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="724fe-552">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-552">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="724fe-553">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="724fe-553">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="724fe-554">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-554">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="724fe-555">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="724fe-555">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="724fe-556">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-556">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="724fe-557">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-557">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="724fe-558">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="724fe-558">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="724fe-559">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-559">The Client ID for this project.</span></span> <span data-ttu-id="724fe-560">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-560">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="724fe-561">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="724fe-561">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="724fe-562">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="724fe-562">The domain for the directory tenant.</span></span> <span data-ttu-id="724fe-563">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="724fe-564">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="724fe-564">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="724fe-565">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="724fe-565">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="724fe-566">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="724fe-566">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="724fe-567">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="724fe-567">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="724fe-568">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="724fe-568">Allows this application read-access to the directory.</span></span> <span data-ttu-id="724fe-569">Si applica `SingleOrg` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-569">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="724fe-570">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="724fe-570">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="724fe-571">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="724fe-571">Turns off HTTPS.</span></span> <span data-ttu-id="724fe-572">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="724fe-572">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="724fe-573">Questa opzione si `IndividualB2C` `SingleOrg` applica solo se o non vengono utilizzati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-573">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="724fe-574">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="724fe-574">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="724fe-575">Si applica `IndividualB2C` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-575">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="724fe-576">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="724fe-576">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="724fe-577">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="724fe-577">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="724fe-578">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="724fe-578">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="724fe-579">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="724fe-579">SDK version</span></span> | <span data-ttu-id="724fe-580">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="724fe-580">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="724fe-581">3.1</span><span class="sxs-lookup"><span data-stu-id="724fe-581">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="724fe-582">3.0</span><span class="sxs-lookup"><span data-stu-id="724fe-582">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="724fe-583">2.1</span><span class="sxs-lookup"><span data-stu-id="724fe-583">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="724fe-584">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="724fe-584">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="724fe-585">globaljson</span><span class="sxs-lookup"><span data-stu-id="724fe-585">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="724fe-586">Specifica la versione di .NET Core SDK da utilizzare nel file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="724fe-586">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="724fe-587">Esempi</span><span class="sxs-lookup"><span data-stu-id="724fe-587">Examples</span></span>

- <span data-ttu-id="724fe-588">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="724fe-588">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="724fe-589">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="724fe-589">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="724fe-590">Creare un progetto di libreria di classi .NET Standard nella directory specificata:Create a .NET Standard class library project in the specified directory:</span><span class="sxs-lookup"><span data-stu-id="724fe-590">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="724fe-591">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="724fe-591">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="724fe-592">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="724fe-592">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="724fe-593">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="724fe-593">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="724fe-594">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="724fe-594">List all templates matching the *we* substring.</span></span> <span data-ttu-id="724fe-595">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="724fe-595">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="724fe-596">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="724fe-596">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="724fe-597">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="724fe-597">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="724fe-598">Installare la versione 2.0 dei modelli SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="724fe-598">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="724fe-599">Elencare i modelli installati e i dettagli su di essi, tra cui come disinstallarli:</span><span class="sxs-lookup"><span data-stu-id="724fe-599">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="724fe-600">Creare un *file global.json* nella directory corrente impostando la versione SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="724fe-600">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="724fe-601">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="724fe-601">See also</span></span>

- [<span data-ttu-id="724fe-602">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="724fe-602">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="724fe-603">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="724fe-603">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="724fe-604">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="724fe-604">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="724fe-605">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="724fe-605">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
