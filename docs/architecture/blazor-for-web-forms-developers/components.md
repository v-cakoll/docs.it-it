---
title: Crea componenti dell'interfaccia utente riutilizzabili con blazer
description: Informazioni su come creare componenti dell'interfaccia utente riutilizzabili con blazer e su come vengono confrontati con i controlli Web Form ASP.NET.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 79fb2338a981389c3750e884ce6606351c84738a
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506766"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="ba9c3-103">Crea componenti dell'interfaccia utente riutilizzabili con blazer</span><span class="sxs-lookup"><span data-stu-id="ba9c3-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ba9c3-104">Uno degli aspetti più interessanti di ASP.NET Web Form è il modo in cui l'incapsulamento di parti riutilizzabili di codice dell'interfaccia utente in controlli dell'interfaccia utente riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="ba9c3-105">I controlli utente personalizzati possono essere definiti nel markup usando file con *estensione ascx* .</span><span class="sxs-lookup"><span data-stu-id="ba9c3-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="ba9c3-106">È anche possibile compilare controlli server elaborati nel codice con supporto completo della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="ba9c3-107">Blazer supporta anche l'incapsulamento dell'interfaccia utente tramite i *componenti*.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="ba9c3-108">Un componente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-108">A component:</span></span>

- <span data-ttu-id="ba9c3-109">È un blocco autonomo di interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="ba9c3-110">Mantiene il proprio stato e la logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="ba9c3-111">Consente di definire gestori di eventi dell'interfaccia utente, eseguire il binding ai dati di input e gestire il proprio ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="ba9c3-112">Viene in genere definito in un file *Razor* con sintassi Razor.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="ba9c3-113">Introduzione a Razor</span><span class="sxs-lookup"><span data-stu-id="ba9c3-113">An introduction to Razor</span></span>

<span data-ttu-id="ba9c3-114">Razor è un linguaggio di modelli di markup leggero basato su HTML e C#.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="ba9c3-115">Con Razor è possibile passare senza interruzioni tra markup e codice C# per definire la logica di rendering dei componenti.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="ba9c3-116">Quando viene compilato il file con *estensione Razor* , la logica di rendering viene acquisita in modo strutturato in una classe .NET.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="ba9c3-117">Il nome della classe compilata è tratto dal nome del file *Razor* .</span><span class="sxs-lookup"><span data-stu-id="ba9c3-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="ba9c3-118">Lo spazio dei nomi viene tratto dallo spazio dei nomi predefinito per il progetto e il percorso della cartella oppure è possibile specificare in modo esplicito lo spazio dei nomi usando la `@namespace` direttiva. altre informazioni sulle direttive Razor sono disponibili di seguito.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="ba9c3-119">La logica di rendering di un componente viene creata usando il normale markup HTML con la logica dinamica aggiunta con C#.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="ba9c3-120">Il `@` carattere viene usato per la transizione a C#.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="ba9c3-121">Razor è in genere intelligente per capire quando è stato eseguito il passaggio al codice HTML.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="ba9c3-122">Il componente seguente, ad esempio, esegue il `<p>` rendering di un tag con l'ora corrente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="ba9c3-123">Per specificare in modo esplicito l'inizio e la fine di un'espressione C#, usare le parentesi:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="ba9c3-124">Razor semplifica anche l'uso del flusso di controllo C# nella logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="ba9c3-125">Ad esempio, è possibile eseguire il rendering condizionale di codice HTML simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="ba9c3-126">In alternativa, è possibile generare un elenco di elementi usando un `foreach` ciclo C# normale come il seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="ba9c3-127">Le direttive Razor, come le direttive nei Web Form ASP.NET, controllano molti aspetti della modalità di compilazione di un componente Razor.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="ba9c3-128">Gli esempi includono i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-128">Examples include the component's:</span></span>

