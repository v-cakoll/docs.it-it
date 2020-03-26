---
title: Crea componenti riutilizzabili dell'interfaccia utente con Blazor
description: Informazioni su come creare componenti dell'interfaccia utente riutilizzabili con Blazor e su come si confrontano con ASP.NET controlli Web Form.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 228f7aec4c7b87cb6d4127b55745f7a5ed90aaf9
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228617"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="aab52-103">Crea componenti riutilizzabili dell'interfaccia utente con Blazor</span><span class="sxs-lookup"><span data-stu-id="aab52-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="aab52-104">Una delle cose belle di ASP.NET Web Form è come consente l'incapsulamento di parti riutilizzabili di codice dell'interfaccia utente (UI) in controlli dell'interfaccia utente riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="aab52-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="aab52-105">I controlli utente personalizzati possono essere definiti nel markup utilizzando file *ascx.*</span><span class="sxs-lookup"><span data-stu-id="aab52-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="aab52-106">È inoltre possibile compilare controlli server elaborati nel codice con il supporto completo della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="aab52-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="aab52-107">Blazor supporta anche l'incapsulamento dell'interfaccia utente attraverso i *componenti*.</span><span class="sxs-lookup"><span data-stu-id="aab52-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="aab52-108">Un componente:</span><span class="sxs-lookup"><span data-stu-id="aab52-108">A component:</span></span>

- <span data-ttu-id="aab52-109">È un blocco indipendente dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="aab52-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="aab52-110">Mantiene il proprio stato e la logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="aab52-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="aab52-111">Può definire gestori eventi dell'interfaccia utente, eseguire l'associazione ai dati di input e gestire il proprio ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="aab52-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="aab52-112">Viene in genere definito in un file *con estensione razor* utilizzando la sintassi Razor.</span><span class="sxs-lookup"><span data-stu-id="aab52-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="aab52-113">Introduzione a Razor</span><span class="sxs-lookup"><span data-stu-id="aab52-113">An introduction to Razor</span></span>

<span data-ttu-id="aab52-114">Razor è un linguaggio di modelli di markup leggero basato su HTML e C.</span><span class="sxs-lookup"><span data-stu-id="aab52-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="aab52-115">Con Razor, è possibile passare senza problemi tra il markup e il codice C , per definire la logica di rendering del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="aab52-116">Quando il file *.razor* viene compilato, la logica di rendering viene acquisita in modo strutturato in una classe .NET.</span><span class="sxs-lookup"><span data-stu-id="aab52-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="aab52-117">Il nome della classe compilata viene ricavato dal nome del file *con estensione razor.*</span><span class="sxs-lookup"><span data-stu-id="aab52-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="aab52-118">Lo spazio dei nomi viene tratto dallo spazio dei nomi predefinito per il `@namespace` progetto e il percorso della cartella oppure è possibile specificare in modo esplicito lo spazio dei nomi usando la direttiva (ulteriori informazioni sulle direttive Razor di seguito).</span><span class="sxs-lookup"><span data-stu-id="aab52-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="aab52-119">La logica di rendering di un componente viene creata utilizzando il normale markup HTML con la logica dinamica aggiunta utilizzando C .</span><span class="sxs-lookup"><span data-stu-id="aab52-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="aab52-120">Il `@` carattere viene utilizzato per la transizione a C .</span><span class="sxs-lookup"><span data-stu-id="aab52-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="aab52-121">Razor è in genere intelligente nel capire quando sei tornato a HTML.</span><span class="sxs-lookup"><span data-stu-id="aab52-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="aab52-122">Ad esempio, il componente `<p>` seguente esegue il rendering di un tag con l'ora corrente:</span><span class="sxs-lookup"><span data-stu-id="aab52-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="aab52-123">Per specificare in modo esplicito l'inizio e la fine di un'espressione c' , utilizzare le parentesi:</span><span class="sxs-lookup"><span data-stu-id="aab52-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="aab52-124">Razor rende anche facile l'uso del flusso di controllo di C , nella logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="aab52-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="aab52-125">Ad esempio, è possibile eseguire il rendering condizionale di alcuni HTML in questo modo:</span><span class="sxs-lookup"><span data-stu-id="aab52-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="aab52-126">In alternativa, è possibile generare un `foreach` elenco di elementi usando un normale ciclo di C, come questo:</span><span class="sxs-lookup"><span data-stu-id="aab52-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="aab52-127">Le direttive Razor, ad esempio le direttive in ASP.NET Web Form, controllano molti aspetti della modalità di compilazione di un componente Razor.</span><span class="sxs-lookup"><span data-stu-id="aab52-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="aab52-128">Gli esempi includono:</span><span class="sxs-lookup"><span data-stu-id="aab52-128">Examples include the component's:</span></span>

