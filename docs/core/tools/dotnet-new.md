---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 04/10/2020
ms.openlocfilehash: 4ad0d7e54f93582237ed9457b562957018916d36
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463608"
---
# <a name="dotnet-new"></a><span data-ttu-id="ef05f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ef05f-103">dotnet new</span></span>

<span data-ttu-id="ef05f-104">**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="ef05f-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ef05f-105">Nome</span><span class="sxs-lookup"><span data-stu-id="ef05f-105">Name</span></span>

<span data-ttu-id="ef05f-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ef05f-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ef05f-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="ef05f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef05f-108">Description</span></span>

<span data-ttu-id="ef05f-109">Il `dotnet new` comando crea un progetto .NET Core o altri elementi basati su un modello.</span><span class="sxs-lookup"><span data-stu-id="ef05f-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="ef05f-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="ef05f-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="ef05f-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ef05f-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="ef05f-112">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="ef05f-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="ef05f-113">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="ef05f-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="ef05f-114">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="ef05f-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="ef05f-115">È possibile `dotnet new --list` eseguire per visualizzare un elenco di tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="ef05f-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="ef05f-116">Se `TEMPLATE` il valore non corrisponde esattamente al testo nella colonna **Templates** o **Short Name** della tabella restituita, viene eseguita una corrispondenza di sottostringhe su queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="ef05f-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="ef05f-117">A partire da .NET Core 3.0 SDK, l'interfaccia `dotnet new` della riga di comando cerca i modelli in NuGet.org quando si richiama il comando nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef05f-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="ef05f-118">Se l'interfaccia della riga di comando `dotnet new`non riesce a trovare una corrispondenza del modello quando si richiama , nemmeno parziale.</span><span class="sxs-lookup"><span data-stu-id="ef05f-118">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="ef05f-119">Se è disponibile una versione più recente del modello.</span><span class="sxs-lookup"><span data-stu-id="ef05f-119">If there's a newer version of the template available.</span></span> <span data-ttu-id="ef05f-120">In questo caso, il progetto o l'elemento viene creato, ma l'interfaccia della riga di comando avvisa l'utente di una versione aggiornata del modello.</span><span class="sxs-lookup"><span data-stu-id="ef05f-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="ef05f-121">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="ef05f-121">The command contains a default list of templates.</span></span> <span data-ttu-id="ef05f-122">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="ef05f-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="ef05f-123">Nella tabella seguente vengono illustrati i modelli preinstallati con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="ef05f-124">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="ef05f-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="ef05f-125">Fare clic sul collegamento del nome breve per visualizzare le opzioni del modello specifico.</span><span class="sxs-lookup"><span data-stu-id="ef05f-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="ef05f-126">Modelli</span><span class="sxs-lookup"><span data-stu-id="ef05f-126">Templates</span></span>                                    | <span data-ttu-id="ef05f-127">Nome breve</span><span class="sxs-lookup"><span data-stu-id="ef05f-127">Short name</span></span>                      | <span data-ttu-id="ef05f-128">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="ef05f-128">Language</span></span>     | <span data-ttu-id="ef05f-129">Tag</span><span class="sxs-lookup"><span data-stu-id="ef05f-129">Tags</span></span>                                  | <span data-ttu-id="ef05f-130">Presentare</span><span class="sxs-lookup"><span data-stu-id="ef05f-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="ef05f-131">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="ef05f-131">Console Application</span></span>                          | [<span data-ttu-id="ef05f-132">Console</span><span class="sxs-lookup"><span data-stu-id="ef05f-132">console</span></span>](#console)             | <span data-ttu-id="ef05f-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ef05f-133">[C#], F#, VB</span></span> | <span data-ttu-id="ef05f-134">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="ef05f-134">Common/Console</span></span>                        | <span data-ttu-id="ef05f-135">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-135">1.0</span></span>        |
| <span data-ttu-id="ef05f-136">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="ef05f-136">Class library</span></span>                                | [<span data-ttu-id="ef05f-137">classlib</span><span class="sxs-lookup"><span data-stu-id="ef05f-137">classlib</span></span>](#classlib)           | <span data-ttu-id="ef05f-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ef05f-138">[C#], F#, VB</span></span> | <span data-ttu-id="ef05f-139">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="ef05f-139">Common/Library</span></span>                        | <span data-ttu-id="ef05f-140">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-140">1.0</span></span>        |
| <span data-ttu-id="ef05f-141">Applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="ef05f-141">WPF Application</span></span>                              | [<span data-ttu-id="ef05f-142">Wpf</span><span class="sxs-lookup"><span data-stu-id="ef05f-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="ef05f-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-143">[C#]</span></span>         | <span data-ttu-id="ef05f-144">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="ef05f-144">Common/WPF</span></span>                            | <span data-ttu-id="ef05f-145">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-145">3.0</span></span>        |
| <span data-ttu-id="ef05f-146">Libreria di classi WPFWPF Class library</span><span class="sxs-lookup"><span data-stu-id="ef05f-146">WPF Class library</span></span>                            | [<span data-ttu-id="ef05f-147">wpflib (libreria)</span><span class="sxs-lookup"><span data-stu-id="ef05f-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="ef05f-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-148">[C#]</span></span>         | <span data-ttu-id="ef05f-149">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="ef05f-149">Common/WPF</span></span>                            | <span data-ttu-id="ef05f-150">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-150">3.0</span></span>        |
| <span data-ttu-id="ef05f-151">Libreria di controlli personalizzati WPF</span><span class="sxs-lookup"><span data-stu-id="ef05f-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="ef05f-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="ef05f-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="ef05f-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-153">[C#]</span></span>         | <span data-ttu-id="ef05f-154">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="ef05f-154">Common/WPF</span></span>                            | <span data-ttu-id="ef05f-155">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-155">3.0</span></span>        |
| <span data-ttu-id="ef05f-156">Libreria di controlli utente WPF</span><span class="sxs-lookup"><span data-stu-id="ef05f-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="ef05f-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="ef05f-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="ef05f-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-158">[C#]</span></span>         | <span data-ttu-id="ef05f-159">Comune/WPF</span><span class="sxs-lookup"><span data-stu-id="ef05f-159">Common/WPF</span></span>                            | <span data-ttu-id="ef05f-160">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-160">3.0</span></span>        |
| <span data-ttu-id="ef05f-161">Applicazione Windows Form (WinForms)</span><span class="sxs-lookup"><span data-stu-id="ef05f-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="ef05f-162">Winforms</span><span class="sxs-lookup"><span data-stu-id="ef05f-162">winforms</span></span>](#winforms)           | <span data-ttu-id="ef05f-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-163">[C#]</span></span>         | <span data-ttu-id="ef05f-164">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="ef05f-164">Common/WinForms</span></span>                       | <span data-ttu-id="ef05f-165">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-165">3.0</span></span>        |
| <span data-ttu-id="ef05f-166">Libreria di classi Windows Form (WindowsForms)</span><span class="sxs-lookup"><span data-stu-id="ef05f-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="ef05f-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="ef05f-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="ef05f-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-168">[C#]</span></span>         | <span data-ttu-id="ef05f-169">Comune/WinForms</span><span class="sxs-lookup"><span data-stu-id="ef05f-169">Common/WinForms</span></span>                       | <span data-ttu-id="ef05f-170">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-170">3.0</span></span>        |
| <span data-ttu-id="ef05f-171">Servizio di lavoro</span><span class="sxs-lookup"><span data-stu-id="ef05f-171">Worker Service</span></span>                               | [<span data-ttu-id="ef05f-172">Lavoratore</span><span class="sxs-lookup"><span data-stu-id="ef05f-172">worker</span></span>](#web-others)           | <span data-ttu-id="ef05f-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-173">[C#]</span></span>         | <span data-ttu-id="ef05f-174">Comune/Lavoratore/Web</span><span class="sxs-lookup"><span data-stu-id="ef05f-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="ef05f-175">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-175">3.0</span></span>        |
| <span data-ttu-id="ef05f-176">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="ef05f-176">Unit Test Project</span></span>                            | [<span data-ttu-id="ef05f-177">Mstest</span><span class="sxs-lookup"><span data-stu-id="ef05f-177">mstest</span></span>](#test)                 | <span data-ttu-id="ef05f-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ef05f-178">[C#], F#, VB</span></span> | <span data-ttu-id="ef05f-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="ef05f-179">Test/MSTest</span></span>                           | <span data-ttu-id="ef05f-180">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-180">1.0</span></span>        |
| <span data-ttu-id="ef05f-181">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="ef05f-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="ef05f-182">Nunit</span><span class="sxs-lookup"><span data-stu-id="ef05f-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="ef05f-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ef05f-183">[C#], F#, VB</span></span> | <span data-ttu-id="ef05f-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="ef05f-184">Test/NUnit</span></span>                            | <span data-ttu-id="ef05f-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="ef05f-185">2.1.400</span></span>    |
| <span data-ttu-id="ef05f-186">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="ef05f-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="ef05f-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ef05f-187">[C#], F#, VB</span></span> | <span data-ttu-id="ef05f-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="ef05f-188">Test/NUnit</span></span>                            | <span data-ttu-id="ef05f-189">2.2</span><span class="sxs-lookup"><span data-stu-id="ef05f-189">2.2</span></span>        |
| <span data-ttu-id="ef05f-190">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="ef05f-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="ef05f-191">xunit</span><span class="sxs-lookup"><span data-stu-id="ef05f-191">xunit</span></span>](#test)                  | <span data-ttu-id="ef05f-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ef05f-192">[C#], F#, VB</span></span> | <span data-ttu-id="ef05f-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="ef05f-193">Test/xUnit</span></span>                            | <span data-ttu-id="ef05f-194">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-194">1.0</span></span>        |
| <span data-ttu-id="ef05f-195">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="ef05f-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="ef05f-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-196">[C#]</span></span>         | <span data-ttu-id="ef05f-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ef05f-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="ef05f-198">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-198">3.0</span></span>        |
| <span data-ttu-id="ef05f-199">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="ef05f-199">Razor Page</span></span>                                   | [<span data-ttu-id="ef05f-200">Pagina</span><span class="sxs-lookup"><span data-stu-id="ef05f-200">page</span></span>](#page)                   | <span data-ttu-id="ef05f-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-201">[C#]</span></span>         | <span data-ttu-id="ef05f-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ef05f-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="ef05f-203">2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-203">2.0</span></span>        |
| <span data-ttu-id="ef05f-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="ef05f-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="ef05f-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="ef05f-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="ef05f-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-206">[C#]</span></span>         | <span data-ttu-id="ef05f-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ef05f-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="ef05f-208">2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-208">2.0</span></span>        |
| <span data-ttu-id="ef05f-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="ef05f-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="ef05f-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-210">[C#]</span></span>         | <span data-ttu-id="ef05f-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ef05f-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="ef05f-212">2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-212">2.0</span></span>        |
| <span data-ttu-id="ef05f-213">Blazor Server App</span><span class="sxs-lookup"><span data-stu-id="ef05f-213">Blazor Server App</span></span>                            | [<span data-ttu-id="ef05f-214">blazorservere</span><span class="sxs-lookup"><span data-stu-id="ef05f-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="ef05f-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-215">[C#]</span></span>         | <span data-ttu-id="ef05f-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="ef05f-216">Web/Blazor</span></span>                            | <span data-ttu-id="ef05f-217">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-217">3.0</span></span>        |
| <span data-ttu-id="ef05f-218">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="ef05f-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="ef05f-219">Web</span><span class="sxs-lookup"><span data-stu-id="ef05f-219">web</span></span>](#web)                     | <span data-ttu-id="ef05f-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ef05f-220">[C#], F#</span></span>     | <span data-ttu-id="ef05f-221">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="ef05f-221">Web/Empty</span></span>                             | <span data-ttu-id="ef05f-222">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-222">1.0</span></span>        |
| <span data-ttu-id="ef05f-223">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="ef05f-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="ef05f-224">Mvc</span><span class="sxs-lookup"><span data-stu-id="ef05f-224">mvc</span></span>](#web-options)             | <span data-ttu-id="ef05f-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ef05f-225">[C#], F#</span></span>     | <span data-ttu-id="ef05f-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="ef05f-226">Web/MVC</span></span>                               | <span data-ttu-id="ef05f-227">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-227">1.0</span></span>        |
| <span data-ttu-id="ef05f-228">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ef05f-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="ef05f-229">webapp, rasoio</span><span class="sxs-lookup"><span data-stu-id="ef05f-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="ef05f-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-230">[C#]</span></span>         | <span data-ttu-id="ef05f-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="ef05f-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="ef05f-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="ef05f-233">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="ef05f-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="ef05f-234">Angolare</span><span class="sxs-lookup"><span data-stu-id="ef05f-234">angular</span></span>](#spa)                 | <span data-ttu-id="ef05f-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-235">[C#]</span></span>         | <span data-ttu-id="ef05f-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ef05f-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ef05f-237">2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-237">2.0</span></span>        |
| <span data-ttu-id="ef05f-238">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="ef05f-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="ef05f-239">Reagire</span><span class="sxs-lookup"><span data-stu-id="ef05f-239">react</span></span>](#spa)                   | <span data-ttu-id="ef05f-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-240">[C#]</span></span>         | <span data-ttu-id="ef05f-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ef05f-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ef05f-242">2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-242">2.0</span></span>        |
| <span data-ttu-id="ef05f-243">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="ef05f-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="ef05f-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="ef05f-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="ef05f-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-245">[C#]</span></span>         | <span data-ttu-id="ef05f-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="ef05f-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="ef05f-247">2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-247">2.0</span></span>        |
| <span data-ttu-id="ef05f-248">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="ef05f-248">Razor Class Library</span></span>                          | [<span data-ttu-id="ef05f-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="ef05f-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="ef05f-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-250">[C#]</span></span>         | <span data-ttu-id="ef05f-251">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="ef05f-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="ef05f-252">2.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-252">2.1</span></span>        |
| <span data-ttu-id="ef05f-253">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ef05f-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="ef05f-254">webapi</span><span class="sxs-lookup"><span data-stu-id="ef05f-254">webapi</span></span>](#webapi)               | <span data-ttu-id="ef05f-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ef05f-255">[C#], F#</span></span>     | <span data-ttu-id="ef05f-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="ef05f-256">Web/WebAPI</span></span>                            | <span data-ttu-id="ef05f-257">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-257">1.0</span></span>        |
| <span data-ttu-id="ef05f-258">ASP.NET core del servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="ef05f-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="ef05f-259">grpc</span><span class="sxs-lookup"><span data-stu-id="ef05f-259">grpc</span></span>](#web-others)             | <span data-ttu-id="ef05f-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="ef05f-260">[C#]</span></span>         | <span data-ttu-id="ef05f-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="ef05f-261">Web/gRPC</span></span>                              | <span data-ttu-id="ef05f-262">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-262">3.0</span></span>        |
| <span data-ttu-id="ef05f-263">File buffer protocollo</span><span class="sxs-lookup"><span data-stu-id="ef05f-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="ef05f-264">Proto</span><span class="sxs-lookup"><span data-stu-id="ef05f-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="ef05f-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="ef05f-265">Web/gRPC</span></span>                              | <span data-ttu-id="ef05f-266">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-266">3.0</span></span>        |
| <span data-ttu-id="ef05f-267">file gitignore dotnet</span><span class="sxs-lookup"><span data-stu-id="ef05f-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="ef05f-268">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ef05f-268">Config</span></span>                                | <span data-ttu-id="ef05f-269">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-269">3.0</span></span>        |
| <span data-ttu-id="ef05f-270">File global.json</span><span class="sxs-lookup"><span data-stu-id="ef05f-270">global.json file</span></span>                             | [<span data-ttu-id="ef05f-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="ef05f-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="ef05f-272">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ef05f-272">Config</span></span>                                | <span data-ttu-id="ef05f-273">2.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-273">2.0</span></span>        |
| <span data-ttu-id="ef05f-274">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="ef05f-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="ef05f-275">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ef05f-275">Config</span></span>                                | <span data-ttu-id="ef05f-276">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-276">1.0</span></span>        |
| <span data-ttu-id="ef05f-277">dotnet file manifesto dello strumento locale</span><span class="sxs-lookup"><span data-stu-id="ef05f-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="ef05f-278">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ef05f-278">Config</span></span>                                | <span data-ttu-id="ef05f-279">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-279">3.0</span></span>        |
| <span data-ttu-id="ef05f-280">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="ef05f-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="ef05f-281">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ef05f-281">Config</span></span>                                | <span data-ttu-id="ef05f-282">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-282">1.0</span></span>        |
| <span data-ttu-id="ef05f-283">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="ef05f-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="ef05f-284">Soluzione</span><span class="sxs-lookup"><span data-stu-id="ef05f-284">Solution</span></span>                              | <span data-ttu-id="ef05f-285">1.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="ef05f-286">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ef05f-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="ef05f-287">Visualizza un riepilogo di ciò che accadrebbe se il comando specificato venisse eseguito.</span><span class="sxs-lookup"><span data-stu-id="ef05f-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="ef05f-288">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="ef05f-289">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="ef05f-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="ef05f-290">Questa operazione è necessaria quando il modello scelto sovrascriverà i file esistenti nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="ef05f-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ef05f-291">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="ef05f-291">Prints out help for the command.</span></span> <span data-ttu-id="ef05f-292">Può essere richiamato `dotnet new` per il comando stesso o per qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="ef05f-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="ef05f-293">Ad esempio: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="ef05f-294">Installa un pacchetto di `PATH` `NUGET_ID` modelli da o fornito.</span><span class="sxs-lookup"><span data-stu-id="ef05f-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ef05f-295">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="ef05f-296">Per impostazione predefinita, `dotnet new` passa \* per la versione, che rappresenta la versione del pacchetto stabile più recente.</span><span class="sxs-lookup"><span data-stu-id="ef05f-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="ef05f-297">Vedere un esempio nella sezione [Esempi.See](#examples) an example in the Examples section.</span><span class="sxs-lookup"><span data-stu-id="ef05f-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="ef05f-298">Se una versione del modello è già stata installata quando si esegue questo comando, il modello verrà aggiornato alla versione specificata o alla versione stabile più recente se non è stata specificata alcuna versione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="ef05f-299">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="ef05f-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="ef05f-300">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="ef05f-301">Se non viene specificato alcun nome, vengono elencati tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="ef05f-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="ef05f-302">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="ef05f-302">The language of the template to create.</span></span> <span data-ttu-id="ef05f-303">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="ef05f-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="ef05f-304">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="ef05f-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef05f-305">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="ef05f-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="ef05f-306">In questi casi, racchiudere il valore del parametro del linguaggio tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="ef05f-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="ef05f-307">Ad esempio: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="ef05f-308">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-308">The name for the created output.</span></span> <span data-ttu-id="ef05f-309">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="ef05f-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="ef05f-310">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="ef05f-311">Disponibile da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="ef05f-312">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-312">Location to place the generated output.</span></span> <span data-ttu-id="ef05f-313">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="ef05f-313">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="ef05f-314">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="ef05f-314">Filters templates based on available types.</span></span> <span data-ttu-id="ef05f-315">I valori `project`predefiniti `item`sono `other`, , o .</span><span class="sxs-lookup"><span data-stu-id="ef05f-315">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="ef05f-316">Disinstalla un pacchetto di `PATH` `NUGET_ID` modelli nel file o fornito.</span><span class="sxs-lookup"><span data-stu-id="ef05f-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ef05f-317">Quando `<PATH|NUGET_ID>` il valore non è specificato, vengono visualizzati tutti i modelli di modello attualmente installati e i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="ef05f-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="ef05f-318">Quando si `NUGET_ID`specifica , non includere il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="ef05f-319">Se non si specifica un parametro per questa opzione, il comando elenca i modelli installati e i relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="ef05f-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef05f-320">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="ef05f-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="ef05f-321">Ad esempio, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funzionerà, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella che la contiene non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="ef05f-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="ef05f-322">Non includere una barra di terminazione finale nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="ef05f-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="ef05f-323">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati e li installa.</span><span class="sxs-lookup"><span data-stu-id="ef05f-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="ef05f-324">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="ef05f-325">Controlla se sono disponibili aggiornamenti per i pacchetti modello attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="ef05f-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="ef05f-326">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="ef05f-327">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="ef05f-327">Template options</span></span>

<span data-ttu-id="ef05f-328">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ef05f-328">Each project template may have additional options available.</span></span> <span data-ttu-id="ef05f-329">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef05f-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="ef05f-330">console</span><span class="sxs-lookup"><span data-stu-id="ef05f-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-331">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-332">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ef05f-333">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-334">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-334">SDK version</span></span> | <span data-ttu-id="ef05f-335">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-336">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-337">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ef05f-338">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ef05f-339">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="ef05f-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="ef05f-340">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="ef05f-340">Not supported for F#.</span></span> <span data-ttu-id="ef05f-341">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ef05f-342">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="ef05f-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-343">Se specificato, non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="ef05f-344">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="ef05f-345">classlib</span><span class="sxs-lookup"><span data-stu-id="ef05f-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-346">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-347">Valori: `netcoreapp<version>` per creare una libreria di classi .NET Core o `netstandard<version>` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ef05f-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="ef05f-348">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ef05f-349">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ef05f-350">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="ef05f-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="ef05f-351">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="ef05f-351">Not supported for F#.</span></span> <span data-ttu-id="ef05f-352">Disponibile da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ef05f-353">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="ef05f-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-354">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a><span data-ttu-id="ef05f-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="ef05f-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-356">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-357">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="ef05f-358">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ef05f-359">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ef05f-360">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="ef05f-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="ef05f-361">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="ef05f-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-362">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a><span data-ttu-id="ef05f-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="ef05f-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="ef05f-364">Imposta `LangVersion` la proprietà nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="ef05f-365">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="ef05f-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="ef05f-366">Per un elenco delle versioni predefinite di C, vedere [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="ef05f-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-367">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a><span data-ttu-id="ef05f-368">lavoratore, grpc</span><span class="sxs-lookup"><span data-stu-id="ef05f-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-369">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-370">Il valore predefinito è `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="ef05f-371">Disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ef05f-372">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-373">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a><span data-ttu-id="ef05f-374">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="ef05f-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-375">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-376">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ef05f-377">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-378">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-378">SDK version</span></span> | <span data-ttu-id="ef05f-379">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-380">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-381">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="ef05f-382">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="ef05f-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-383">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="ef05f-384">Nunit</span><span class="sxs-lookup"><span data-stu-id="ef05f-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-385">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="ef05f-386">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-387">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-387">SDK version</span></span> | <span data-ttu-id="ef05f-388">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-389">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-390">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ef05f-391">2.2</span><span class="sxs-lookup"><span data-stu-id="ef05f-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="ef05f-392">2.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="ef05f-393">Abilita la creazione di pacchetti per il progetto utilizzando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="ef05f-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-394">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="ef05f-395">pagina</span><span class="sxs-lookup"><span data-stu-id="ef05f-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="ef05f-396">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-396">Namespace for the generated code.</span></span> <span data-ttu-id="ef05f-397">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="ef05f-398">Crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="ef05f-398">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a><span data-ttu-id="ef05f-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="ef05f-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="ef05f-400">Spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-400">Namespace for the generated code.</span></span> <span data-ttu-id="ef05f-401">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="ef05f-402">blazorservere</span><span class="sxs-lookup"><span data-stu-id="ef05f-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ef05f-403">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="ef05f-403">The type of authentication to use.</span></span> <span data-ttu-id="ef05f-404">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="ef05f-404">The possible values are:</span></span>

  - <span data-ttu-id="ef05f-405">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="ef05f-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ef05f-406">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="ef05f-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="ef05f-407">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="ef05f-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ef05f-408">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="ef05f-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ef05f-409">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="ef05f-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="ef05f-410">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ef05f-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ef05f-411">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ef05f-412">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-413">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ef05f-414">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ef05f-415">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="ef05f-416">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="ef05f-417">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="ef05f-418">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="ef05f-419">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ef05f-420">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ef05f-421">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ef05f-422">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ef05f-423">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-423">The Client ID for this project.</span></span> <span data-ttu-id="ef05f-424">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ef05f-425">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ef05f-426">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="ef05f-426">The domain for the directory tenant.</span></span> <span data-ttu-id="ef05f-427">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-428">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ef05f-429">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ef05f-430">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ef05f-431">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="ef05f-432">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="ef05f-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ef05f-433">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-434">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ef05f-435">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="ef05f-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ef05f-436">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ef05f-437">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ef05f-438">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef05f-438">Turns off HTTPS.</span></span> <span data-ttu-id="ef05f-439">Questa opzione si `Individual` `IndividualB2C`applica `SingleOrg`solo `MultiOrg` se , , `--auth`o non vengono utilizzati per .</span><span class="sxs-lookup"><span data-stu-id="ef05f-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ef05f-440">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="ef05f-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ef05f-441">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-442">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="ef05f-443">Web</span><span class="sxs-lookup"><span data-stu-id="ef05f-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ef05f-444">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-445">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-446">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ef05f-447">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-448">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-448">SDK version</span></span> | <span data-ttu-id="ef05f-449">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-450">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-451">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ef05f-452">2.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="ef05f-453">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ef05f-454">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef05f-454">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a><span data-ttu-id="ef05f-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="ef05f-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ef05f-456">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="ef05f-456">The type of authentication to use.</span></span> <span data-ttu-id="ef05f-457">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="ef05f-457">The possible values are:</span></span>

  - <span data-ttu-id="ef05f-458">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="ef05f-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ef05f-459">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="ef05f-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="ef05f-460">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="ef05f-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ef05f-461">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="ef05f-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ef05f-462">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="ef05f-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="ef05f-463">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ef05f-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ef05f-464">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ef05f-465">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-466">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ef05f-467">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ef05f-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="ef05f-469">ID criterio password di reimpostazione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="ef05f-470">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="ef05f-471">ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="ef05f-472">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ef05f-473">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ef05f-474">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ef05f-475">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ef05f-476">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-476">The Client ID for this project.</span></span> <span data-ttu-id="ef05f-477">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ef05f-478">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ef05f-479">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="ef05f-479">The domain for the directory tenant.</span></span> <span data-ttu-id="ef05f-480">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-481">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ef05f-482">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ef05f-483">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ef05f-484">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="ef05f-485">Percorso della richiesta all'interno del percorso di base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="ef05f-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ef05f-486">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-487">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ef05f-488">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="ef05f-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ef05f-489">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ef05f-490">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ef05f-491">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef05f-491">Turns off HTTPS.</span></span> <span data-ttu-id="ef05f-492">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="ef05f-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ef05f-493">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="ef05f-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ef05f-494">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-495">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-496">Opzione disponibile da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="ef05f-497">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-498">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-498">SDK version</span></span> | <span data-ttu-id="ef05f-499">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-500">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-501">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="ef05f-502">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="ef05f-503">Include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="ef05f-504">Opzione non disponibile in .NET Core 2.2 e 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="ef05f-505">Determina se il progetto è configurato per utilizzare la compilazione di [runtime Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) nelle compilazioni di debug.</span><span class="sxs-lookup"><span data-stu-id="ef05f-505">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="ef05f-506">Opzione disponibile da .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-506">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a><span data-ttu-id="ef05f-507">angolare, reagire</span><span class="sxs-lookup"><span data-stu-id="ef05f-507">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ef05f-508">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="ef05f-508">The type of authentication to use.</span></span> <span data-ttu-id="ef05f-509">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-509">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="ef05f-510">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="ef05f-510">The possible values are:</span></span>

  - <span data-ttu-id="ef05f-511">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="ef05f-511">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ef05f-512">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="ef05f-512">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ef05f-513">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-514">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-514">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ef05f-515">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef05f-515">Turns off HTTPS.</span></span> <span data-ttu-id="ef05f-516">Questa opzione si applica `None`solo se l'autenticazione è .</span><span class="sxs-lookup"><span data-stu-id="ef05f-516">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ef05f-517">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="ef05f-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ef05f-518">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-519">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-519">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-520">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-521">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-521">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ef05f-522">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-523">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-523">SDK version</span></span> | <span data-ttu-id="ef05f-524">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-525">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-526">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-526">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ef05f-527">2.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-527">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="ef05f-528">reactredux</span><span class="sxs-lookup"><span data-stu-id="ef05f-528">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ef05f-529">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-529">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-530">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-530">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-531">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-531">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ef05f-532">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-532">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-533">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-533">SDK version</span></span> | <span data-ttu-id="ef05f-534">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-534">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-535">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-535">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-536">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-536">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ef05f-537">2.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-537">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="ef05f-538">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-538">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="ef05f-539">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef05f-539">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="ef05f-540">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="ef05f-540">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="ef05f-541">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="ef05f-542">Supporta l'aggiunta di pagine e viste Razor tradizionali oltre ai componenti di questa libreria.</span><span class="sxs-lookup"><span data-stu-id="ef05f-542">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="ef05f-543">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-543">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="ef05f-544">webapi</span><span class="sxs-lookup"><span data-stu-id="ef05f-544">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="ef05f-545">Tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="ef05f-545">The type of authentication to use.</span></span> <span data-ttu-id="ef05f-546">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="ef05f-546">The possible values are:</span></span>

  - <span data-ttu-id="ef05f-547">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="ef05f-547">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="ef05f-548">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="ef05f-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="ef05f-549">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="ef05f-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="ef05f-550">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ef05f-550">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="ef05f-551">Istanza B2C di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-551">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ef05f-552">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-552">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ef05f-553">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-553">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="ef05f-554">ID del criterio di accesso e di iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-554">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ef05f-555">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-555">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="ef05f-556">Istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-556">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ef05f-557">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-557">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ef05f-558">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-558">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="ef05f-559">ID client per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-559">The Client ID for this project.</span></span> <span data-ttu-id="ef05f-560">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-560">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ef05f-561">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-561">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="ef05f-562">Dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="ef05f-562">The domain for the directory tenant.</span></span> <span data-ttu-id="ef05f-563">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ef05f-564">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-564">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="ef05f-565">ID TenantId della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ef05f-565">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ef05f-566">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-566">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ef05f-567">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-567">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="ef05f-568">Consente all'applicazione l'accesso in lettura alla directory.</span><span class="sxs-lookup"><span data-stu-id="ef05f-568">Allows this application read-access to the directory.</span></span> <span data-ttu-id="ef05f-569">Si applica `SingleOrg` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-569">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="ef05f-570">Esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="ef05f-570">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="ef05f-571">Disattiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ef05f-571">Turns off HTTPS.</span></span> <span data-ttu-id="ef05f-572">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="ef05f-572">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="ef05f-573">Questa opzione si `IndividualB2C` `SingleOrg` applica solo se o non vengono utilizzati per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-573">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="ef05f-574">Specifica che deve essere utilizzato LocalDB anziché SQLite.</span><span class="sxs-lookup"><span data-stu-id="ef05f-574">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ef05f-575">Si applica `IndividualB2C` solo all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-575">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ef05f-576">Specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ef05f-576">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ef05f-577">Opzione non disponibile in .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="ef05f-577">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="ef05f-578">Nella tabella seguente sono elencati i valori predefiniti in base al numero di versione SDK in uso:</span><span class="sxs-lookup"><span data-stu-id="ef05f-578">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="ef05f-579">Versione dell'SDK</span><span class="sxs-lookup"><span data-stu-id="ef05f-579">SDK version</span></span> | <span data-ttu-id="ef05f-580">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="ef05f-580">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="ef05f-581">3.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-581">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="ef05f-582">3.0</span><span class="sxs-lookup"><span data-stu-id="ef05f-582">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="ef05f-583">2.1</span><span class="sxs-lookup"><span data-stu-id="ef05f-583">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="ef05f-584">Non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="ef05f-584">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="ef05f-585">globaljson</span><span class="sxs-lookup"><span data-stu-id="ef05f-585">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="ef05f-586">Specifica la versione di .NET Core SDK da utilizzare nel file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="ef05f-586">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="ef05f-587">Esempi</span><span class="sxs-lookup"><span data-stu-id="ef05f-587">Examples</span></span>

- <span data-ttu-id="ef05f-588">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="ef05f-588">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="ef05f-589">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="ef05f-589">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="ef05f-590">Creare un progetto di libreria di classi .NET Standard nella directory specificata:Create a .NET Standard class library project in the specified directory:</span><span class="sxs-lookup"><span data-stu-id="ef05f-590">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="ef05f-591">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="ef05f-591">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="ef05f-592">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="ef05f-592">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="ef05f-593">Elencare tutti i modelli disponibili per i modelli di applicazione a pagina singola (SPA):</span><span class="sxs-lookup"><span data-stu-id="ef05f-593">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="ef05f-594">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="ef05f-594">List all templates matching the *we* substring.</span></span> <span data-ttu-id="ef05f-595">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="ef05f-595">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="ef05f-596">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="ef05f-596">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="ef05f-597">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="ef05f-597">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="ef05f-598">Installare la versione 2.0 dei modelli SPA per ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="ef05f-598">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="ef05f-599">Elencare i modelli installati e i dettagli su di essi, tra cui come disinstallarli:</span><span class="sxs-lookup"><span data-stu-id="ef05f-599">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="ef05f-600">Creare un *file global.json* nella directory corrente impostando la versione SDK su 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="ef05f-600">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="ef05f-601">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef05f-601">See also</span></span>

- [<span data-ttu-id="ef05f-602">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="ef05f-602">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="ef05f-603">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="ef05f-603">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="ef05f-604">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="ef05f-604">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="ef05f-605">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="ef05f-605">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
