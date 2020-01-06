---
title: Crea componenti dell'interfaccia utente riutilizzabili con blazer
description: Informazioni su come creare componenti dell'interfaccia utente riutilizzabili con blazer e su come vengono confrontati con i controlli Web Form ASP.NET.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 5e5ca128bea2e77d795cede17df73963d9b49a48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337393"
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

Razor è un linguaggio di modello di markup leggero basato su HTML e C#. Con Razor è possibile passare senza interruzioni tra markup C# e codice per definire la logica di rendering dei componenti. Quando viene compilato il file con *estensione Razor* , la logica di rendering viene acquisita in modo strutturato in una classe .NET. Il nome della classe compilata è tratto dal nome del file *Razor* . Lo spazio dei nomi viene tratto dallo spazio dei nomi predefinito per il progetto e il percorso della cartella oppure è possibile specificare in modo esplicito lo spazio dei nomi usando la direttiva `@namespace` (altre informazioni sulle direttive Razor riportate di seguito).

La logica di rendering di un componente viene creata usando il normale markup HTML con la logica C#dinamica aggiunta usando. Il carattere `@` viene usato per la transizione C#a. Razor è in genere intelligente per capire quando è stato eseguito il passaggio al codice HTML. Il componente seguente, ad esempio, esegue il rendering di un tag di `<p>` con l'ora corrente:

```razor
<p>@DateTime.Now</p>
```

Per specificare in modo esplicito l'inizio e la C# fine di un'espressione, utilizzare le parentesi:

```razor
<p>@(DateTime.Now)</p>
```

Razor semplifica inoltre l'utilizzo C# del flusso di controllo nella logica di rendering. Ad esempio, è possibile eseguire il rendering condizionale di codice HTML simile al seguente:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

In alternativa, è possibile generare un elenco di elementi usando C# un ciclo di `foreach` normale come il seguente:

```razor
<ul>
@foreach (var item in items)
{
    <li>item.Text</li>
}
</ul>
```

Le direttive Razor, come le direttive nei Web Form ASP.NET, controllano molti aspetti della modalità di compilazione di un componente Razor. Gli esempi includono i componenti seguenti:

- Spazio dei nomi
- Classe base
- Interfacce implementate
- Parametri generici
- Spazi dei nomi importati
- Route

Le direttive Razor iniziano con il carattere `@` e vengono in genere usate all'inizio di una nuova riga all'inizio del file. Ad esempio, la direttiva `@namespace` definisce lo spazio dei nomi del componente:

```razor
@namespace MyComponentNamespace
```

La tabella seguente riepiloga le varie direttive Razor usate in blazer e i rispettivi equivalenti Web Form ASP.NET, se esistenti.

|Directive    |Descrizione|Esempio|Web Form equivalenti|
|-------------|-----------|-------|--------------------|
|`@attribute` |Aggiunge un attributo a livello di classe al componente.|`@attribute [Authorize]`|nessuna|
|`@code`      |Aggiunge membri di classe al componente|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implementa l'interfaccia specificata.|`@implements IDisposable`|Usare il code-behind|
|`@inherits`  |Eredita dalla classe di base specificata|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Inserisce un servizio nel componente|`@inject IJSRuntime JS`|nessuna|
|`@layout`    |Specifica un componente di layout per il componente|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Imposta lo spazio dei nomi per il componente|`@namespace MyNamespace`|nessuna|
|`@page`      |Specifica la route per il componente|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Specifica un parametro di tipo generico per il componente|`@typeparam TItem`|Usare il code-behind|
|`@using`     |Specifica uno spazio dei nomi da inserire nell'ambito|`@using MyComponentNamespace`|Aggiungi spazio dei nomi in *Web. config*|

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

I vari attributi di direttiva usati da Blazer (`@onclick`, `@bind`, `@ref`e così via) sono descritti nelle sezioni seguenti e nei capitoli successivi.

Molte delle sintassi usate nei file *. aspx* e *. ascx* hanno sintassi parallele in Razor. Di seguito è riportato un semplice confronto delle sintassi per ASP.NET Web Forms e Razor.

