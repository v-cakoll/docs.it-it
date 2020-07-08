---
title: Crea componenti dell'interfaccia utente riutilizzabili con blazer
description: Informazioni su come creare componenti dell'interfaccia utente riutilizzabili con blazer e su come vengono confrontati con i controlli Web Form ASP.NET.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: f6528b1e68b49b6ee3949baca166f4806448718b
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051452"
---
# <a name="build-reusable-ui-components-with-blazor"></a>Crea componenti dell'interfaccia utente riutilizzabili con blazer

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Uno degli aspetti più interessanti di ASP.NET Web Form è il modo in cui l'incapsulamento di parti riutilizzabili di codice dell'interfaccia utente in controlli dell'interfaccia utente riutilizzabili. I controlli utente personalizzati possono essere definiti nel markup usando file con *estensione ascx* . È anche possibile compilare controlli server elaborati nel codice con supporto completo della finestra di progettazione.

Blazer supporta anche l'incapsulamento dell'interfaccia utente tramite i *componenti*. Un componente:

- È un blocco autonomo di interfaccia utente.
- Mantiene il proprio stato e la logica di rendering.
- Consente di definire gestori di eventi dell'interfaccia utente, eseguire il binding ai dati di input e gestire il proprio ciclo di vita.
- Viene in genere definito in un file *Razor* con sintassi Razor.

## <a name="an-introduction-to-razor"></a>Introduzione a Razor

Razor è un linguaggio di modelli di markup leggero basato su HTML e C#. Con Razor è possibile passare senza interruzioni tra markup e codice C# per definire la logica di rendering dei componenti. Quando viene compilato il file con *estensione Razor* , la logica di rendering viene acquisita in modo strutturato in una classe .NET. Il nome della classe compilata è tratto dal nome del file *Razor* . Lo spazio dei nomi viene tratto dallo spazio dei nomi predefinito per il progetto e il percorso della cartella oppure è possibile specificare in modo esplicito lo spazio dei nomi usando la `@namespace` direttiva. altre informazioni sulle direttive Razor sono disponibili di seguito.

La logica di rendering di un componente viene creata usando il normale markup HTML con la logica dinamica aggiunta con C#. Il `@` carattere viene usato per la transizione a C#. Razor è in genere intelligente per capire quando è stato eseguito il passaggio al codice HTML. Il componente seguente, ad esempio, esegue il rendering di un `<p>` tag con l'ora corrente:

```razor
<p>@DateTime.Now</p>
```

Per specificare in modo esplicito l'inizio e la fine di un'espressione C#, usare le parentesi:

```razor
<p>@(DateTime.Now)</p>
```

Razor semplifica anche l'uso del flusso di controllo C# nella logica di rendering. Ad esempio, è possibile eseguire il rendering condizionale di codice HTML simile al seguente:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

In alternativa, è possibile generare un elenco di elementi usando un `foreach` ciclo C# normale come il seguente:

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Le direttive Razor, come le direttive nei Web Form ASP.NET, controllano molti aspetti della modalità di compilazione di un componente Razor. Gli esempi includono i componenti seguenti:

- Spazio dei nomi
- Classe di base
- Interfacce implementate
- Parametri generici
- Spazi dei nomi importati
- Route

Le direttive Razor iniziano con il `@` carattere e vengono in genere usate all'inizio di una nuova riga all'inizio del file. Ad esempio, la `@namespace` direttiva definisce lo spazio dei nomi del componente:

```razor
@namespace MyComponentNamespace
```

La tabella seguente riepiloga le varie direttive Razor usate in blazer e i rispettivi equivalenti Web Form ASP.NET, se esistenti.

|Direttiva    |Descrizione|Esempio|Web Form equivalenti|
|-------------|-----------|-------|--------------------|
|`@attribute` |Aggiunge un attributo a livello di classe al componente.|`@attribute [Authorize]`|nessuno|
|`@code`      |Aggiunge membri di classe al componente|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implementa l'interfaccia specificata.|`@implements IDisposable`|Usare il code-behind|
|`@inherits`  |Eredita dalla classe di base specificata|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Inserisce un servizio nel componente|`@inject IJSRuntime JS`|nessuno|
|`@layout`    |Specifica un componente di layout per il componente|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Imposta lo spazio dei nomi per il componente|`@namespace MyNamespace`|nessuno|
|`@page`      |Specifica la route per il componente|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Specifica un parametro di tipo generico per il componente|`@typeparam TItem`|Usare il code-behind|
|`@using`     |Specifica uno spazio dei nomi da inserire nell'ambito|`@using MyComponentNamespace`|Aggiungi spazio dei nomi in *web.config*|