- <span data-ttu-id="aab52-129">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="aab52-129">Namespace</span></span>
- <span data-ttu-id="aab52-130">Classe di base</span><span class="sxs-lookup"><span data-stu-id="aab52-130">Base class</span></span>
- <span data-ttu-id="aab52-131">Interfacce implementate</span><span class="sxs-lookup"><span data-stu-id="aab52-131">Implemented interfaces</span></span>
- <span data-ttu-id="aab52-132">Parametri generici</span><span class="sxs-lookup"><span data-stu-id="aab52-132">Generic parameters</span></span>
- <span data-ttu-id="aab52-133">Spazi dei nomi importati</span><span class="sxs-lookup"><span data-stu-id="aab52-133">Imported namespaces</span></span>
- <span data-ttu-id="aab52-134">Route</span><span class="sxs-lookup"><span data-stu-id="aab52-134">Routes</span></span>

<span data-ttu-id="aab52-135">Le direttive Razor `@` iniziano con il carattere e vengono in genere utilizzate all'inizio di una nuova riga all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="aab52-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="aab52-136">Ad esempio, `@namespace` la direttiva definisce lo spazio dei nomi del componente:For example, the directive defines the component's namespace:</span><span class="sxs-lookup"><span data-stu-id="aab52-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="aab52-137">Nella tabella seguente sono riepilogate le varie direttive Razor utilizzate in Blazor e i relativi ASP.NET equivalenti di Web Form, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="aab52-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="aab52-138">Direttiva</span><span class="sxs-lookup"><span data-stu-id="aab52-138">Directive</span></span>    |<span data-ttu-id="aab52-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aab52-139">Description</span></span>|<span data-ttu-id="aab52-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="aab52-140">Example</span></span>|<span data-ttu-id="aab52-141">Equivalente di Web Form</span><span class="sxs-lookup"><span data-stu-id="aab52-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="aab52-142">Aggiunge un attributo a livello di classe al componente</span><span class="sxs-lookup"><span data-stu-id="aab52-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="aab52-143">nessuno</span><span class="sxs-lookup"><span data-stu-id="aab52-143">None</span></span>|
|`@code`      |<span data-ttu-id="aab52-144">Aggiunge membri di classe al componente</span><span class="sxs-lookup"><span data-stu-id="aab52-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="aab52-145">Implementa l'interfaccia specificata</span><span class="sxs-lookup"><span data-stu-id="aab52-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="aab52-146">Usare il code-behind</span><span class="sxs-lookup"><span data-stu-id="aab52-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="aab52-147">Eredita dalla classe base specificata</span><span class="sxs-lookup"><span data-stu-id="aab52-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="aab52-148">Inserisce un servizio nel componente</span><span class="sxs-lookup"><span data-stu-id="aab52-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="aab52-149">nessuno</span><span class="sxs-lookup"><span data-stu-id="aab52-149">None</span></span>|
|`@layout`    |<span data-ttu-id="aab52-150">Specifica un componente di layout per il componente</span><span class="sxs-lookup"><span data-stu-id="aab52-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="aab52-151">Imposta lo spazio dei nomi per il componente</span><span class="sxs-lookup"><span data-stu-id="aab52-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="aab52-152">nessuno</span><span class="sxs-lookup"><span data-stu-id="aab52-152">None</span></span>|
|`@page`      |<span data-ttu-id="aab52-153">Specifica il percorso per il componente</span><span class="sxs-lookup"><span data-stu-id="aab52-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="aab52-154">Specifica un parametro di tipo generico per il componente</span><span class="sxs-lookup"><span data-stu-id="aab52-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="aab52-155">Usare il code-behind</span><span class="sxs-lookup"><span data-stu-id="aab52-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="aab52-156">Specifica uno spazio dei nomi da inserire nell'ambito</span><span class="sxs-lookup"><span data-stu-id="aab52-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="aab52-157">Aggiungere lo spazio dei nomi in *web.configAdd* namespace in web.config</span><span class="sxs-lookup"><span data-stu-id="aab52-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="aab52-158">I componenti Razor fanno anche ampio uso degli attributi della *direttiva* sugli elementi per controllare vari aspetti della modalità di compilazione dei componenti (gestione degli eventi, associazione dati, riferimenti a componenti & elementi e così via).</span><span class="sxs-lookup"><span data-stu-id="aab52-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="aab52-159">Gli attributi di direttiva seguono tutti una sintassi generica comune in cui i valori tra parentesi sono facoltativi:Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span><span class="sxs-lookup"><span data-stu-id="aab52-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="aab52-160">Nella tabella seguente sono riepilogati i vari attributi per le direttive Razor utilizzate in Blazor.</span><span class="sxs-lookup"><span data-stu-id="aab52-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="aab52-161">Attributo</span><span class="sxs-lookup"><span data-stu-id="aab52-161">Attribute</span></span>    |<span data-ttu-id="aab52-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aab52-162">Description</span></span>|<span data-ttu-id="aab52-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="aab52-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="aab52-164">Esegue il rendering di un dizionario di attributi</span><span class="sxs-lookup"><span data-stu-id="aab52-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="aab52-165">Crea un'associazione dati bidirezionale</span><span class="sxs-lookup"><span data-stu-id="aab52-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="aab52-166">Aggiunge un gestore eventi per l'evento specificato</span><span class="sxs-lookup"><span data-stu-id="aab52-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="aab52-167">Specifica una chiave che deve essere utilizzata dall'algoritmo di diffing per mantenere gli elementi in una raccolta</span><span class="sxs-lookup"><span data-stu-id="aab52-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="aab52-168">Acquisisce un riferimento al componente o all'elemento HTML</span><span class="sxs-lookup"><span data-stu-id="aab52-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="aab52-169">I vari attributi di direttiva`@onclick`utilizzati da Blazor ( , `@bind`, `@ref`e così via) sono trattati nelle sezioni seguenti e nei capitoli successivi.</span><span class="sxs-lookup"><span data-stu-id="aab52-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="aab52-170">Molte delle sintassi utilizzate nei file *aspx* e *ascx* hanno sintassi parallele in Razor.</span><span class="sxs-lookup"><span data-stu-id="aab52-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="aab52-171">Di seguito è riportato un semplice confronto delle sintassi per ASP.NET Web Form e Razor.</span><span class="sxs-lookup"><span data-stu-id="aab52-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="aab52-172">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="aab52-172">Feature</span></span>                      |<span data-ttu-id="aab52-173">Web Form</span><span class="sxs-lookup"><span data-stu-id="aab52-173">Web Forms</span></span>           |<span data-ttu-id="aab52-174">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aab52-174">Syntax</span></span>               |<span data-ttu-id="aab52-175">Razor</span><span class="sxs-lookup"><span data-stu-id="aab52-175">Razor</span></span>         |<span data-ttu-id="aab52-176">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aab52-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="aab52-177">Direttive</span><span class="sxs-lookup"><span data-stu-id="aab52-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="aab52-178">Blocchi di codice</span><span class="sxs-lookup"><span data-stu-id="aab52-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="aab52-179">Espressioni</span><span class="sxs-lookup"><span data-stu-id="aab52-179">Expressions</span></span><br><span data-ttu-id="aab52-180">(codifica HTML)</span><span class="sxs-lookup"><span data-stu-id="aab52-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="aab52-181">Implicita:`@`</span><span class="sxs-lookup"><span data-stu-id="aab52-181">Implicit: `@`</span></span><br><span data-ttu-id="aab52-182">Esplicito:`@()`</span><span class="sxs-lookup"><span data-stu-id="aab52-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="aab52-183">Commenti</span><span class="sxs-lookup"><span data-stu-id="aab52-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="aab52-184">Associazione dati</span><span class="sxs-lookup"><span data-stu-id="aab52-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="aab52-185">Per aggiungere membri alla classe del `@code` componente Razor, utilizzare la direttiva .</span><span class="sxs-lookup"><span data-stu-id="aab52-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="aab52-186">Questa tecnica è simile `<script runat="server">...</script>` all'utilizzo di un blocco in un controllo utente o in una pagina Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="aab52-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="aab52-187">Poiché Razor è basato su C, deve essere compilato all'interno di un progetto C ,*csproj*.</span><span class="sxs-lookup"><span data-stu-id="aab52-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="aab52-188">Non è possibile compilare file *con estensione razor* da un progetto Visual Basic (*vbproj*).</span><span class="sxs-lookup"><span data-stu-id="aab52-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="aab52-189">È comunque possibile fare riferimento a progetti visual basic dal progetto Blazor.</span><span class="sxs-lookup"><span data-stu-id="aab52-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="aab52-190">È vero anche il contrario.</span><span class="sxs-lookup"><span data-stu-id="aab52-190">The opposite is true too.</span></span>

