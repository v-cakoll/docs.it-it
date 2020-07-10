---
title: Pagine, routing e layout
description: Informazioni su come creare pagine in Blazor , utilizzare il routing lato client e gestire i layout di pagina.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/19/2019
ms.openlocfilehash: fc1f6f9420c7149b6e67123f2f68bef75667aa0c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173107"
---
# <a name="pages-routing-and-layouts"></a>Pagine, routing e layout

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Le app Web Form ASP.NET sono costituite da pagine definite nei file *aspx* . L'indirizzo di ogni pagina è basato sul percorso fisico del file nel progetto. Quando un browser esegue una richiesta alla pagina, viene eseguito il rendering dinamico del contenuto della pagina nel server. Gli account di rendering per il markup HTML della pagina e i relativi controlli server.

In Blazor ogni pagina dell'app è un componente, in genere definito in un file con *estensione Razor* , con una o più route specificate. Il routing avviene principalmente sul lato client senza coinvolgere una richiesta server specifica. Il browser esegue prima di tutto una richiesta all'indirizzo radice dell'app. Un `Router` componente radice nell' Blazor app gestisce quindi l'intercettazione delle richieste di navigazione e le richieste al componente corretto.

Blazorsupporta anche *deep linking*. Il collegamento diretto si verifica quando il browser esegue una richiesta a una route specifica diversa dalla radice dell'app. Le richieste di collegamenti profondi inviati al server vengono indirizzate all' Blazor app, che quindi instrada il lato client della richiesta al componente corretto.

Una pagina semplice in Web Form ASP.NET potrebbe contenere il markup seguente:

*Nome. aspx*

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

*Name.aspx.cs*

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

La pagina equivalente in un' Blazor app avrà un aspetto simile al seguente:

*Nome. Razor*

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

## <a name="create-pages"></a>Crea pagine

Per creare una pagina in Blazor , creare un componente e aggiungere la `@page` direttiva Razor per specificare la route per il componente. La `@page` direttiva accetta un solo parametro, ovvero il modello di route da aggiungere a tale componente.

```razor
@page "/counter"
```

Il parametro del modello di route è obbligatorio. A differenza di ASP.NET Web Form, la route per un Blazor componente *non* viene dedotta dal percorso del file, anche se potrebbe essere una funzionalità aggiunta in futuro.

La sintassi del modello di route è la stessa sintassi di base usata per il routing in Web Form ASP.NET. I parametri di route vengono specificati nel modello usando le parentesi graffe. Blazorassocia i valori di route ai parametri del componente con lo stesso nome (senza distinzione tra maiuscole e minuscole).

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

È anche possibile specificare vincoli sul valore del parametro di route. Ad esempio, per vincolare l'ID prodotto come `int` :

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