- <span data-ttu-id="ba9c3-129">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ba9c3-129">Namespace</span></span>
- <span data-ttu-id="ba9c3-130">Classe di base</span><span class="sxs-lookup"><span data-stu-id="ba9c3-130">Base class</span></span>
- <span data-ttu-id="ba9c3-131">Interfacce implementate</span><span class="sxs-lookup"><span data-stu-id="ba9c3-131">Implemented interfaces</span></span>
- <span data-ttu-id="ba9c3-132">Parametri generici</span><span class="sxs-lookup"><span data-stu-id="ba9c3-132">Generic parameters</span></span>
- <span data-ttu-id="ba9c3-133">Spazi dei nomi importati</span><span class="sxs-lookup"><span data-stu-id="ba9c3-133">Imported namespaces</span></span>
- <span data-ttu-id="ba9c3-134">Route</span><span class="sxs-lookup"><span data-stu-id="ba9c3-134">Routes</span></span>

<span data-ttu-id="ba9c3-135">Le direttive Razor iniziano con `@` il carattere e vengono in genere usate all'inizio di una nuova riga all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="ba9c3-136">Ad esempio, la `@namespace` direttiva definisce lo spazio dei nomi del componente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="ba9c3-137">La tabella seguente riepiloga le varie direttive Razor usate in blazer e i rispettivi equivalenti Web Form ASP.NET, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="ba9c3-138">Direttiva</span><span class="sxs-lookup"><span data-stu-id="ba9c3-138">Directive</span></span>    |<span data-ttu-id="ba9c3-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba9c3-139">Description</span></span>|<span data-ttu-id="ba9c3-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba9c3-140">Example</span></span>|<span data-ttu-id="ba9c3-141">Web Form equivalenti</span><span class="sxs-lookup"><span data-stu-id="ba9c3-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="ba9c3-142">Aggiunge un attributo a livello di classe al componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="ba9c3-143">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ba9c3-143">None</span></span>|
|`@code`      |<span data-ttu-id="ba9c3-144">Aggiunge membri di classe al componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="ba9c3-145">Implementa l'interfaccia specificata.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="ba9c3-146">Usare il code-behind</span><span class="sxs-lookup"><span data-stu-id="ba9c3-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="ba9c3-147">Eredita dalla classe di base specificata</span><span class="sxs-lookup"><span data-stu-id="ba9c3-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="ba9c3-148">Inserisce un servizio nel componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="ba9c3-149">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ba9c3-149">None</span></span>|
|`@layout`    |<span data-ttu-id="ba9c3-150">Specifica un componente di layout per il componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="ba9c3-151">Imposta lo spazio dei nomi per il componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="ba9c3-152">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ba9c3-152">None</span></span>|
|`@page`      |<span data-ttu-id="ba9c3-153">Specifica la route per il componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="ba9c3-154">Specifica un parametro di tipo generico per il componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="ba9c3-155">Usare il code-behind</span><span class="sxs-lookup"><span data-stu-id="ba9c3-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="ba9c3-156">Specifica uno spazio dei nomi da inserire nell'ambito</span><span class="sxs-lookup"><span data-stu-id="ba9c3-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="ba9c3-157">Aggiungi spazio dei nomi in *Web. config*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="ba9c3-158">I componenti Razor fanno anche uso estensivo degli *attributi di direttiva* sugli elementi per controllare vari aspetti del modo in cui i componenti vengono compilati (gestione degli eventi, data binding, componenti & riferimenti agli elementi e così via).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="ba9c3-159">Tutti gli attributi di direttiva seguono una sintassi generica comune in cui i valori tra parentesi sono facoltativi:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="ba9c3-160">Nella tabella seguente vengono riepilogati i vari attributi per le direttive Razor utilizzate in blazer.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="ba9c3-161">Attributo</span><span class="sxs-lookup"><span data-stu-id="ba9c3-161">Attribute</span></span>    |<span data-ttu-id="ba9c3-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba9c3-162">Description</span></span>|<span data-ttu-id="ba9c3-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba9c3-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="ba9c3-164">Esegue il rendering di un dizionario di attributi</span><span class="sxs-lookup"><span data-stu-id="ba9c3-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="ba9c3-165">Crea una data binding bidirezionale</span><span class="sxs-lookup"><span data-stu-id="ba9c3-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="ba9c3-166">Aggiunge un gestore eventi per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="ba9c3-167">Specifica una chiave che deve essere usata dall'algoritmo diffing per mantenere gli elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="ba9c3-168">Acquisisce un riferimento all'elemento Component o HTML</span><span class="sxs-lookup"><span data-stu-id="ba9c3-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="ba9c3-169">I vari attributi di direttiva usati da Blazer`@onclick`( `@bind`, `@ref`, e così via) sono descritti nelle sezioni seguenti e nei capitoli successivi.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="ba9c3-170">Molte delle sintassi usate nei file *. aspx* e *. ascx* hanno sintassi parallele in Razor.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="ba9c3-171">Di seguito è riportato un semplice confronto delle sintassi per ASP.NET Web Forms e Razor.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="ba9c3-172">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="ba9c3-172">Feature</span></span>                      |<span data-ttu-id="ba9c3-173">Web Form</span><span class="sxs-lookup"><span data-stu-id="ba9c3-173">Web Forms</span></span>           |<span data-ttu-id="ba9c3-174">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba9c3-174">Syntax</span></span>               |<span data-ttu-id="ba9c3-175">Razor</span><span class="sxs-lookup"><span data-stu-id="ba9c3-175">Razor</span></span>         |<span data-ttu-id="ba9c3-176">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba9c3-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="ba9c3-177">Direttive</span><span class="sxs-lookup"><span data-stu-id="ba9c3-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="ba9c3-178">Blocchi di codice</span><span class="sxs-lookup"><span data-stu-id="ba9c3-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="ba9c3-179">Espressioni</span><span class="sxs-lookup"><span data-stu-id="ba9c3-179">Expressions</span></span><br><span data-ttu-id="ba9c3-180">(Codificata in HTML)</span><span class="sxs-lookup"><span data-stu-id="ba9c3-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="ba9c3-181">Implicita`@`</span><span class="sxs-lookup"><span data-stu-id="ba9c3-181">Implicit: `@`</span></span><br><span data-ttu-id="ba9c3-182">Esplicita`@()`</span><span class="sxs-lookup"><span data-stu-id="ba9c3-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="ba9c3-183">Commenti</span><span class="sxs-lookup"><span data-stu-id="ba9c3-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="ba9c3-184">Associazione dati</span><span class="sxs-lookup"><span data-stu-id="ba9c3-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="ba9c3-185">Per aggiungere membri alla classe del componente Razor, utilizzare la `@code` direttiva.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="ba9c3-186">Questa tecnica è simile all'uso di `<script runat="server">...</script>` un blocco in una pagina o in un controllo utente Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="ba9c3-187">Poiché Razor è basato su C#, è necessario compilarlo dall'interno di un progetto C# (*csproj*).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="ba9c3-188">Non è possibile compilare file con *estensione Razor* da un progetto Visual Basic (*VBPROJ*).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="ba9c3-189">È comunque possibile fare riferimento ai progetti Visual Basic dal progetto blazer.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="ba9c3-190">Il contrario è true.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-190">The opposite is true too.</span></span>