|Caratteristica                      |Web Form           |Sintassi               |Razor         |Sintassi |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Direttive                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Blocchi di codice                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Espressioni<br>(Codificata in HTML)|`<%: %>`            |`<%:DateTime.Now %>` |Implicito: `@`<br>Esplicito: `@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Comments                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|Associazione dati                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Per aggiungere membri alla classe del componente Razor, usare la direttiva `@code`. Questa tecnica è simile all'uso di un blocco `<script runat="server">...</script>` in una pagina o in un controllo utente Web Form ASP.NET.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Poiché Razor è basato su C#, è necessario compilarlo dall'interno C# di un progetto (*csproj*). Non è possibile compilare file con *estensione Razor* da un progetto Visual Basic (*VBPROJ*). È comunque possibile fare riferimento ai progetti Visual Basic dal progetto blazer. Il contrario è true.

Per un riferimento completo sintassi Razor, vedere [riferimento sintassi Razor per ASP.NET Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>Usare i componenti

Oltre al normale HTML, i componenti possono usare anche altri componenti come parte della logica di rendering. La sintassi per l'uso di un componente in Razor è simile all'uso di un controllo utente in un'app Web Form ASP.NET. I componenti vengono specificati utilizzando un tag di elemento che corrisponde al nome del tipo del componente. Ad esempio, è possibile aggiungere un componente `Counter` come il seguente:

```razor
<Counter />
```

A differenza dei Web Form ASP.NET, componenti in Blazer:

- Non usare un prefisso di elemento, ad esempio `asp:`.
- Non richiedere la registrazione nella pagina o in *Web. config*.

Si pensi ai componenti Razor come se fossero tipi .NET, perché si tratta esattamente di ciò che si tratta. Se viene fatto riferimento all'assembly contenente il componente, il componente sarà disponibile per l'utilizzo. Per portare lo spazio dei nomi del componente nell'ambito, applicare la direttiva `@using`:

```razor
@using MyComponentLib

<Counter />
```

Come illustrato nei progetti Blazer predefiniti, è comune inserire le direttive `@using` in un file *_Imports. Razor* in modo che vengano importate in tutti i file con *estensione Razor* nella stessa directory e nelle directory figlio.

Se lo spazio dei nomi per un componente non è incluso nell'ambito, è possibile specificare un componente usando il nome completo del tipo C#, come è possibile:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Parametri del componente

In ASP.NET Web Form è possibile eseguire il flusso di parametri e dati ai controlli usando proprietà pubbliche. Queste proprietà possono essere impostate nel markup usando gli attributi o impostate direttamente nel codice. I componenti Blazer funzionano in modo analogo, anche se le proprietà del componente devono essere contrassegnate con l'attributo `[Parameter]` per essere considerati parametri del componente.

Il componente `Counter` seguente definisce un parametro del componente denominato `IncrementAmount` che può essere utilizzato per specificare la quantità di incremento del `Counter` ogni volta che si fa clic sul pulsante.

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

In blazer è possibile registrare i gestori per gli eventi dell'interfaccia utente DOM direttamente usando gli attributi di direttiva del modulo `@on{event}`. Il segnaposto `{event}` rappresenta il nome dell'evento. Ad esempio, è possibile ascoltare i clic del pulsante come segue:

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

I gestori di eventi possono essere eseguiti in modo sincrono o asincrono. Ad esempio, il gestore dell'evento `OnClick` seguente viene eseguito in modo asincrono:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

Una volta gestito un evento, viene eseguito il rendering del componente per tenere conto di eventuali modifiche dello stato dei componenti. Con i gestori eventi asincroni, il rendering del componente viene eseguito subito dopo il completamento dell'esecuzione del gestore. Il rendering del componente viene eseguito *nuovamente* dopo il completamento del `Task` asincrono. Questa modalità di esecuzione asincrona consente di eseguire il rendering di un'interfaccia utente appropriata mentre il `Task` asincrono è ancora in corso.

```razor
<button @onclick="Get message">Get message</button>

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