I componenti Razor fanno anche uso estensivo degli *attributi di direttiva* sugli elementi per controllare vari aspetti del modo in cui i componenti vengono compilati (gestione degli eventi, data binding, componenti & riferimenti agli elementi e così via). Tutti gli attributi di direttiva seguono una sintassi generica comune in cui i valori tra parentesi sono facoltativi:

```razor
@directive(-suffix(:name))(="value")
```

Nella tabella seguente vengono riepilogati i vari attributi per le direttive Razor utilizzate in blazer.

|Attributo    |Descrizione|Esempio|
|-------------|-----------|-------|
|`@attributes`|Esegue il rendering di un dizionario di attributi|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Crea una data binding bidirezionale    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Aggiunge un gestore eventi per l'evento specificato.|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Specifica una chiave che deve essere usata dall'algoritmo diffing per mantenere gli elementi in una raccolta.|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Acquisisce un riferimento all'elemento Component o HTML|`<MyDialog @ref="myDialog" />`|

I vari attributi di direttiva usati da Blazer ( `@onclick` ,, `@bind` `@ref` e così via) sono descritti nelle sezioni seguenti e nei capitoli successivi.

Molte delle sintassi usate nei file *. aspx* e *. ascx* hanno sintassi parallele in Razor. Di seguito è riportato un semplice confronto delle sintassi per ASP.NET Web Forms e Razor.

|Funzionalità                      |Web Form           |Sintassi               |Razor         |Sintassi |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Direttive                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Blocchi di codice                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Espressioni<br>(Codificata in HTML)|`<%: %>`            |`<%:DateTime.Now %>` |Implicita`@`<br>Esplicita`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Commenti                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|Data binding                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Per aggiungere membri alla classe del componente Razor, utilizzare la `@code` direttiva. Questa tecnica è simile all'uso di un `<script runat="server">...</script>` blocco in una pagina o in un controllo utente Web form ASP.NET.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Poiché Razor è basato su C#, è necessario compilarlo dall'interno di un progetto C# (*csproj*). Non è possibile compilare file con *estensione Razor* da un progetto Visual Basic (*VBPROJ*). È comunque possibile fare riferimento ai progetti Visual Basic dal progetto blazer. Il contrario è true.

Per un riferimento completo sintassi Razor, vedere [riferimento sintassi Razor per ASP.NET Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>Usare i componenti

Oltre al normale HTML, i componenti possono usare anche altri componenti come parte della logica di rendering. La sintassi per l'uso di un componente in Razor è simile all'uso di un controllo utente in un'app Web Form ASP.NET. I componenti vengono specificati utilizzando un tag di elemento che corrisponde al nome del tipo del componente. Ad esempio, è possibile aggiungere un `Counter` componente analogo al seguente:

```razor
<Counter />
```

A differenza dei Web Form ASP.NET, componenti in Blazer:

- Non usare un prefisso di elemento (ad esempio, `asp:` ).
- Non richiedere la registrazione nella pagina o nel *web.config*.

Si pensi ai componenti Razor come se fossero tipi .NET, perché si tratta esattamente di ciò che si tratta. Se viene fatto riferimento all'assembly contenente il componente, il componente sarà disponibile per l'utilizzo. Per portare lo spazio dei nomi del componente nell'ambito, applicare la `@using` direttiva:

```razor
@using MyComponentLib

