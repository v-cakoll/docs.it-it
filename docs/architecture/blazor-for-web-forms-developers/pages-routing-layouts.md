---
title: Pagine, routing e layout
description: Informazioni su come creare pagine in blazer, utilizzare il routing lato client e gestire i layout di pagina.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: 693eee270a46ccb56ed5fef8fced1d4a1cf1974f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72520233"
---
# <a name="pages-routing-and-layouts"></a><span data-ttu-id="795b0-103">Pagine, routing e layout</span><span class="sxs-lookup"><span data-stu-id="795b0-103">Pages, routing, and layouts</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="795b0-104">Le app Web Form ASP.NET sono costituite da pagine definite nei file *aspx* .</span><span class="sxs-lookup"><span data-stu-id="795b0-104">ASP.NET Web Forms apps are composed of pages defined in *.aspx* files.</span></span> <span data-ttu-id="795b0-105">L'indirizzo di ogni pagina è basato sul percorso fisico del file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="795b0-105">Each page's address is based on its physical file path in the project.</span></span> <span data-ttu-id="795b0-106">Quando un browser esegue una richiesta alla pagina, viene eseguito il rendering dinamico del contenuto della pagina nel server.</span><span class="sxs-lookup"><span data-stu-id="795b0-106">When a browser makes a request to the page, the contents of the page are dynamically rendered on the server.</span></span> <span data-ttu-id="795b0-107">Gli account di rendering per il markup HTML della pagina e i relativi controlli server.</span><span class="sxs-lookup"><span data-stu-id="795b0-107">The rendering accounts for both the page's HTML markup and its server controls.</span></span>

<span data-ttu-id="795b0-108">In blazer ogni pagina dell'app è un componente, in genere definito in un file con *estensione Razor* , con una o più route specificate.</span><span class="sxs-lookup"><span data-stu-id="795b0-108">In Blazor, each page in the app is a component, typically defined in a *.razor* file, with one or more specified routes.</span></span> <span data-ttu-id="795b0-109">Il routing avviene principalmente sul lato client senza coinvolgere una richiesta server specifica.</span><span class="sxs-lookup"><span data-stu-id="795b0-109">Routing mostly happens client-side without involving a specific server request.</span></span> <span data-ttu-id="795b0-110">Il browser esegue prima di tutto una richiesta all'indirizzo radice dell'app.</span><span class="sxs-lookup"><span data-stu-id="795b0-110">The browser first makes a request to the root address of the app.</span></span> <span data-ttu-id="795b0-111">Un componente `Router` radice nell'app Blazer gestisce quindi l'intercettazione delle richieste di navigazione e dei componenti corretti.</span><span class="sxs-lookup"><span data-stu-id="795b0-111">A root `Router` component in the Blazor app then handles intercepting navigation requests and them to the correct component.</span></span>

<span data-ttu-id="795b0-112">Blazer supporta anche *deep linking*.</span><span class="sxs-lookup"><span data-stu-id="795b0-112">Blazor also supports *deep linking*.</span></span> <span data-ttu-id="795b0-113">Il collegamento diretto si verifica quando il browser esegue una richiesta a una route specifica diversa dalla radice dell'app.</span><span class="sxs-lookup"><span data-stu-id="795b0-113">Deep linking occurs when the browser makes a request to a specific route other than the root of the app.</span></span> <span data-ttu-id="795b0-114">Le richieste di collegamenti diretti inviati al server vengono indirizzate all'app blazer, che quindi instrada il lato client della richiesta al componente corretto.</span><span class="sxs-lookup"><span data-stu-id="795b0-114">Requests for deep links sent to the server are routed to the Blazor app, which then routes the request client-side to the correct component.</span></span>

<span data-ttu-id="795b0-115">Una pagina semplice in Web Form ASP.NET potrebbe contenere il markup seguente:</span><span class="sxs-lookup"><span data-stu-id="795b0-115">A simple page in ASP.NET Web Forms might contain the following markup:</span></span>