I componenti possono anche definire i propri eventi definendo un parametro component di tipo `EventCallback<TValue>`. I callback di evento supportano tutte le varianti dei gestori eventi dell'interfaccia utente DOM: argomenti facoltativi, sincroni o asincroni, gruppi di metodi o espressioni lambda.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>Associazione dati

Blazer fornisce un meccanismo semplice per associare i dati di un componente dell'interfaccia utente allo stato del componente. Questo approccio è diverso dalle funzionalità di ASP.NET Web Forms per l'associazione dei dati dalle origini dati ai controlli dell'interfaccia utente. Si tratterà di gestire i dati di origini dati diverse nella sezione relativa alla gestione [dei dati](data.md) .

Per creare un data binding bidirezionale da un componente dell'interfaccia utente allo stato del componente, usare l'attributo della direttiva `@bind`. Nell'esempio seguente il valore della casella di controllo è associato al campo `isChecked`.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

Quando viene eseguito il rendering del componente, il valore della casella di controllo viene impostato sul valore del campo `isChecked`. Quando l'utente attiva o imposta la casella di controllo, viene generato l'evento `onchange` e il campo `isChecked` viene impostato sul nuovo valore. La sintassi del `@bind` in questo caso è equivalente al markup seguente:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Per modificare l'evento usato per l'associazione, usare l'attributo `@bind:event`.

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

Per concatenare un data binding a un elemento dell'interfaccia utente sottostante, impostare il valore e gestire l'evento direttamente sull'elemento dell'interfaccia utente anziché usare l'attributo `@bind`.

Per eseguire l'associazione a un parametro component, utilizzare un attributo `@bind-{Parameter}` per specificare il parametro al quale si desidera eseguire il binding.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Modifiche dello stato

Se lo stato del componente è stato modificato all'esterno di un normale evento dell'interfaccia utente o di un callback di evento, il componente deve segnalare manualmente che è necessario eseguire nuovamente il rendering. Per segnalare che lo stato di un componente è stato modificato, chiamare il metodo `StateHasChanged` sul componente.

Nell'esempio seguente un componente Visualizza un messaggio da un servizio `AppState` che può essere aggiornato da altre parti dell'app. Il componente registra il metodo `StateHasChanged` con l'evento `AppState.OnChange` in modo che venga eseguito il rendering del componente ogni volta che il messaggio viene aggiornato.

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

## <a name="component-lifecycle"></a>Ciclo di vita componente

Il framework ASP.NET Web Forms include metodi del ciclo di vita ben definiti per moduli, pagine e controlli. Il controllo seguente, ad esempio, implementa i gestori eventi per gli eventi del ciclo di vita `Init`, `Load`e `UnLoad`:

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

Tutti i metodi del ciclo di vita dei componenti di Blazer hanno versioni sincrone e asincrone. Il rendering del componente è sincrono. Non è possibile eseguire la logica asincrona come parte del rendering dei componenti. Tutte le logiche asincrone devono essere eseguite come parte di un metodo del ciclo di vita `async`.

### <a name="oninitialized"></a>OnInitialized

I metodi `OnInitialized` e `OnInitializedAsync` vengono utilizzati per inizializzare il componente. Un componente viene in genere inizializzato dopo il primo rendering. Dopo l'inizializzazione di un componente, è possibile eseguirne il rendering più volte prima di eliminarlo. Il `OnInitialized` metodo è simile all'evento `Page_Load` in pagine e controlli di ASP.NET Web Form.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

I metodi `OnParametersSet` e `OnParametersSetAsync` vengono chiamati quando un componente riceve parametri dal relativo elemento padre e il valore viene assegnato alle proprietà. Questi metodi vengono eseguiti dopo l'inizializzazione *del componente e ogni volta che il componente viene*sottoposto a rendering.

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

I metodi `OnAfterRender` e `OnAfterRenderAsync` vengono chiamati dopo che un componente ha terminato il rendering. A questo punto vengono popolati i riferimenti a elementi e componenti (altre informazioni sui concetti seguenti). L'interattività con il browser è abilitata a questo punto. Le interazioni con l'esecuzione DOM e JavaScript possono avere luogo in modo sicuro.

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

`OnAfterRender` e `OnAfterRenderAsync` *non vengono chiamati durante il prerendering sul server*.