<span data-ttu-id="ba9c3-191">Per un riferimento completo sintassi Razor, vedere [riferimento sintassi Razor per ASP.NET Core](/aspnet/core/mvc/views/razor).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="ba9c3-192">Usare i componenti</span><span class="sxs-lookup"><span data-stu-id="ba9c3-192">Use components</span></span>

<span data-ttu-id="ba9c3-193">Oltre al normale HTML, i componenti possono usare anche altri componenti come parte della logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="ba9c3-194">La sintassi per l'uso di un componente in Razor è simile all'uso di un controllo utente in un'app Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="ba9c3-195">I componenti vengono specificati utilizzando un tag di elemento che corrisponde al nome del tipo del componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="ba9c3-196">Ad esempio, è possibile aggiungere un `Counter` componente analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="ba9c3-197">A differenza dei Web Form ASP.NET, componenti in Blazer:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="ba9c3-198">Non usare un prefisso di elemento (ad esempio `asp:`,).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="ba9c3-199">Non richiedere la registrazione nella pagina o in *Web. config*.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="ba9c3-200">Si pensi ai componenti Razor come se fossero tipi .NET, perché si tratta esattamente di ciò che si tratta.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="ba9c3-201">Se viene fatto riferimento all'assembly contenente il componente, il componente sarà disponibile per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="ba9c3-202">Per portare lo spazio dei nomi del componente nell'ambito, `@using` applicare la direttiva:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="ba9c3-203">Come illustrato nei progetti Blazer predefiniti, è comune inserire `@using` le direttive in un file *_Imports. Razor* , in modo che vengano importate in tutti i file con *estensione Razor* nella stessa directory e nelle directory figlio.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="ba9c3-204">Se lo spazio dei nomi per un componente non è incluso nell'ambito, è possibile specificare un componente usando il nome completo del tipo, come è possibile in C#:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="ba9c3-205">Parametri del componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-205">Component parameters</span></span>