<span data-ttu-id="aab52-191">Per un riferimento completo alla sintassi Razor, vedere Informazioni di riferimento sulla [sintassi Razor per ASP.NET Core](/aspnet/core/mvc/views/razor).</span><span class="sxs-lookup"><span data-stu-id="aab52-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="aab52-192">Usare i componenti</span><span class="sxs-lookup"><span data-stu-id="aab52-192">Use components</span></span>

<span data-ttu-id="aab52-193">Oltre al normale HTML, i componenti possono anche utilizzare altri componenti come parte della logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="aab52-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="aab52-194">La sintassi per l'utilizzo di un componente in Razor è simile all'utilizzo di un controllo utente in un'app Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="aab52-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="aab52-195">I componenti vengono specificati utilizzando un tag di elemento che corrisponde al nome del tipo del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="aab52-196">Ad esempio, è `Counter` possibile aggiungere un componente simile al seguente:For example, you can add a component like this:</span><span class="sxs-lookup"><span data-stu-id="aab52-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="aab52-197">A differenza di Web Form ASP.NET, i componenti in Blazor:</span><span class="sxs-lookup"><span data-stu-id="aab52-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="aab52-198">Non utilizzare un prefisso di `asp:`elemento ( ad esempio, ).</span><span class="sxs-lookup"><span data-stu-id="aab52-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="aab52-199">Non richiedere la registrazione nella pagina o nel *file web.config*.</span><span class="sxs-lookup"><span data-stu-id="aab52-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="aab52-200">Pensate ai componenti Razor come si farebbe tipi .NET, perché questo è esattamente quello che sono.</span><span class="sxs-lookup"><span data-stu-id="aab52-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="aab52-201">Se si fa riferimento all'assieme contenente il componente, il componente è disponibile per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="aab52-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="aab52-202">Per inserire lo spazio dei nomi `@using` del componente nell'ambito, applicare la direttiva:To bring the component's namespace into scope, apply the directive:</span><span class="sxs-lookup"><span data-stu-id="aab52-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="aab52-203">Come illustrato nei progetti Blazor predefiniti, è `@using` comune inserire le direttive in un file *_Imports.razor* in modo che vengano importate in tutti i file *con estensione razor* nella stessa directory e nelle directory figlio.</span><span class="sxs-lookup"><span data-stu-id="aab52-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="aab52-204">Se lo spazio dei nomi per un componente non si trova nell'ambito, è possibile specificare un componente usando il nome completo del tipo, come è possibile in C:</span><span class="sxs-lookup"><span data-stu-id="aab52-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="aab52-205">Parametri del componente</span><span class="sxs-lookup"><span data-stu-id="aab52-205">Component parameters</span></span>