Per un elenco completo dei vincoli di route supportati da Blazor , vedere [vincoli di route](/aspnet/core/blazor/routing#route-constraints).

## <a name="router-component"></a>Componente router

Il routing in Blazor è gestito dal `Router` componente. Il `Router` componente viene in genere usato nel componente radice dell'app (*app. Razor*).

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

Il `Router` componente individua i componenti instradabili nell'oggetto specificato `AppAssembly` e nell'oggetto specificato facoltativamente `AdditionalAssemblies` . Quando il browser si sposta, `Router` intercetta la navigazione ed esegue il rendering del contenuto del relativo `Found` parametro con l'oggetto estratto `RouteData` se una route corrisponde all'indirizzo; in caso contrario, `Router` esegue il rendering del relativo `NotFound` parametro.

Il `RouteView` componente gestisce il rendering del componente corrispondente specificato da `RouteData` con il relativo layout se ne è presente uno. Se il componente corrispondente non ha un layout, viene usato l'oggetto specificato facoltativamente `DefaultLayout` .

Il `LayoutView` componente esegue il rendering del contenuto figlio all'interno del layout specificato. I layout verranno esaminati più dettagliatamente più avanti in questo capitolo.

## <a name="navigation"></a>Navigazione

In ASP.NET Web Forms è possibile attivare la navigazione a una pagina diversa restituendo una risposta di reindirizzamento al browser. Ad esempio:

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

La restituzione di una risposta di reindirizzamento non è in genere possibile in Blazor . Blazornon usa un modello Request/Reply. È tuttavia possibile attivare direttamente le navigazioni del browser, come si può fare con JavaScript.

Blazorfornisce un `NavigationManager` servizio che può essere usato per:

- Ottenere l'indirizzo del browser corrente
- Ottenere l'indirizzo di base
- Spostamenti trigger
- Ricevere una notifica quando viene modificato l'indirizzo

Per passare a un indirizzo diverso, usare il `NavigateTo` Metodo:

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

Per una descrizione di tutti `NavigationManager` i membri, vedere [URI e Helper dello stato di navigazione](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).

## <a name="base-urls"></a>URL di base

Se l' Blazor app viene distribuita in un percorso di base, è necessario specificare l'URL di base nei metadati della pagina usando il `<base>` tag per il routing alla proprietà di lavoro. Se la pagina host per l'app viene sottoposta a rendering server con Razor, è possibile usare la `~/` sintassi per specificare l'indirizzo di base dell'app. Se la pagina host è HTML statico, è necessario specificare in modo esplicito l'URL di base.

```html
<base href="~/" />
```

## <a name="page-layout"></a>Layout di pagina

Il layout di pagina in Web Form ASP.NET è gestito da pagine master. Le pagine master definiscono un modello con uno o più segnaposto di contenuto che possono essere forniti da singole pagine. Le pagine master sono definite nei file con *estensione master* e iniziano con la `<%@ Master %>` direttiva. Il contenuto dei file con *estensione master* viene codificato come si farebbe con una pagina *. aspx* , ma con l'aggiunta di `<asp:ContentPlaceHolder>` controlli per contrassegnare il punto in cui le pagine possono fornire contenuto.

*Site.master*

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

In Blazor è possibile gestire il layout di pagina utilizzando i componenti del layout. I componenti di layout ereditano da `LayoutComponentBase` , che definisce una singola `Body` proprietà di tipo `RenderFragment` , che può essere usata per eseguire il rendering del contenuto della pagina.

*MainLayout. Razor*

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

Quando viene eseguito il rendering della pagina con un layout, il rendering della pagina viene eseguito all'interno del contenuto del layout specificato nella posizione in cui il layout esegue il rendering della relativa `Body` Proprietà.

Per applicare un layout a una pagina, usare la `@layout` direttiva:

```razor
@layout MainLayout
```

È possibile specificare il layout per tutti i componenti di una cartella e sottocartelle utilizzando un file *_Imports. Razor* . È inoltre possibile specificare un layout predefinito per tutte le pagine utilizzando il [componente router](#router-component).

Le pagine master possono definire più segnaposto di contenuto, ma i layout in Blazor hanno solo una singola `Body` Proprietà. Questa limitazione dei Blazor componenti di layout sarà probabilmente risolta in una versione futura.

Le pagine master in Web Form ASP.NET possono essere nidificate. Ovvero una pagina master può utilizzare anche una pagina master. Anche i componenti di layout in Blazor possono essere annidati. È possibile applicare un componente di layout a un componente di layout. Il rendering del contenuto del layout interno verrà eseguito all'interno del layout esterno.

*ChildLayout. Razor*

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

*Index. Razor*

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

L'output di cui è stato eseguito il rendering per la pagina sarà quindi:

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

I layout in Blazor non definiscono in genere gli elementi HTML radice per una pagina ( `<html>` ,, `<body>` `<head>` e così via). Gli elementi HTML radice sono invece definiti nella Blazor pagina host di un'app, che viene usata per eseguire il rendering del contenuto HTML iniziale per l'app (vedere [bootstrap Blazor ](project-structure.md#bootstrap-blazor)). La pagina host può eseguire il rendering di più componenti radice per l'app con markup circostante.

I componenti in Blazor , incluse le pagine, non possono eseguire il rendering dei `<script>` tag. Questa restrizione di rendering esiste perché i `<script>` tag vengono caricati una sola volta e non possono essere modificati. Potrebbe verificarsi un comportamento imprevisto se si tenta di eseguire il rendering dinamico dei tag usando sintassi Razor. Al contrario, tutti i `<script>` tag devono essere aggiunti alla pagina host dell'app.

>[!div class="step-by-step"]
>[Precedente](components.md) 
> [Avanti](state-management.md)