<span data-ttu-id="795b0-116">*Nome. aspx*</span><span class="sxs-lookup"><span data-stu-id="795b0-116">*Name.aspx*</span></span>

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

<span data-ttu-id="795b0-117">*Name.aspx.cs*</span><span class="sxs-lookup"><span data-stu-id="795b0-117">*Name.aspx.cs*</span></span>

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

<span data-ttu-id="795b0-118">La pagina equivalente in un'app Blazer avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="795b0-118">The equivalent page in a Blazor app would look like this:</span></span>

<span data-ttu-id="795b0-119">*Nome. Razor*</span><span class="sxs-lookup"><span data-stu-id="795b0-119">*Name.razor*</span></span>

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a><span data-ttu-id="795b0-120">Crea pagine</span><span class="sxs-lookup"><span data-stu-id="795b0-120">Create pages</span></span>

<span data-ttu-id="795b0-121">Per creare una pagina in blazer, creare un componente e aggiungere la direttiva `@page` Razor per specificare la route per il componente.</span><span class="sxs-lookup"><span data-stu-id="795b0-121">To create a page in Blazor, create a component and add the `@page` Razor directive to specify the route for the component.</span></span> <span data-ttu-id="795b0-122">La direttiva `@page` accetta un solo parametro, ovvero il modello di route da aggiungere a tale componente.</span><span class="sxs-lookup"><span data-stu-id="795b0-122">The `@page` directive takes a single parameter, which is the route template to add to that component.</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="795b0-123">Il parametro del modello di route è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="795b0-123">The route template parameter is required.</span></span> <span data-ttu-id="795b0-124">A differenza di ASP.NET Web Forms, la route per un componente Blazer *non* viene dedotta dal percorso del file, anche se potrebbe essere una funzionalità aggiunta in futuro.</span><span class="sxs-lookup"><span data-stu-id="795b0-124">Unlike ASP.NET Web Forms, the route to a Blazor component *isn't* inferred from its file location (although that may be a feature added in the future).</span></span>

<span data-ttu-id="795b0-125">La sintassi del modello di route è la stessa sintassi di base usata per il routing in Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="795b0-125">The route template syntax is the same basic syntax used for routing in ASP.NET Web Forms.</span></span> <span data-ttu-id="795b0-126">I parametri di route vengono specificati nel modello usando le parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="795b0-126">Route parameters are specified in the template using braces.</span></span> <span data-ttu-id="795b0-127">Blazer associa i valori di route ai parametri del componente con lo stesso nome (senza distinzione tra maiuscole e minuscole).</span><span class="sxs-lookup"><span data-stu-id="795b0-127">Blazor will bind route values to component parameters with the same name (case-insensitive).</span></span>

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

<span data-ttu-id="795b0-128">È anche possibile specificare vincoli sul valore del parametro di route.</span><span class="sxs-lookup"><span data-stu-id="795b0-128">You can also specify constraints on the value of the route parameter.</span></span> <span data-ttu-id="795b0-129">Ad esempio, per vincolare l'ID del prodotto come `int`:</span><span class="sxs-lookup"><span data-stu-id="795b0-129">For example, to constrain the product ID to be an `int`:</span></span>

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