<span data-ttu-id="aab52-206">In ASP.NET Web Form è possibile eseguire il flusso di parametri e dati ai controlli utilizzando le proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="aab52-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="aab52-207">Queste proprietà possono essere impostate nel markup utilizzando gli attributi o impostate direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="aab52-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="aab52-208">I componenti Blazor funzionano in modo simile, anche `[Parameter]` se le proprietà del componente devono anche essere contrassegnate con l'attributo per essere considerate parametri del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="aab52-209">Il `Counter` componente seguente definisce `IncrementAmount` un parametro del componente chiamato `Counter` che può essere utilizzato per specificare la quantità che deve essere incrementata ogni volta che si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="aab52-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

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

<span data-ttu-id="aab52-210">Per specificare un parametro del componente in Blazor, utilizzare un attributo come in ASP.NET Web Form:</span><span class="sxs-lookup"><span data-stu-id="aab52-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="aab52-211">Gestori eventi</span><span class="sxs-lookup"><span data-stu-id="aab52-211">Event handlers</span></span>

<span data-ttu-id="aab52-212">Sia ASP.NET Web Form che Blazor forniscono un modello di programmazione basato su eventi per la gestione degli eventi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="aab52-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="aab52-213">Esempi di tali eventi includono i clic sui pulsanti e l'input di testo.</span><span class="sxs-lookup"><span data-stu-id="aab52-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="aab52-214">In ASP.NET Web Form, si utilizzano i controlli server HTML per gestire gli eventi dell'interfaccia utente esposti dal DOM oppure è possibile gestire gli eventi esposti dai controlli server Web.</span><span class="sxs-lookup"><span data-stu-id="aab52-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="aab52-215">Gli eventi vengono visualizzati nel server tramite le richieste di postback del form.</span><span class="sxs-lookup"><span data-stu-id="aab52-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="aab52-216">Si consideri il seguente esempio di clic sul pulsante Web Form:</span><span class="sxs-lookup"><span data-stu-id="aab52-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="aab52-217">*Contatore.ascx*</span><span class="sxs-lookup"><span data-stu-id="aab52-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="aab52-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="aab52-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="aab52-219">In Blazor è possibile registrare i gestori per gli `@on{event}`eventi dell'interfaccia utente DOM direttamente utilizzando gli attributi della direttiva nel formato .</span><span class="sxs-lookup"><span data-stu-id="aab52-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="aab52-220">Il `{event}` segnaposto rappresenta il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="aab52-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="aab52-221">Ad esempio, è possibile ascoltare i clic sui pulsanti in questo modo:For example, you can listen for button clicks like this:</span><span class="sxs-lookup"><span data-stu-id="aab52-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="aab52-222">I gestori eventi possono accettare un argomento facoltativo specifico dell'evento per fornire ulteriori informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="aab52-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="aab52-223">Ad esempio, gli eventi `MouseEventArgs` del mouse possono accettare un argomento, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="aab52-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="aab52-224">Anziché fare riferimento a un gruppo di metodi per un gestore eventi, è possibile usare un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="aab52-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="aab52-225">Un'espressione lambda consente di chiudere su altri valori nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="aab52-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="aab52-226">I gestori eventi possono essere eseguiti in modo sincrono o asincrono.</span><span class="sxs-lookup"><span data-stu-id="aab52-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="aab52-227">Ad esempio, `OnClick` il gestore eventi seguente viene eseguito in modo asincrono:For example, the following event handler executes asynchronously:</span><span class="sxs-lookup"><span data-stu-id="aab52-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="aab52-228">Dopo la gestione di un evento, viene eseguito il rendering del componente per tenere conto delle modifiche apportate allo stato del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="aab52-229">Con i gestori eventi asincroni, il rendering del componente viene eseguito immediatamente dopo il completamento dell'esecuzione del gestore.</span><span class="sxs-lookup"><span data-stu-id="aab52-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="aab52-230">Il rendering del componente `Task` viene *eseguito nuovamente* dopo il completamento dell'asincrono.</span><span class="sxs-lookup"><span data-stu-id="aab52-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="aab52-231">Questa modalità di esecuzione asincrona offre l'opportunità di eseguire il rendering di un'interfaccia utente appropriata mentre l'asincrono `Task` è ancora in corso.</span><span class="sxs-lookup"><span data-stu-id="aab52-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

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