<span data-ttu-id="ba9c3-206">In ASP.NET Web Form è possibile eseguire il flusso di parametri e dati ai controlli usando proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="ba9c3-207">Queste proprietà possono essere impostate nel markup usando gli attributi o impostate direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="ba9c3-208">I componenti Blazer funzionano in modo simile, anche se le proprietà del componente devono essere contrassegnate `[Parameter]` con l'attributo per essere considerati parametri del componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="ba9c3-209">Il componente `Counter` seguente definisce un parametro del componente `IncrementAmount` denominato che può essere usato per specificare la quantità che `Counter` deve essere incrementata ogni volta che si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

```razor
<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    int currentCount = 0;

    [Parameter]
    public int IncrementAmount { get; set; } = 1;

    void IncrementCount()
    {
        currentCount+=IncrementAmount;
    }
}
```

<span data-ttu-id="ba9c3-210">Per specificare un parametro component in blazer, usare un attributo come in ASP.NET Web Forms:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="ba9c3-211">Gestori eventi</span><span class="sxs-lookup"><span data-stu-id="ba9c3-211">Event handlers</span></span>

<span data-ttu-id="ba9c3-212">Sia ASP.NET Web Forms che Blazer forniscono un modello di programmazione basato sugli eventi per la gestione degli eventi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="ba9c3-213">Esempi di eventi di questo tipo includono clic sui pulsanti e input di testo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="ba9c3-214">In ASP.NET Web Forms, si usano i controlli server HTML per gestire gli eventi dell'interfaccia utente esposti dal DOM oppure è possibile gestire eventi esposti da controlli server Web.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="ba9c3-215">Gli eventi vengono esposti sul server tramite richieste post-back del modulo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="ba9c3-216">Si consideri l'esempio di clic del pulsante Web form seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="ba9c3-217">*Counter. ascx*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="ba9c3-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="ba9c3-219">In blazer è possibile registrare i gestori per gli eventi dell'interfaccia utente DOM direttamente usando gli attributi di `@on{event}`direttiva del modulo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="ba9c3-220">Il `{event}` segnaposto rappresenta il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="ba9c3-221">Ad esempio, è possibile ascoltare i clic del pulsante come segue:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="ba9c3-222">I gestori di eventi possono accettare un argomento facoltativo specifico dell'evento per fornire altre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="ba9c3-223">Gli eventi del mouse, ad esempio, `MouseEventArgs` possono assumere un argomento, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="ba9c3-224">Anziché fare riferimento a un gruppo di metodi per un gestore eventi, è possibile usare un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="ba9c3-225">Un'espressione lambda consente di chiudere gli altri valori nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="ba9c3-226">I gestori di eventi possono essere eseguiti in modo sincrono o asincrono.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="ba9c3-227">Ad esempio, il gestore `OnClick` eventi seguente viene eseguito in modo asincrono:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="ba9c3-228">Una volta gestito un evento, viene eseguito il rendering del componente per tenere conto di eventuali modifiche dello stato dei componenti.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="ba9c3-229">Con i gestori eventi asincroni, il rendering del componente viene eseguito subito dopo il completamento dell'esecuzione del gestore.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="ba9c3-230">Il rendering del componente viene eseguito *nuovamente* dopo `Task` il completamento dell'oggetto asincrono.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="ba9c3-231">Questa modalità di esecuzione asincrona consente di eseguire il rendering di un'interfaccia utente appropriata `Task` mentre l'oggetto asincrono è ancora in corso.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="ShowMessage">Get message</button>

@if (showMessage)
{
    @if (message == null)
    {
        <p><em>Loading...</em></p>
    }
    else
    {
        <p>The message is: @message</p>
    }
}