<span data-ttu-id="795b0-130">Per un elenco completo dei vincoli di route supportati da Blazer, vedere [vincoli di route](/aspnet/core/blazor/routing#route-constraints).</span><span class="sxs-lookup"><span data-stu-id="795b0-130">For a full list of the route constraints supported by Blazor, see [Route constraints](/aspnet/core/blazor/routing#route-constraints).</span></span>

## <a name="router-component"></a><span data-ttu-id="795b0-131">Componente router</span><span class="sxs-lookup"><span data-stu-id="795b0-131">Router component</span></span>

<span data-ttu-id="795b0-132">Il routing in blazer viene gestito dal componente `Router`.</span><span class="sxs-lookup"><span data-stu-id="795b0-132">Routing in Blazor is handled by the `Router` component.</span></span> <span data-ttu-id="795b0-133">Il componente `Router` viene in genere usato nel componente radice dell'app (*app. Razor*).</span><span class="sxs-lookup"><span data-stu-id="795b0-133">The `Router` component is typically used in the app's root component (*App.razor*).</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

<span data-ttu-id="795b0-134">Il componente `Router` individua i componenti instradabili nella `AppAssembly` specificata e nel `AdditionalAssemblies` specificato facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="795b0-134">The `Router` component discovers the routable components in the specified `AppAssembly` and in the optionally specified `AdditionalAssemblies`.</span></span> <span data-ttu-id="795b0-135">Quando il browser si sposta, il `Router` intercetta la navigazione ed esegue il rendering del contenuto del parametro `Found` con il `RouteData` Estratto se una route corrisponde all'indirizzo. in caso contrario, il `Router` esegue il rendering del relativo parametro di `NotFound`.</span><span class="sxs-lookup"><span data-stu-id="795b0-135">When the browser navigates, the `Router` intercepts the navigation and renders the contents of its `Found` parameter with the extracted `RouteData` if a route matches the address, otherwise the `Router` renders its `NotFound` parameter.</span></span>

<span data-ttu-id="795b0-136">Il componente `RouteView` gestisce il rendering del componente corrispondente specificato dall'`RouteData` con il relativo layout se ne è presente uno.</span><span class="sxs-lookup"><span data-stu-id="795b0-136">The `RouteView` component handles rendering the matched component specified by the `RouteData` with its layout if it has one.</span></span> <span data-ttu-id="795b0-137">Se il componente corrispondente non ha un layout, viene usato il `DefaultLayout` facoltativo specificato.</span><span class="sxs-lookup"><span data-stu-id="795b0-137">If the matched component doesn't have a layout, then the optionally specified `DefaultLayout` is used.</span></span>

<span data-ttu-id="795b0-138">Il componente `LayoutView` esegue il rendering del relativo contenuto figlio all'interno del layout specificato.</span><span class="sxs-lookup"><span data-stu-id="795b0-138">The `LayoutView` component renders its child content within the specified layout.</span></span> <span data-ttu-id="795b0-139">I layout verranno esaminati più dettagliatamente più avanti in questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="795b0-139">We'll look at layouts more in detail later in this chapter.</span></span>

## <a name="navigation"></a><span data-ttu-id="795b0-140">Navigazione</span><span class="sxs-lookup"><span data-stu-id="795b0-140">Navigation</span></span>

<span data-ttu-id="795b0-141">In ASP.NET Web Forms è possibile attivare la navigazione a una pagina diversa restituendo una risposta di reindirizzamento al browser.</span><span class="sxs-lookup"><span data-stu-id="795b0-141">In ASP.NET Web Forms, you trigger navigation to a different page by returning a redirect response to the browser.</span></span> <span data-ttu-id="795b0-142">Esempio:</span><span class="sxs-lookup"><span data-stu-id="795b0-142">For example:</span></span>

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

<span data-ttu-id="795b0-143">La restituzione di una risposta di reindirizzamento non è in genere possibile in blazer.</span><span class="sxs-lookup"><span data-stu-id="795b0-143">Returning a redirect response isn't typically possible in Blazor.</span></span> <span data-ttu-id="795b0-144">Blazer non usa un modello Request/Reply.</span><span class="sxs-lookup"><span data-stu-id="795b0-144">Blazor doesn't use a request-reply model.</span></span> <span data-ttu-id="795b0-145">È tuttavia possibile attivare direttamente le navigazioni del browser, come si può fare con JavaScript.</span><span class="sxs-lookup"><span data-stu-id="795b0-145">You can, however, trigger browser navigations directly, as you can with JavaScript.</span></span>

<span data-ttu-id="795b0-146">Blazer fornisce un servizio `NavigationManager` che può essere usato per:</span><span class="sxs-lookup"><span data-stu-id="795b0-146">Blazor provides a `NavigationManager` service that can be used to:</span></span>

- <span data-ttu-id="795b0-147">Ottenere l'indirizzo del browser corrente</span><span class="sxs-lookup"><span data-stu-id="795b0-147">Get the current browser address</span></span>
- <span data-ttu-id="795b0-148">Ottenere l'indirizzo di base</span><span class="sxs-lookup"><span data-stu-id="795b0-148">Get the base address</span></span>
- <span data-ttu-id="795b0-149">Spostamenti trigger</span><span class="sxs-lookup"><span data-stu-id="795b0-149">Trigger navigations</span></span>
- <span data-ttu-id="795b0-150">Ricevere una notifica quando viene modificato l'indirizzo</span><span class="sxs-lookup"><span data-stu-id="795b0-150">Get notified when the address changes</span></span>

<span data-ttu-id="795b0-151">Per passare a un indirizzo diverso, usare il metodo `NavigateTo`:</span><span class="sxs-lookup"><span data-stu-id="795b0-151">To navigate to a different address, use the `NavigateTo` method:</span></span>

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

<span data-ttu-id="795b0-152">Per una descrizione di tutti i membri `NavigationManager`, vedere [URI e Helper dello stato di navigazione](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span><span class="sxs-lookup"><span data-stu-id="795b0-152">For a description of all `NavigationManager` members, see [URI and navigation state helpers](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span></span>

## <a name="base-urls"></a><span data-ttu-id="795b0-153">URL di base</span><span class="sxs-lookup"><span data-stu-id="795b0-153">Base URLs</span></span>

<span data-ttu-id="795b0-154">Se l'app Blazer viene distribuita in un percorso di base, è necessario specificare l'URL di base nei metadati della pagina usando il tag `<base>` per la proprietà routing a lavoro.</span><span class="sxs-lookup"><span data-stu-id="795b0-154">If your Blazor app is deployed under a base path, then you need to specify the base URL in the page metadata using the `<base>` tag for routing to work property.</span></span> <span data-ttu-id="795b0-155">Se la pagina host per l'app viene sottoposta a rendering server con Razor, è possibile usare la sintassi `~/` per specificare l'indirizzo di base dell'app.</span><span class="sxs-lookup"><span data-stu-id="795b0-155">If the host page for the app is server-rendered using Razor, then you can use the `~/` syntax to specify the app's base address.</span></span> <span data-ttu-id="795b0-156">Se la pagina host è HTML statico, è necessario specificare in modo esplicito l'URL di base.</span><span class="sxs-lookup"><span data-stu-id="795b0-156">If the host page is static HTML, then you need to specify the base URL explicitly.</span></span>

```html
<base href="~/" />
```

## <a name="page-layout"></a><span data-ttu-id="795b0-157">Layout di pagina</span><span class="sxs-lookup"><span data-stu-id="795b0-157">Page layout</span></span>

<span data-ttu-id="795b0-158">Il layout di pagina in Web Form ASP.NET è gestito da pagine master.</span><span class="sxs-lookup"><span data-stu-id="795b0-158">Page layout in ASP.NET Web Forms is handled by Master Pages.</span></span> <span data-ttu-id="795b0-159">Le pagine master definiscono un modello con uno o più segnaposto di contenuto che possono essere forniti da singole pagine.</span><span class="sxs-lookup"><span data-stu-id="795b0-159">Master Pages define a template with one or more content placeholders that can then be supplied by individual pages.</span></span> <span data-ttu-id="795b0-160">Le pagine master sono definite nei file con *estensione master* e iniziano con la direttiva `<%@ Master %>`.</span><span class="sxs-lookup"><span data-stu-id="795b0-160">Master Pages are defined in *.master* files and start with the `<%@ Master %>` directive.</span></span> <span data-ttu-id="795b0-161">Il contenuto dei file con *estensione master* viene codificato come si farebbe con una pagina *. aspx* , ma con l'aggiunta di controlli `<asp:ContentPlaceHolder>` per contrassegnare il punto in cui le pagine possono fornire contenuto.</span><span class="sxs-lookup"><span data-stu-id="795b0-161">The content of the *.master* files is coded as you would an *.aspx* page, but with the addition of `<asp:ContentPlaceHolder>` controls to mark where pages can supply content.</span></span>

<span data-ttu-id="795b0-162">*Site. master*</span><span class="sxs-lookup"><span data-stu-id="795b0-162">*Site.master*</span></span>

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

<span data-ttu-id="795b0-163">In blazer si gestisce il layout di pagina usando i componenti di layout.</span><span class="sxs-lookup"><span data-stu-id="795b0-163">In Blazor, you handle page layout using layout components.</span></span> <span data-ttu-id="795b0-164">I componenti di layout ereditano da `LayoutComponentBase`, che definisce una singola proprietà `Body` di tipo `RenderFragment`, che può essere usata per eseguire il rendering del contenuto della pagina.</span><span class="sxs-lookup"><span data-stu-id="795b0-164">Layout components inherit from `LayoutComponentBase`, which defines a single `Body` property of type `RenderFragment`, which can be used to render the contents of the page.</span></span>

<span data-ttu-id="795b0-165">*MainLayout. Razor*</span><span class="sxs-lookup"><span data-stu-id="795b0-165">*MainLayout.razor*</span></span>

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

<span data-ttu-id="795b0-166">Quando viene eseguito il rendering della pagina con un layout, il rendering della pagina viene eseguito all'interno del contenuto del layout specificato nella posizione in cui il layout esegue il rendering della relativa proprietà `Body`.</span><span class="sxs-lookup"><span data-stu-id="795b0-166">When the page with a layout is rendered, the page is rendered within the contents of the specified layout at the location where the layout renders its `Body` property.</span></span>

<span data-ttu-id="795b0-167">Per applicare un layout a una pagina, usare la direttiva `@layout`:</span><span class="sxs-lookup"><span data-stu-id="795b0-167">To apply a layout to a page, use the `@layout` directive:</span></span>

```razor
@layout MainLayout
```

<span data-ttu-id="795b0-168">È possibile specificare il layout per tutti i componenti di una cartella e sottocartelle usando un file *_Imports. Razor* .</span><span class="sxs-lookup"><span data-stu-id="795b0-168">You can specify the layout for all components in a folder and subfolders using an *_Imports.razor* file.</span></span> <span data-ttu-id="795b0-169">È inoltre possibile specificare un layout predefinito per tutte le pagine utilizzando il [componente router](#router-component).</span><span class="sxs-lookup"><span data-stu-id="795b0-169">You can also specify a default layout for all your pages using the [Router component](#router-component).</span></span>

<span data-ttu-id="795b0-170">Le pagine master possono definire più segnaposto di contenuto, ma i layout in blazer hanno solo una singola proprietà `Body`.</span><span class="sxs-lookup"><span data-stu-id="795b0-170">Master Pages can define multiple content placeholders, but layouts in Blazor only have a single `Body` property.</span></span> <span data-ttu-id="795b0-171">Questa limitazione dei componenti di layout di Blazer verrà probabilmente risolta in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="795b0-171">This limitation of Blazor layout components will hopefully be addressed in a future release.</span></span>

<span data-ttu-id="795b0-172">Le pagine master in Web Form ASP.NET possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="795b0-172">Master Pages in ASP.NET Web Forms can be nested.</span></span> <span data-ttu-id="795b0-173">Ovvero una pagina master può utilizzare anche una pagina master.</span><span class="sxs-lookup"><span data-stu-id="795b0-173">That is, a Master Page may also use a Master Page.</span></span> <span data-ttu-id="795b0-174">Anche i componenti di layout in blazer possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="795b0-174">Layout components in Blazor may be nested too.</span></span> <span data-ttu-id="795b0-175">È possibile applicare un componente di layout a un componente di layout.</span><span class="sxs-lookup"><span data-stu-id="795b0-175">You can apply a layout component to a layout component.</span></span> <span data-ttu-id="795b0-176">Il rendering del contenuto del layout interno verrà eseguito all'interno del layout esterno.</span><span class="sxs-lookup"><span data-stu-id="795b0-176">The contents of the inner layout will be rendered within the outer layout.</span></span>

<span data-ttu-id="795b0-177">*ChildLayout. Razor*</span><span class="sxs-lookup"><span data-stu-id="795b0-177">*ChildLayout.razor*</span></span>

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

<span data-ttu-id="795b0-178">*Index. Razor*</span><span class="sxs-lookup"><span data-stu-id="795b0-178">*Index.razor*</span></span>

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

<span data-ttu-id="795b0-179">L'output di cui è stato eseguito il rendering per la pagina sarà quindi:</span><span class="sxs-lookup"><span data-stu-id="795b0-179">The rendered output for the page would then be:</span></span>

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

<span data-ttu-id="795b0-180">I layout in Blazer non definiscono in genere gli elementi HTML radice per una pagina (`<html>`, `<body>`, `<head>` e così via).</span><span class="sxs-lookup"><span data-stu-id="795b0-180">Layouts in Blazor don't typically define the root HTML elements for a page (`<html>`, `<body>`, `<head>`, and so on).</span></span> <span data-ttu-id="795b0-181">Gli elementi HTML radice sono invece definiti nella pagina host dell'app blazer, che viene usata per eseguire il rendering del contenuto HTML iniziale per l'app (vedere [bootstrap Blazer](project-structure.md#bootstrap-blazor)).</span><span class="sxs-lookup"><span data-stu-id="795b0-181">The root HTML elements are instead defined in a Blazor app's host page, which is used to render the initial HTML content for the app (see [Bootstrap Blazor](project-structure.md#bootstrap-blazor)).</span></span> <span data-ttu-id="795b0-182">La pagina host può eseguire il rendering di più componenti radice per l'app con markup circostante.</span><span class="sxs-lookup"><span data-stu-id="795b0-182">The host page can render multiple root components for the app with surrounding markup.</span></span>

<span data-ttu-id="795b0-183">I componenti in blazer, incluse le pagine, non possono eseguire il rendering di tag `<script>`.</span><span class="sxs-lookup"><span data-stu-id="795b0-183">Components in Blazor, including pages, can't render `<script>` tags.</span></span> <span data-ttu-id="795b0-184">Questa restrizione di rendering esiste perché i tag `<script>` vengono caricati una volta e non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="795b0-184">This rendering restriction exists because `<script>` tags get loaded once and then can't be changed.</span></span> <span data-ttu-id="795b0-185">Potrebbe verificarsi un comportamento imprevisto se si tenta di eseguire il rendering dinamico dei tag usando sintassi Razor.</span><span class="sxs-lookup"><span data-stu-id="795b0-185">Unexpected behavior may occur if you try to render the tags dynamically using Razor syntax.</span></span> <span data-ttu-id="795b0-186">Al contrario, tutti i tag di `<script>` devono essere aggiunti alla pagina host dell'app.</span><span class="sxs-lookup"><span data-stu-id="795b0-186">Instead, all `<script>` tags should be added to the app's host page.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="795b0-187">[Precedente](components.md)
>[Successivo](state-management.md)</span><span class="sxs-lookup"><span data-stu-id="795b0-187">[Previous](components.md)
[Next](state-management.md)</span></span>