<span data-ttu-id="aab52-232">I componenti possono inoltre definire i propri `EventCallback<TValue>`eventi definendo un parametro di componente di tipo .</span><span class="sxs-lookup"><span data-stu-id="aab52-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="aab52-233">I callback di eventi supportano tutte le varianti dei gestori eventi dell'interfaccia utente DOM: argomenti facoltativi, sincroni o asincroni, gruppi di metodi o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="aab52-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="aab52-234">Associazione dati</span><span class="sxs-lookup"><span data-stu-id="aab52-234">Data binding</span></span>

<span data-ttu-id="aab52-235">Blazor fornisce un semplice meccanismo per associare i dati da un componente dell'interfaccia utente allo stato del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="aab52-236">Questo approccio è diverso dalle funzionalità di ASP.NET Web Form per l'associazione di dati da origini dati ai controlli dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="aab52-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="aab52-237">Nella sezione Gestione dei [dati](data.md) verrà illustrato il trattamento dei dati provenienti da origini dati diverse.</span><span class="sxs-lookup"><span data-stu-id="aab52-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="aab52-238">Per creare un'associazione dati bidirezionale da un componente dell'interfaccia utente allo stato del componente, usare l'attributo della `@bind` direttiva.</span><span class="sxs-lookup"><span data-stu-id="aab52-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="aab52-239">Nell'esempio seguente, il valore della casella `isChecked` di controllo è associato al campo.</span><span class="sxs-lookup"><span data-stu-id="aab52-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="aab52-240">Quando viene eseguito il rendering del componente, il `isChecked` valore della casella di controllo viene impostato sul valore del campo.</span><span class="sxs-lookup"><span data-stu-id="aab52-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="aab52-241">Quando l'utente attiva o `onchange` disattiva la `isChecked` casella di controllo, l'evento viene generato e il campo viene impostato sul nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="aab52-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="aab52-242">La `@bind` sintassi in questo caso è equivalente al markup seguente:The syntax in this case is equivalent to the following markup:</span><span class="sxs-lookup"><span data-stu-id="aab52-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="aab52-243">Per modificare l'evento utilizzato per `@bind:event` l'associazione, utilizzare l'attributo .</span><span class="sxs-lookup"><span data-stu-id="aab52-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="aab52-244">I componenti possono inoltre supportare l'associazione dati ai relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="aab52-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="aab52-245">Per l'associazione dati, definire un parametro di callback eventi con lo stesso nome del parametro associabile.</span><span class="sxs-lookup"><span data-stu-id="aab52-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="aab52-246">Il suffisso "Changed" viene aggiunto al nome.</span><span class="sxs-lookup"><span data-stu-id="aab52-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="aab52-247">*PasswordBox.razor*</span><span class="sxs-lookup"><span data-stu-id="aab52-247">*PasswordBox.razor*</span></span>

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

<span data-ttu-id="aab52-248">Per concatenare un'associazione dati a un elemento dell'interfaccia utente sottostante, imposta il valore e gestisci l'evento direttamente nell'elemento dell'interfaccia utente anziché usare l'attributo. `@bind`</span><span class="sxs-lookup"><span data-stu-id="aab52-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="aab52-249">Per eseguire l'associazione `@bind-{Parameter}` a un parametro del componente, utilizzare un attributo per specificare il parametro a cui si desidera eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="aab52-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="aab52-250">Modifiche stato</span><span class="sxs-lookup"><span data-stu-id="aab52-250">State changes</span></span>