@code
{
    bool showMessage = false;
    string message;

    public async Task ShowMessage()
    {
        showMessage = true;
        message = await MessageService.GetMessageAsync();
    }
}
```

<span data-ttu-id="ba9c3-232">I componenti possono anche definire i propri eventi definendo un parametro component di tipo `EventCallback<TValue>`.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="ba9c3-233">I callback di evento supportano tutte le varianti dei gestori eventi dell'interfaccia utente DOM: argomenti facoltativi, sincroni o asincroni, gruppi di metodi o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="ba9c3-234">Associazione dati</span><span class="sxs-lookup"><span data-stu-id="ba9c3-234">Data binding</span></span>

<span data-ttu-id="ba9c3-235">Blazer fornisce un meccanismo semplice per associare i dati di un componente dell'interfaccia utente allo stato del componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="ba9c3-236">Questo approccio è diverso dalle funzionalità di ASP.NET Web Forms per l'associazione dei dati dalle origini dati ai controlli dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="ba9c3-237">Si tratterà di gestire i dati di origini dati diverse nella sezione relativa alla gestione [dei dati](data.md) .</span><span class="sxs-lookup"><span data-stu-id="ba9c3-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="ba9c3-238">Per creare un data binding bidirezionale da un componente dell'interfaccia utente allo stato del componente, usare l' `@bind` attributo Directive.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="ba9c3-239">Nell'esempio seguente il valore della casella di controllo è associato al `isChecked` campo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="ba9c3-240">Quando viene eseguito il rendering del componente, il valore della casella di controllo viene impostato sul valore `isChecked` del campo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="ba9c3-241">Quando l'utente attiva o imposta la casella di `onchange` controllo, viene generato l' `isChecked` evento e il campo viene impostato sul nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="ba9c3-242">In `@bind` questo caso la sintassi è equivalente al markup seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="ba9c3-243">Per modificare l'evento usato per l'associazione, usare l' `@bind:event` attributo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="ba9c3-244">I componenti possono inoltre supportare data binding ai relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="ba9c3-245">Per eseguire il binding dei dati, definire un parametro di callback di evento con lo stesso nome del parametro associabile.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="ba9c3-246">Il suffisso "Changed" viene aggiunto al nome.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="ba9c3-247">*PasswordBox. Razor*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-247">*PasswordBox.razor*</span></span>

```razor
Password: <input
    value="@Password"
    @oninput="OnPasswordChanged"
    type="@(showPassword ? "text" : "password")" />

<label><input type="checkbox" @bind="showPassword" />Show password</label>

@code {
    private bool showPassword;

    [Parameter]
    public string Password { get; set; }

    [Parameter]
    public EventCallback<string> PasswordChanged { get; set; }

    private Task OnPasswordChanged(ChangeEventArgs e)
    {
        Password = e.Value.ToString();
        return PasswordChanged.InvokeAsync(Password);
    }
}
```

<span data-ttu-id="ba9c3-248">Per concatenare un data binding a un elemento dell'interfaccia utente sottostante, impostare il valore e gestire l'evento direttamente sull'elemento dell'interfaccia `@bind` utente anziché utilizzare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="ba9c3-249">Per eseguire l'associazione a un parametro component, `@bind-{Parameter}` utilizzare un attributo per specificare il parametro al quale si desidera eseguire il binding.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="ba9c3-250">Modifiche stato</span><span class="sxs-lookup"><span data-stu-id="ba9c3-250">State changes</span></span>

<span data-ttu-id="ba9c3-251">Se lo stato del componente è stato modificato all'esterno di un normale evento dell'interfaccia utente o di un callback di evento, il componente deve segnalare manualmente che è necessario eseguire nuovamente il rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="ba9c3-252">Per segnalare che lo stato di un componente è stato modificato, `StateHasChanged` chiamare il metodo sul componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="ba9c3-253">Nell'esempio seguente un componente Visualizza un messaggio da un `AppState` servizio che può essere aggiornato da altre parti dell'app.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="ba9c3-254">Il componente registra il `StateHasChanged` proprio metodo con `AppState.OnChange` l'evento in modo che il componente venga sottoposto a rendering ogni volta che il messaggio viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        shortlist.Add(itinerary);
        NotifyStateChanged();
    }

    private void NotifyStateChanged() => OnChange?.Invoke();
}
```