Il parametro `firstRender` viene `true` la prima volta che il componente viene sottoposto a rendering; in caso contrario, il relativo valore è `false`.

### <a name="idisposable"></a>IDisposable

I componenti di Blazer possono implementare `IDisposable` per eliminare le risorse quando il componente viene rimosso dall'interfaccia utente. Un componente Razor può implementare `IDispose` usando la direttiva `@implements`:

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

Per acquisire un riferimento a un componente in blazer, usare l'attributo della direttiva `@ref`. Il valore dell'attributo deve corrispondere al nome di un campo impostabile con lo stesso tipo del componente a cui si fa riferimento.

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

In ASP.NET Web Forms è possibile creare *controlli basati su modelli*. I controlli basati su modelli consentono allo sviluppatore di specificare una parte del codice HTML usato per eseguire il rendering di un controllo contenitore. I meccanismi di creazione di controlli server basati su modelli sono complessi, ma consentono scenari avanzati per il rendering dei dati in modo personalizzabile dall'utente. Esempi di controlli basati su modelli includono `Repeater` e `DataList`.

I componenti di Blazer possono anche essere basati su modelli definendo parametri del componente di tipo `RenderFragment` o `RenderFragment<T>`. Una `RenderFragment` rappresenta un blocco di markup Razor di cui è possibile eseguire il rendering dal componente. Un `RenderFragment<T>` è un blocco di markup Razor che accetta un parametro che può essere specificato quando viene eseguito il rendering del frammento di rendering.

### <a name="child-content"></a>Contenuto figlio

I componenti di Blazer possono acquisire il contenuto figlio come `RenderFragment` ed eseguire il rendering del contenuto come parte del rendering dei componenti. Per acquisire il contenuto figlio, definire un parametro del componente di tipo `RenderFragment` e denominarlo `ChildContent`.

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

### <a name="template-parameters"></a>Parametri modello

Un componente Blazer basato su modelli può anche definire più parametri di componenti di tipo `RenderFragment` o `RenderFragment<T>`. Il parametro per un `RenderFragment<T>` può essere specificato quando viene richiamato. Per specificare un parametro di tipo generico per un componente, usare la direttiva `@typeparam` Razor.

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

Quando si usa un componente basato su modelli, è possibile specificare i parametri del modello usando gli elementi figlio che corrispondono ai nomi dei parametri. Gli argomenti del componente di tipo `RenderFragment<T>` passati come elementi hanno un parametro implicito denominato `context`. È possibile modificare il nome di questo parametro di implementazione utilizzando l'attributo `Context` sull'elemento figlio. È possibile specificare parametri di tipo generico usando un attributo che corrisponda al nome del parametro di tipo. Il parametro di tipo verrà dedotto se possibile:

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

L'output di questo componente è simile al seguente:

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>Code-behind

Un componente Blazer viene in genere creato in un singolo file *Razor* . Tuttavia, è anche possibile separare il codice e il markup usando un file code-behind. Per usare un file componente, aggiungere un C# file che corrisponda al nome del file del componente, ma con estensione *cs* aggiunto (*Counter.Razor.cs*). Usare il C# file per definire una classe di base per il componente. È possibile assegnare un nome alla classe di base, ma è comune denominare la classe come la classe Component, ma con un'estensione `Base` aggiunta (`CounterBase`). La classe basata su componenti deve anche derivare da `ComponentBase`. Quindi, nel file del componente Razor aggiungere la direttiva `@inherits` per specificare la classe di base per il componente (`@inherits CounterBase`).

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

La visibilità dei membri del componente nella classe base deve essere `protected` o `public` essere visibile alla classe Component.

## <a name="additional-resources"></a>Risorse aggiuntive

Il precedente non è un trattamento esaustivo di tutti gli aspetti dei componenti di Blazer. Per ulteriori informazioni su come [creare e utilizzare ASP.NET Core componenti Razor](/aspnet/core/blazor/components), vedere la documentazione di Blazer.

>[!div class="step-by-step"]
>[Precedente](app-startup.md)
>[Successivo](pages-routing-layouts.md)