<span data-ttu-id="aab52-251">Se lo stato del componente è stato modificato al di fuori di un normale callback di eventi o eventi dell'interfaccia utente, il componente deve segnalare manualmente che deve essere eseguito nuovamente il rendering.</span><span class="sxs-lookup"><span data-stu-id="aab52-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="aab52-252">Per segnalare che lo stato di `StateHasChanged` un componente è cambiato, chiamare il metodo sul componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="aab52-253">Nell'esempio seguente, un componente visualizza `AppState` un messaggio da un servizio che può essere aggiornato da altre parti dell'app.</span><span class="sxs-lookup"><span data-stu-id="aab52-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="aab52-254">Il componente registra `StateHasChanged` il `AppState.OnChange` relativo metodo con l'evento in modo che il componente viene eseguito il rendering ogni volta che il messaggio viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="aab52-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

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

## <a name="component-lifecycle"></a><span data-ttu-id="aab52-255">Ciclo di vita dei componenti</span><span class="sxs-lookup"><span data-stu-id="aab52-255">Component lifecycle</span></span>

<span data-ttu-id="aab52-256">Il framework Web Form ASP.NET dispone di metodi del ciclo di vita ben definiti per moduli, pagine e controlli.</span><span class="sxs-lookup"><span data-stu-id="aab52-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="aab52-257">Ad esempio, il controllo seguente implementa `Init` `Load`i `UnLoad` gestori eventi per gli eventi del ciclo di vita , , e :</span><span class="sxs-lookup"><span data-stu-id="aab52-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="aab52-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="aab52-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="aab52-259">I componenti Blazor hanno anche un ciclo di vita ben definito.</span><span class="sxs-lookup"><span data-stu-id="aab52-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="aab52-260">Il ciclo di vita di un componente può essere utilizzato per inizializzare lo stato del componente e implementare comportamenti avanzati del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="aab52-261">Tutti i metodi del ciclo di vita dei componenti di Blazor hanno versioni sincrone e asincrone.</span><span class="sxs-lookup"><span data-stu-id="aab52-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="aab52-262">Il rendering dei componenti è sincrono.</span><span class="sxs-lookup"><span data-stu-id="aab52-262">Component rendering is synchronous.</span></span> <span data-ttu-id="aab52-263">Non è possibile eseguire la logica asincrona come parte del rendering del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="aab52-264">Tutta la logica asincrona `async` deve essere eseguita come parte di un metodo del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="aab52-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="aab52-265">OnInitialized (in grado di essere inizializzato)</span><span class="sxs-lookup"><span data-stu-id="aab52-265">OnInitialized</span></span>

<span data-ttu-id="aab52-266">I `OnInitialized` `OnInitializedAsync` metodi e vengono utilizzati per inizializzare il componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="aab52-267">Un componente viene in genere inizializzato dopo il primo rendering.</span><span class="sxs-lookup"><span data-stu-id="aab52-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="aab52-268">Dopo l'inizializzazione di un componente, è possibile che venga eseguito il rendering più volte prima che venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="aab52-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="aab52-269">Il `OnInitialized` metodo è `Page_Load` simile all'evento in ASP.NET pagine e controlli Web Form.</span><span class="sxs-lookup"><span data-stu-id="aab52-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="aab52-270">OnParametersSet</span><span class="sxs-lookup"><span data-stu-id="aab52-270">OnParametersSet</span></span>

<span data-ttu-id="aab52-271">I `OnParametersSet` `OnParametersSetAsync` metodi e vengono chiamati quando un componente ha ricevuto parametri dal relativo elemento padre e il valore vengono assegnati alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="aab52-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="aab52-272">Questi metodi vengono eseguiti dopo l'inizializzazione del componente e *ogni volta che viene eseguito il rendering del componente.*</span><span class="sxs-lookup"><span data-stu-id="aab52-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="aab52-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="aab52-273">OnAfterRender</span></span>

<span data-ttu-id="aab52-274">I `OnAfterRender` `OnAfterRenderAsync` metodi e vengono chiamati al termine del rendering di un componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="aab52-275">I riferimenti a elementi e componenti vengono popolati a questo punto (ulteriori informazioni su questi concetti di seguito).</span><span class="sxs-lookup"><span data-stu-id="aab52-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="aab52-276">L'interattività con il browser è abilitata a questo punto.</span><span class="sxs-lookup"><span data-stu-id="aab52-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="aab52-277">Le interazioni con l'esecuzione di DOM e JavaScript possono avvenire in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="aab52-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

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

<span data-ttu-id="aab52-278">`OnAfterRender`e `OnAfterRenderAsync` *non vengono chiamati durante il prerendering sul server*.</span><span class="sxs-lookup"><span data-stu-id="aab52-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="aab52-279">Il `firstRender` parametro è `true` la prima volta che viene eseguito il rendering del componente; in caso contrario, il relativo valore è `false`.</span><span class="sxs-lookup"><span data-stu-id="aab52-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="aab52-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="aab52-280">IDisposable</span></span>

<span data-ttu-id="aab52-281">I componenti Blazor possono implementare `IDisposable` per eliminare le risorse quando il componente viene rimosso dall'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="aab52-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="aab52-282">Un componente Razor `IDispose` può `@implements` implementare utilizzando la direttiva:A Razor component can implement by using the directive:</span><span class="sxs-lookup"><span data-stu-id="aab52-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

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