```razor
@inject AppState AppState

<p>App message: @AppState.Message</p>

@code {
    protected override void OnInitialized()
    {
        AppState.OnChange += StateHasChanged
    }
}
```

## <a name="component-lifecycle"></a><span data-ttu-id="ba9c3-255">Ciclo di vita componente</span><span class="sxs-lookup"><span data-stu-id="ba9c3-255">Component lifecycle</span></span>

<span data-ttu-id="ba9c3-256">Il framework ASP.NET Web Forms include metodi del ciclo di vita ben definiti per moduli, pagine e controlli.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="ba9c3-257">Il controllo seguente, ad esempio, implementa i gestori eventi per `Init`gli `Load`eventi del `UnLoad` ciclo di vita, e:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="ba9c3-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="ba9c3-259">I componenti Blazer hanno anche un ciclo di vita ben definito.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="ba9c3-260">Il ciclo di vita di un componente può essere utilizzato per inizializzare lo stato del componente e implementare i comportamenti dei componenti avanzati.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="ba9c3-261">Tutti i metodi del ciclo di vita dei componenti di Blazer hanno versioni sincrone e asincrone.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="ba9c3-262">Il rendering del componente è sincrono.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-262">Component rendering is synchronous.</span></span> <span data-ttu-id="ba9c3-263">Non è possibile eseguire la logica asincrona come parte del rendering dei componenti.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="ba9c3-264">Tutte le logiche asincrone devono essere eseguite come parte `async` di un metodo del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="ba9c3-265">OnInitialized</span><span class="sxs-lookup"><span data-stu-id="ba9c3-265">OnInitialized</span></span>

<span data-ttu-id="ba9c3-266">I `OnInitialized` metodi `OnInitializedAsync` e vengono usati per inizializzare il componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="ba9c3-267">Un componente viene in genere inizializzato dopo il primo rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="ba9c3-268">Dopo l'inizializzazione di un componente, è possibile eseguirne il rendering più volte prima di eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="ba9c3-269">Il `OnInitialized` metodo è simile all' `Page_Load` evento nei controlli e nelle pagine Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="ba9c3-270">OnParametersSet</span><span class="sxs-lookup"><span data-stu-id="ba9c3-270">OnParametersSet</span></span>

<span data-ttu-id="ba9c3-271">I `OnParametersSet` metodi `OnParametersSetAsync` e vengono chiamati quando un componente ha ricevuto parametri dal relativo elemento padre e il valore viene assegnato alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="ba9c3-272">Questi metodi vengono eseguiti dopo l'inizializzazione *del componente e ogni volta che il componente viene*sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="ba9c3-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="ba9c3-273">OnAfterRender</span></span>

<span data-ttu-id="ba9c3-274">I `OnAfterRender` metodi `OnAfterRenderAsync` e vengono chiamati dopo che un componente ha terminato il rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="ba9c3-275">A questo punto vengono popolati i riferimenti a elementi e componenti (altre informazioni sui concetti seguenti).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="ba9c3-276">L'interattività con il browser è abilitata a questo punto.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="ba9c3-277">Le interazioni con l'esecuzione DOM e JavaScript possono avere luogo in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

```csharp
protected override void OnAfterRender(bool firstRender)
{
    if (firstRender)
    {
        ...
    }
}
protected override async Task OnAfterRenderAsync(bool firstRender)
{
    if (firstRender)
    {
        await ...
    }
}
```

<span data-ttu-id="ba9c3-278">`OnAfterRender`e `OnAfterRenderAsync` *non vengono chiamati durante il prerendering sul server*.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="ba9c3-279">Il `firstRender` parametro è `true` la prima volta che il componente viene sottoposto a rendering; in caso contrario, il `false`relativo valore è.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="ba9c3-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="ba9c3-280">IDisposable</span></span>

<span data-ttu-id="ba9c3-281">I componenti di Blazer `IDisposable` possono implementare per eliminare le risorse quando il componente viene rimosso dall'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="ba9c3-282">Un componente Razor può implementare `IDispose` usando la `@implements` direttiva:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