<Counter />
```

Come illustrato nei progetti Blazer predefiniti, è comune inserire le `@using` direttive in un file *_Imports. Razor* , in modo che vengano importate in tutti i file con *estensione Razor* nella stessa directory e nelle directory figlio.

Se lo spazio dei nomi per un componente non è incluso nell'ambito, è possibile specificare un componente usando il nome completo del tipo, come è possibile in C#:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Parametri del componente

In ASP.NET Web Form è possibile eseguire il flusso di parametri e dati ai controlli usando proprietà pubbliche. Queste proprietà possono essere impostate nel markup usando gli attributi o impostate direttamente nel codice. I componenti Blazer funzionano in modo simile, anche se le proprietà del componente devono essere contrassegnate con l' `[Parameter]` attributo per essere considerati parametri del componente.

Il `Counter` componente seguente definisce un parametro del componente denominato `IncrementAmount` che può essere usato per specificare la quantità che `Counter` deve essere incrementata ogni volta che si fa clic sul pulsante.

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

Per specificare un parametro component in blazer, usare un attributo come in ASP.NET Web Forms:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>Gestori eventi

Sia ASP.NET Web Forms che Blazer forniscono un modello di programmazione basato sugli eventi per la gestione degli eventi dell'interfaccia utente. Esempi di eventi di questo tipo includono clic sui pulsanti e input di testo. In ASP.NET Web Forms, si usano i controlli server HTML per gestire gli eventi dell'interfaccia utente esposti dal DOM oppure è possibile gestire eventi esposti da controlli server Web. Gli eventi vengono esposti sul server tramite richieste post-back del modulo. Si consideri l'esempio di clic del pulsante Web form seguente:

*Counter. ascx*

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

In blazer è possibile registrare i gestori per gli eventi dell'interfaccia utente DOM direttamente usando gli attributi di direttiva del modulo `@on{event}` . Il `{event}` segnaposto rappresenta il nome dell'evento. Ad esempio, è possibile ascoltare i clic del pulsante come segue:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

I gestori di eventi possono accettare un argomento facoltativo specifico dell'evento per fornire altre informazioni sull'evento. Gli eventi del mouse, ad esempio, possono assumere un `MouseEventArgs` argomento, ma non è obbligatorio.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

Anziché fare riferimento a un gruppo di metodi per un gestore eventi, è possibile usare un'espressione lambda. Un'espressione lambda consente di chiudere gli altri valori nell'ambito.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

I gestori di eventi possono essere eseguiti in modo sincrono o asincrono. Ad esempio, il `OnClick` gestore eventi seguente viene eseguito in modo asincrono:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

Una volta gestito un evento, viene eseguito il rendering del componente per tenere conto di eventuali modifiche dello stato dei componenti. Con i gestori eventi asincroni, il rendering del componente viene eseguito subito dopo il completamento dell'esecuzione del gestore. Il rendering del componente viene eseguito *nuovamente* dopo il completamento dell'oggetto asincrono `Task` . Questa modalità di esecuzione asincrona consente di eseguire il rendering di un'interfaccia utente appropriata mentre l'oggetto asincrono `Task` è ancora in corso.

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

I componenti possono anche definire i propri eventi definendo un parametro component di tipo `EventCallback<TValue>` . I callback di evento supportano tutte le varianti dei gestori eventi dell'interfaccia utente DOM: argomenti facoltativi, sincroni o asincroni, gruppi di metodi o espressioni lambda.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>Data binding

Blazer fornisce un meccanismo semplice per associare i dati di un componente dell'interfaccia utente allo stato del componente. Questo approccio è diverso dalle funzionalità di ASP.NET Web Forms per l'associazione dei dati dalle origini dati ai controlli dell'interfaccia utente. Si tratterà di gestire i dati di origini dati diverse nella sezione relativa alla gestione [dei dati](data.md) .

Per creare un data binding bidirezionale da un componente dell'interfaccia utente allo stato del componente, usare l' `@bind` attributo Directive. Nell'esempio seguente il valore della casella di controllo è associato al `isChecked` campo.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

Quando viene eseguito il rendering del componente, il valore della casella di controllo viene impostato sul valore del `isChecked` campo. Quando l'utente attiva o imposta la casella di controllo, `onchange` viene generato l'evento e il `isChecked` campo viene impostato sul nuovo valore. `@bind`In questo caso la sintassi è equivalente al markup seguente:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Per modificare l'evento usato per l'associazione, usare l' `@bind:event` attributo.

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

I componenti possono inoltre supportare data binding ai relativi parametri. Per eseguire il binding dei dati, definire un parametro di callback di evento con lo stesso nome del parametro associabile. Il suffisso "Changed" viene aggiunto al nome.

*PasswordBox. Razor*

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

Per concatenare un data binding a un elemento dell'interfaccia utente sottostante, impostare il valore e gestire l'evento direttamente sull'elemento dell'interfaccia utente anziché utilizzare l' `@bind` attributo.

Per eseguire l'associazione a un parametro component, utilizzare un `@bind-{Parameter}` attributo per specificare il parametro al quale si desidera eseguire il binding.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Modifiche stato

Se lo stato del componente è stato modificato all'esterno di un normale evento dell'interfaccia utente o di un callback di evento, il componente deve segnalare manualmente che è necessario eseguire nuovamente il rendering. Per segnalare che lo stato di un componente è stato modificato, chiamare il `StateHasChanged` metodo sul componente.

Nell'esempio seguente un componente Visualizza un messaggio da un `AppState` servizio che può essere aggiornato da altre parti dell'app. Il componente registra il proprio `StateHasChanged` metodo con l' `AppState.OnChange` evento in modo che il componente venga sottoposto a rendering ogni volta che il messaggio viene aggiornato.

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        Message = message;
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

## <a name="component-lifecycle"></a>Ciclo di vita componente

Il framework ASP.NET Web Forms include metodi del ciclo di vita ben definiti per moduli, pagine e controlli. Il controllo seguente, ad esempio, implementa i gestori eventi per gli eventi del ciclo di vita `Init` , `Load` e `UnLoad` :

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

I componenti Blazer hanno anche un ciclo di vita ben definito. Il ciclo di vita di un componente può essere utilizzato per inizializzare lo stato del componente e implementare i comportamenti dei componenti avanzati.

Tutti i metodi del ciclo di vita dei componenti di Blazer hanno versioni sincrone e asincrone. Il rendering del componente è sincrono. Non è possibile eseguire la logica asincrona come parte del rendering dei componenti. Tutte le logiche asincrone devono essere eseguite come parte di un metodo del ciclo di vita `async` .

### <a name="oninitialized"></a>OnInitialized

I `OnInitialized` `OnInitializedAsync` metodi e vengono usati per inizializzare il componente. Un componente viene in genere inizializzato dopo il primo rendering. Dopo l'inizializzazione di un componente, è possibile eseguirne il rendering più volte prima di eliminarlo. Il `OnInitialized` metodo è simile all' `Page_Load` evento nei controlli e nelle pagine Web Form ASP.NET.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

I `OnParametersSet` `OnParametersSetAsync` metodi e vengono chiamati quando un componente ha ricevuto parametri dal relativo elemento padre e il valore viene assegnato alle proprietà. Questi metodi vengono eseguiti dopo l'inizializzazione *del componente e ogni volta che il componente viene*sottoposto a rendering.

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

I `OnAfterRender` `OnAfterRenderAsync` metodi e vengono chiamati dopo che un componente ha terminato il rendering. A questo punto vengono popolati i riferimenti a elementi e componenti (altre informazioni sui concetti seguenti). L'interattività con il browser è abilitata a questo punto. Le interazioni con l'esecuzione DOM e JavaScript possono avere luogo in modo sicuro.

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

`OnAfterRender`e `OnAfterRenderAsync` *non vengono chiamati durante il prerendering sul server*.

Il `firstRender` parametro è `true` la prima volta che il componente viene sottoposto a rendering; in caso contrario, il relativo valore è `false` .

### <a name="idisposable"></a>IDisposable

I componenti di Blazer possono implementare `IDisposable` per eliminare le risorse quando il componente viene rimosso dall'interfaccia utente. Un componente Razor può implementare `IDispose` usando la `@implements` direttiva:

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

## <a name="capture-component-references"></a>Riferimenti ai componenti di acquisizione

In ASP.NET Web Forms è normale modificare un'istanza del controllo direttamente nel codice facendo riferimento al relativo ID. In blazer è anche possibile acquisire e modificare un riferimento a un componente, anche se è molto meno comune.

Per acquisire un riferimento a un componente in blazer, usare l' `@ref` attributo Directive. Il valore dell'attributo deve corrispondere al nome di un campo impostabile con lo stesso tipo del componente a cui si fa riferimento.

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

Quando viene eseguito il rendering del componente padre, il campo viene popolato con l'istanza del componente figlio. È quindi possibile chiamare i metodi in o in altro modo modificare l'istanza del componente.

Non è consigliabile modificare lo stato del componente direttamente usando i riferimenti ai componenti. In questo modo si impedisce che il componente venga sottoposto automaticamente a rendering nei momenti corretti.

## <a name="capture-element-references"></a>Riferimenti a elementi di acquisizione

I componenti di Blazer possono acquisire riferimenti a un elemento. A differenza dei controlli server HTML nei Web Form ASP.NET, non è possibile modificare direttamente il DOM usando un riferimento a un elemento in blazer. Blazer gestisce la maggior parte delle interazioni DOM usando l'algoritmo di confronto DOM. I riferimenti agli elementi acquisiti in blazer sono opachi. Tuttavia, vengono usati per passare un riferimento a un elemento specifico in una chiamata di interoperabilità JavaScript. Per altre informazioni sull'interoperabilità di JavaScript, vedere [ASP.NET Core interoperabilità JavaScript Blazer](/aspnet/core/blazor/javascript-interop).

## <a name="templated-components"></a>Componenti basati su modelli

In ASP.NET Web Forms è possibile creare *controlli basati su modelli*. I controlli basati su modelli consentono allo sviluppatore di specificare una parte del codice HTML usato per eseguire il rendering di un controllo contenitore. I meccanismi di creazione di controlli server basati su modelli sono complessi, ma consentono scenari avanzati per il rendering dei dati in modo personalizzabile dall'utente. Esempi di controlli basati su modelli includono `Repeater` e `DataList` .

I componenti Blazer possono anche essere basati su modelli definendo parametri del componente di tipo `RenderFragment` o `RenderFragment<T>` . Un oggetto `RenderFragment` rappresenta un blocco di markup Razor di cui è possibile eseguire il rendering tramite il componente. Un `RenderFragment<T>` è un blocco di markup Razor che accetta un parametro che può essere specificato quando viene eseguito il rendering del frammento di rendering.

### <a name="child-content"></a>Contenuto figlio

I componenti di Blazer possono acquisire il contenuto figlio come `RenderFragment` ed eseguire il rendering del contenuto come parte del rendering dei componenti. Per acquisire il contenuto figlio, definire un parametro del componente di tipo `RenderFragment` e denominarlo `ChildContent` .

*ChildContentComponent. Razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

Un componente padre può quindi fornire contenuto figlio utilizzando la normale sintassi Razor.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>Parametri di modelli

Un componente Blazer basato su modelli può anche definire più parametri Component di tipo `RenderFragment` o `RenderFragment<T>` . Il parametro per un oggetto `RenderFragment<T>` può essere specificato quando viene richiamato. Per specificare un parametro di tipo generico per un componente, usare la `@typeparam` direttiva Razor.

*SimpleListView. Razor*

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

Quando si usa un componente basato su modelli, è possibile specificare i parametri del modello usando gli elementi figlio che corrispondono ai nomi dei parametri. Gli argomenti del componente di tipo `RenderFragment<T>` passati come elementi hanno un parametro implicito denominato `context` . È possibile modificare il nome di questo parametro di implementazione utilizzando l' `Context` attributo nell'elemento figlio. È possibile specificare parametri di tipo generico usando un attributo che corrisponda al nome del parametro di tipo. Il parametro di tipo verrà dedotto se possibile:

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

L'output di questo componente è simile al seguente:

```html
<h1>My list</h1>
<ul>
    <li><p>The message is: message1</p></li>
    <li><p>The message is: message2</p></li>