## <a name="capture-component-references"></a><span data-ttu-id="aab52-283">Acquisire riferimenti ai componenti</span><span class="sxs-lookup"><span data-stu-id="aab52-283">Capture component references</span></span>

<span data-ttu-id="aab52-284">In ASP.NET Web Form, è comune modificare un'istanza del controllo direttamente nel codice facendo riferimento al relativo ID.</span><span class="sxs-lookup"><span data-stu-id="aab52-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="aab52-285">In Blazor, è anche possibile catturare e manipolare un riferimento a un componente, anche se è molto meno comune.</span><span class="sxs-lookup"><span data-stu-id="aab52-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="aab52-286">Per acquisire un riferimento al componente in `@ref` Blazor, usare l'attributo della direttiva.</span><span class="sxs-lookup"><span data-stu-id="aab52-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="aab52-287">Il valore dell'attributo deve corrispondere al nome di un campo impostabile con lo stesso tipo del componente di riferimento.</span><span class="sxs-lookup"><span data-stu-id="aab52-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

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

<span data-ttu-id="aab52-288">Quando viene eseguito il rendering del componente padre, il campo viene popolato con l'istanza del componente figlio.</span><span class="sxs-lookup"><span data-stu-id="aab52-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="aab52-289">È quindi possibile chiamare i metodi sull'istanza del componente o modificare in altro modo.</span><span class="sxs-lookup"><span data-stu-id="aab52-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="aab52-290">La modifica diretta dello stato del componente tramite i riferimenti dei componenti non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="aab52-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="aab52-291">In questo modo si impedisce il rendering automatico del componente nei momenti corretti.</span><span class="sxs-lookup"><span data-stu-id="aab52-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="aab52-292">Riferimenti agli elementi di acquisizione</span><span class="sxs-lookup"><span data-stu-id="aab52-292">Capture element references</span></span>

<span data-ttu-id="aab52-293">I componenti Blazor possono acquisire riferimenti a un elemento.</span><span class="sxs-lookup"><span data-stu-id="aab52-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="aab52-294">A differenza dei controlli server HTML in ASP.NET Web Form, non è possibile modificare il DOM direttamente utilizzando un riferimento all'elemento in Blazor.</span><span class="sxs-lookup"><span data-stu-id="aab52-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="aab52-295">Blazor gestisce la maggior parte delle interazioni DOM per l'utente utilizzando il relativo algoritmo di diffing DOM.</span><span class="sxs-lookup"><span data-stu-id="aab52-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="aab52-296">I riferimenti agli elementi acquisiti in Blazor sono opachi.</span><span class="sxs-lookup"><span data-stu-id="aab52-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="aab52-297">Tuttavia, vengono utilizzati per passare un riferimento a un elemento specifico in una chiamata di interoperabilità JavaScript.However, they're used to pass a specific element reference in a JavaScript interop call.</span><span class="sxs-lookup"><span data-stu-id="aab52-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="aab52-298">Per ulteriori informazioni sull'interoperabilità JavaScript, vedere [ASP.NETcore Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="aab52-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="aab52-299">Componenti basati su modelli</span><span class="sxs-lookup"><span data-stu-id="aab52-299">Templated components</span></span>

<span data-ttu-id="aab52-300">In ASP.NET Web Form è possibile creare *controlli basati su modelli.*</span><span class="sxs-lookup"><span data-stu-id="aab52-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="aab52-301">I controlli basati su modelli consentono allo sviluppatore di specificare una parte del codice HTML utilizzato per eseguire il rendering di un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="aab52-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="aab52-302">I meccanismi di creazione di controlli server basati su modelli sono complessi, ma consentono scenari potenti per il rendering dei dati in modo personalizzabile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="aab52-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="aab52-303">Esempi di controlli `Repeater` basati su modelli includono e `DataList`.</span><span class="sxs-lookup"><span data-stu-id="aab52-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="aab52-304">I componenti Blazor possono anche essere basati su modelli definendo parametri di tipo `RenderFragment` componente o `RenderFragment<T>`.</span><span class="sxs-lookup"><span data-stu-id="aab52-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="aab52-305">Oggetto `RenderFragment` rappresenta un blocco di Razor markup che può quindi essere eseguito il rendering dal componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="aab52-306">Un `RenderFragment<T>` è un blocco di Razor markup che accetta un parametro che può essere specificato quando viene eseguito il rendering del frammento di rendering.</span><span class="sxs-lookup"><span data-stu-id="aab52-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="aab52-307">Contenuto per bambini</span><span class="sxs-lookup"><span data-stu-id="aab52-307">Child content</span></span>