```razor
@using System
@implements IDisposable

...

@code {
    public void Dispose()
    {
        ...
    }
}
```

## <a name="capture-component-references"></a><span data-ttu-id="ba9c3-283">Riferimenti ai componenti di acquisizione</span><span class="sxs-lookup"><span data-stu-id="ba9c3-283">Capture component references</span></span>

<span data-ttu-id="ba9c3-284">In ASP.NET Web Forms è normale modificare un'istanza del controllo direttamente nel codice facendo riferimento al relativo ID.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="ba9c3-285">In blazer è anche possibile acquisire e modificare un riferimento a un componente, anche se è molto meno comune.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="ba9c3-286">Per acquisire un riferimento a un componente in blazer, `@ref` usare l'attributo Directive.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="ba9c3-287">Il valore dell'attributo deve corrispondere al nome di un campo impostabile con lo stesso tipo del componente a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

```razor
<MyLoginDialog @ref="loginDialog" ... />

@code {
    MyLoginDialog loginDialog;

    void OnSomething()
    {
        loginDialog.Show();
    }
}
```

<span data-ttu-id="ba9c3-288">Quando viene eseguito il rendering del componente padre, il campo viene popolato con l'istanza del componente figlio.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="ba9c3-289">È quindi possibile chiamare i metodi in o in altro modo modificare l'istanza del componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="ba9c3-290">Non è consigliabile modificare lo stato del componente direttamente usando i riferimenti ai componenti.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="ba9c3-291">In questo modo si impedisce che il componente venga sottoposto automaticamente a rendering nei momenti corretti.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="ba9c3-292">Riferimenti a elementi di acquisizione</span><span class="sxs-lookup"><span data-stu-id="ba9c3-292">Capture element references</span></span>