<ul>
```

## <a name="code-behind"></a>Code-behind

Un componente Blazer viene in genere creato in un singolo file *Razor* . Tuttavia, è anche possibile separare il codice e il markup usando un file code-behind. Per usare un file di componente, aggiungere un file C# che corrisponda al nome del file del componente, ma con estensione *CS* aggiunto (*Counter.Razor.cs*). Usare il file C# per definire una classe di base per il componente. È possibile assegnare un nome alla classe di base, ma è comune denominare la classe come la classe Component, ma con un' `Base` estensione aggiunta ( `CounterBase` ). La classe basata su componenti deve anche derivare da `ComponentBase` . Quindi, nel file del componente Razor aggiungere la `@inherits` direttiva per specificare la classe di base per il componente ( `@inherits CounterBase` ).

*Counter. Razor*

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

*Counter.razor.cs*

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

La visibilità dei membri del componente nella classe base deve essere o essere `protected` `public` visibile alla classe Component.

## <a name="additional-resources"></a>Risorse aggiuntive

Il precedente non è un trattamento esaustivo di tutti gli aspetti dei componenti di Blazer. Per ulteriori informazioni su come [creare e utilizzare ASP.NET Core componenti Razor](/aspnet/core/blazor/components), vedere la documentazione di Blazer.

>[!div class="step-by-step"]
>[Precedente](app-startup.md) 
> [Avanti](pages-routing-layouts.md)