<span data-ttu-id="aab52-308">I componenti Blazor possono acquisire `RenderFragment` il contenuto figlio come e renderizzarlo come parte del rendering del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="aab52-309">Per acquisire contenuto figlio, definire `RenderFragment` un parametro del componente di tipo e denominarlo `ChildContent`.</span><span class="sxs-lookup"><span data-stu-id="aab52-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="aab52-310">*ChildContentComponent.razor*</span><span class="sxs-lookup"><span data-stu-id="aab52-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="aab52-311">Un componente padre può quindi fornire contenuto figlio utilizzando la normale sintassi Razor.A parent component can then supply child content using normal Razor syntax.</span><span class="sxs-lookup"><span data-stu-id="aab52-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="aab52-312">Parametri del modello</span><span class="sxs-lookup"><span data-stu-id="aab52-312">Template parameters</span></span>

<span data-ttu-id="aab52-313">Un componente Blazor basato su modelli `RenderFragment` può `RenderFragment<T>`inoltre definire più parametri del componente di tipo o .</span><span class="sxs-lookup"><span data-stu-id="aab52-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="aab52-314">Il parametro `RenderFragment<T>` per un oggetto può essere specificato quando viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="aab52-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="aab52-315">Per specificare un parametro di `@typeparam` tipo generico per un componente, utilizzare la direttiva Razor.</span><span class="sxs-lookup"><span data-stu-id="aab52-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="aab52-316">*SimpleListView.razor*</span><span class="sxs-lookup"><span data-stu-id="aab52-316">*SimpleListView.razor*</span></span>

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

<span data-ttu-id="aab52-317">Quando si utilizza un componente basato su modelli, i parametri del modello possono essere specificati utilizzando elementi figlio che corrispondono ai nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="aab52-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="aab52-318">Gli argomenti `RenderFragment<T>` del componente di tipo `context`passato come elementi dispongono di un parametro implicito denominato .</span><span class="sxs-lookup"><span data-stu-id="aab52-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="aab52-319">È possibile modificare il nome di `Context` questo parametro di implementazione utilizzando l'attributo nell'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="aab52-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="aab52-320">È possibile specificare qualsiasi parametro di tipo generico utilizzando un attributo che corrisponde al nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="aab52-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="aab52-321">Il parametro di tipo verrà dedotto se possibile:The type parameter will be inferred if possible:</span><span class="sxs-lookup"><span data-stu-id="aab52-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Content="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="aab52-322">L'output di questo componente è simile al seguente:The output of this component looks like this:</span><span class="sxs-lookup"><span data-stu-id="aab52-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="aab52-323">Code-behind</span><span class="sxs-lookup"><span data-stu-id="aab52-323">Code-behind</span></span>

<span data-ttu-id="aab52-324">Un componente Blazor viene in genere creato in un singolo file *.razor.*</span><span class="sxs-lookup"><span data-stu-id="aab52-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="aab52-325">Tuttavia, è anche possibile separare il codice e il markup utilizzando un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="aab52-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="aab52-326">Per utilizzare un file di componente, aggiungere un file di C, che corrisponda al nome del file del componente ma con l'estensione *cs* aggiunta (*Counter.razor.cs*).</span><span class="sxs-lookup"><span data-stu-id="aab52-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="aab52-327">Utilizzare il file di C , per definire una classe di base per il componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="aab52-328">È possibile denominare la classe base in qualsiasi elemento desiderato, ma è comune denominare la classe come la classe del componente, ma con un'estensione `Base` aggiunta ( ).`CounterBase`</span><span class="sxs-lookup"><span data-stu-id="aab52-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="aab52-329">Anche la classe basata `ComponentBase`su componenti deve derivare da .</span><span class="sxs-lookup"><span data-stu-id="aab52-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="aab52-330">Quindi, nel file del componente `@inherits` Razor, aggiungere la direttiva`@inherits CounterBase`per specificare la classe di base per il componente ( ).</span><span class="sxs-lookup"><span data-stu-id="aab52-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="aab52-331">*Contatore.rasoio*</span><span class="sxs-lookup"><span data-stu-id="aab52-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="aab52-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="aab52-332">*Counter.razor.cs*</span></span>

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

<span data-ttu-id="aab52-333">La visibilità dei membri del componente nella `protected` `public` classe base deve essere o deve essere visibile alla classe del componente.</span><span class="sxs-lookup"><span data-stu-id="aab52-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aab52-334">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="aab52-334">Additional resources</span></span>

<span data-ttu-id="aab52-335">Il precedente non è un trattamento esaustivo di tutti gli aspetti dei componenti Blazor.</span><span class="sxs-lookup"><span data-stu-id="aab52-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="aab52-336">Per ulteriori informazioni su come [creare e utilizzare ASP.NET componenti Core Razor](/aspnet/core/blazor/components), vedere la documentazione di Blazor .</span><span class="sxs-lookup"><span data-stu-id="aab52-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="aab52-337">[Successivo](app-startup.md)
>[precedente](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="aab52-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