<span data-ttu-id="ba9c3-293">I componenti di Blazer possono acquisire riferimenti a un elemento.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="ba9c3-294">A differenza dei controlli server HTML nei Web Form ASP.NET, non è possibile modificare direttamente il DOM usando un riferimento a un elemento in blazer.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="ba9c3-295">Blazer gestisce la maggior parte delle interazioni DOM usando l'algoritmo di confronto DOM.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="ba9c3-296">I riferimenti agli elementi acquisiti in blazer sono opachi.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="ba9c3-297">Tuttavia, vengono usati per passare un riferimento a un elemento specifico in una chiamata di interoperabilità JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="ba9c3-298">Per altre informazioni sull'interoperabilità di JavaScript, vedere [ASP.NET Core interoperabilità JavaScript Blazer](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="ba9c3-299">Componenti basati su modelli</span><span class="sxs-lookup"><span data-stu-id="ba9c3-299">Templated components</span></span>

<span data-ttu-id="ba9c3-300">In ASP.NET Web Forms è possibile creare *controlli basati su modelli*.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="ba9c3-301">I controlli basati su modelli consentono allo sviluppatore di specificare una parte del codice HTML usato per eseguire il rendering di un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="ba9c3-302">I meccanismi di creazione di controlli server basati su modelli sono complessi, ma consentono scenari avanzati per il rendering dei dati in modo personalizzabile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="ba9c3-303">Esempi di controlli basati su modelli `Repeater` includono `DataList`e.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="ba9c3-304">I componenti Blazer possono anche essere basati su modelli definendo parametri del componente `RenderFragment` di `RenderFragment<T>`tipo o.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="ba9c3-305">Un `RenderFragment` oggetto rappresenta un blocco di markup Razor di cui è possibile eseguire il rendering tramite il componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="ba9c3-306">Un `RenderFragment<T>` è un blocco di markup Razor che accetta un parametro che può essere specificato quando viene eseguito il rendering del frammento di rendering.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="ba9c3-307">Contenuto figlio</span><span class="sxs-lookup"><span data-stu-id="ba9c3-307">Child content</span></span>

<span data-ttu-id="ba9c3-308">I componenti di Blazer possono acquisire il contenuto figlio `RenderFragment` come ed eseguire il rendering del contenuto come parte del rendering dei componenti.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="ba9c3-309">Per acquisire il contenuto figlio, definire un parametro del componente `RenderFragment` di tipo e `ChildContent`denominarlo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="ba9c3-310">*ChildContentComponent. Razor*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="ba9c3-311">Un componente padre può quindi fornire contenuto figlio utilizzando la normale sintassi Razor.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="ba9c3-312">Parametri di modelli</span><span class="sxs-lookup"><span data-stu-id="ba9c3-312">Template parameters</span></span>

<span data-ttu-id="ba9c3-313">Un componente Blazer basato su modelli può anche definire più parametri Component di `RenderFragment` tipo `RenderFragment<T>`o.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="ba9c3-314">Il parametro per un `RenderFragment<T>` oggetto può essere specificato quando viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="ba9c3-315">Per specificare un parametro di tipo generico per un componente, usare `@typeparam` la direttiva Razor.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="ba9c3-316">*SimpleListView. Razor*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-316">*SimpleListView.razor*</span></span>

```razor
@typeparam TItem

@Heading

<ul>
@foreach (var item in Items)
{
    <li>@ItemTemplate(item)</li>
}
</ul>

@code {
    [Parameter]
    public RenderFragment Heading { get; set; }

    [Parameter]
    public RenderFragment<TItem> ItemTemplate { get; set; }

    [Parameter]
    public IEnumerable<TItem> Items { get; set; }
}
```

<span data-ttu-id="ba9c3-317">Quando si usa un componente basato su modelli, è possibile specificare i parametri del modello usando gli elementi figlio che corrispondono ai nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="ba9c3-318">Gli argomenti del componente `RenderFragment<T>` di tipo passati come elementi hanno un parametro `context`implicito denominato.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="ba9c3-319">È possibile modificare il nome di questo parametro di implementazione utilizzando `Context` l'attributo nell'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="ba9c3-320">È possibile specificare parametri di tipo generico usando un attributo che corrisponda al nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="ba9c3-321">Il parametro di tipo verrà dedotto se possibile:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Context="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="ba9c3-322">L'output di questo componente è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9c3-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="ba9c3-323">Code-behind</span><span class="sxs-lookup"><span data-stu-id="ba9c3-323">Code-behind</span></span>

<span data-ttu-id="ba9c3-324">Un componente Blazer viene in genere creato in un singolo file *Razor* .</span><span class="sxs-lookup"><span data-stu-id="ba9c3-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="ba9c3-325">Tuttavia, è anche possibile separare il codice e il markup usando un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="ba9c3-326">Per usare un file di componente, aggiungere un file C# che corrisponda al nome del file del componente, ma con estensione *CS* aggiunto (*Counter.Razor.cs*).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="ba9c3-327">Usare il file C# per definire una classe di base per il componente.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="ba9c3-328">È possibile assegnare un nome alla classe di base, ma è comune denominare la classe come la classe Component, ma con un' `Base` estensione aggiunta (`CounterBase`).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="ba9c3-329">La classe basata su componenti deve anche derivare `ComponentBase`da.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="ba9c3-330">Quindi, nel file del componente Razor aggiungere la `@inherits` direttiva per specificare la classe di base per il componente (`@inherits CounterBase`).</span><span class="sxs-lookup"><span data-stu-id="ba9c3-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="ba9c3-331">*Counter. Razor*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="ba9c3-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="ba9c3-332">*Counter.razor.cs*</span></span>

```csharp
public class CounterBase : ComponentBase
{
    protected int currentCount = 0;

    protected void IncrementCount()
    {
        currentCount++;
    }
}
```

<span data-ttu-id="ba9c3-333">La visibilità dei membri del componente nella classe base deve essere `protected` o `public` essere visibile alla classe Component.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba9c3-334">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ba9c3-334">Additional resources</span></span>

<span data-ttu-id="ba9c3-335">Il precedente non è un trattamento esaustivo di tutti gli aspetti dei componenti di Blazer.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="ba9c3-336">Per ulteriori informazioni su come [creare e utilizzare ASP.NET Core componenti Razor](/aspnet/core/blazor/components), vedere la documentazione di Blazer.</span><span class="sxs-lookup"><span data-stu-id="ba9c3-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ba9c3-337">[Precedente](app-startup.md)
>[successivo](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="ba9c3-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
