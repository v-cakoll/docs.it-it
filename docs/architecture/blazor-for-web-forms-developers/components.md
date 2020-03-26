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
# <a name="build-reusable-ui-components-with-blazor"></a>Crea componenti riutilizzabili dell'interfaccia utente con Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Una delle cose belle di ASP.NET Web Form è come consente l'incapsulamento di parti riutilizzabili di codice dell'interfaccia utente (UI) in controlli dell'interfaccia utente riutilizzabili. I controlli utente personalizzati possono essere definiti nel markup utilizzando file *ascx.* È inoltre possibile compilare controlli server elaborati nel codice con il supporto completo della finestra di progettazione.

Blazor supporta anche l'incapsulamento dell'interfaccia utente attraverso i *componenti*. Un componente:

- È un blocco indipendente dell'interfaccia utente.
- Mantiene il proprio stato e la logica di rendering.
- Può definire gestori eventi dell'interfaccia utente, eseguire l'associazione ai dati di input e gestire il proprio ciclo di vita.
- Viene in genere definito in un file *con estensione razor* utilizzando la sintassi Razor.

## <a name="an-introduction-to-razor"></a>Introduzione a Razor

Razor è un linguaggio di modelli di markup leggero basato su HTML e C. Con Razor, è possibile passare senza problemi tra il markup e il codice C , per definire la logica di rendering del componente. Quando il file *.razor* viene compilato, la logica di rendering viene acquisita in modo strutturato in una classe .NET. Il nome della classe compilata viene ricavato dal nome del file *con estensione razor.* Lo spazio dei nomi viene tratto dallo spazio dei nomi predefinito per il `@namespace` progetto e il percorso della cartella oppure è possibile specificare in modo esplicito lo spazio dei nomi usando la direttiva (ulteriori informazioni sulle direttive Razor di seguito).

La logica di rendering di un componente viene creata utilizzando il normale markup HTML con la logica dinamica aggiunta utilizzando C . Il `@` carattere viene utilizzato per la transizione a C . Razor è in genere intelligente nel capire quando sei tornato a HTML. Ad esempio, il componente `<p>` seguente esegue il rendering di un tag con l'ora corrente:

```razor
<p>@DateTime.Now</p>
```

Per specificare in modo esplicito l'inizio e la fine di un'espressione c' , utilizzare le parentesi:

```razor
<p>@(DateTime.Now)</p>
```

Razor rende anche facile l'uso del flusso di controllo di C , nella logica di rendering. Ad esempio, è possibile eseguire il rendering condizionale di alcuni HTML in questo modo:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

In alternativa, è possibile generare un `foreach` elenco di elementi usando un normale ciclo di C, come questo:

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Le direttive Razor, ad esempio le direttive in ASP.NET Web Form, controllano molti aspetti della modalità di compilazione di un componente Razor. Gli esempi includono:

- Spazio dei nomi
- Classe di base
- Interfacce implementate
- Parametri generici
- Spazi dei nomi importati
- Route

Le direttive Razor `@` iniziano con il carattere e vengono in genere utilizzate all'inizio di una nuova riga all'inizio del file. Ad esempio, `@namespace` la direttiva definisce lo spazio dei nomi del componente:For example, the directive defines the component's namespace:

```razor
@namespace MyComponentNamespace
```

Nella tabella seguente sono riepilogate le varie direttive Razor utilizzate in Blazor e i relativi ASP.NET equivalenti di Web Form, se esistenti.

|Direttiva    |Descrizione|Esempio|Equivalente di Web Form|
|-------------|-----------|-------|--------------------|
|`@attribute` |Aggiunge un attributo a livello di classe al componente|`@attribute [Authorize]`|nessuno|
|`@code`      |Aggiunge membri di classe al componente|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implementa l'interfaccia specificata|`@implements IDisposable`|Usare il code-behind|
|`@inherits`  |Eredita dalla classe base specificata|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Inserisce un servizio nel componente|`@inject IJSRuntime JS`|nessuno|
|`@layout`    |Specifica un componente di layout per il componente|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Imposta lo spazio dei nomi per il componente|`@namespace MyNamespace`|nessuno|
|`@page`      |Specifica il percorso per il componente|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Specifica un parametro di tipo generico per il componente|`@typeparam TItem`|Usare il code-behind|
|`@using`     |Specifica uno spazio dei nomi da inserire nell'ambito|`@using MyComponentNamespace`|Aggiungere lo spazio dei nomi in *web.configAdd* namespace in web.config|

I componenti Razor fanno anche ampio uso degli attributi della *direttiva* sugli elementi per controllare vari aspetti della modalità di compilazione dei componenti (gestione degli eventi, associazione dati, riferimenti a componenti & elementi e così via). Gli attributi di direttiva seguono tutti una sintassi generica comune in cui i valori tra parentesi sono facoltativi:Directive attributes all follow a common generic syntax where the values in parenthesis are optional:

```razor
@directive(-suffix(:name))(="value")
```

Nella tabella seguente sono riepilogati i vari attributi per le direttive Razor utilizzate in Blazor.

|Attributo    |Descrizione|Esempio|
|-------------|-----------|-------|
|`@attributes`|Esegue il rendering di un dizionario di attributi|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Crea un'associazione dati bidirezionale    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Aggiunge un gestore eventi per l'evento specificato|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Specifica una chiave che deve essere utilizzata dall'algoritmo di diffing per mantenere gli elementi in una raccolta|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Acquisisce un riferimento al componente o all'elemento HTML|`<MyDialog @ref="myDialog" />`|

I vari attributi di direttiva`@onclick`utilizzati da Blazor ( , `@bind`, `@ref`e così via) sono trattati nelle sezioni seguenti e nei capitoli successivi.

Molte delle sintassi utilizzate nei file *aspx* e *ascx* hanno sintassi parallele in Razor. Di seguito è riportato un semplice confronto delle sintassi per ASP.NET Web Form e Razor.

|Funzionalità                      |Web Form           |Sintassi               |Razor         |Sintassi |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Direttive                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Blocchi di codice                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Espressioni<br>(codifica HTML)|`<%: %>`            |`<%:DateTime.Now %>` |Implicita:`@`<br>Esplicito:`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Commenti                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|Associazione dati                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Per aggiungere membri alla classe del `@code` componente Razor, utilizzare la direttiva . Questa tecnica è simile `<script runat="server">...</script>` all'utilizzo di un blocco in un controllo utente o in una pagina Web Form ASP.NET.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Poiché Razor è basato su C, deve essere compilato all'interno di un progetto C ,*csproj*. Non è possibile compilare file *con estensione razor* da un progetto Visual Basic (*vbproj*). È comunque possibile fare riferimento a progetti visual basic dal progetto Blazor. È vero anche il contrario.

Per un riferimento completo alla sintassi Razor, vedere Informazioni di riferimento sulla [sintassi Razor per ASP.NET Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>Usare i componenti

Oltre al normale HTML, i componenti possono anche utilizzare altri componenti come parte della logica di rendering. La sintassi per l'utilizzo di un componente in Razor è simile all'utilizzo di un controllo utente in un'app Web Form ASP.NET. I componenti vengono specificati utilizzando un tag di elemento che corrisponde al nome del tipo del componente. Ad esempio, è `Counter` possibile aggiungere un componente simile al seguente:For example, you can add a component like this:

```razor
<Counter />
```

A differenza di Web Form ASP.NET, i componenti in Blazor:

- Non utilizzare un prefisso di `asp:`elemento ( ad esempio, ).
- Non richiedere la registrazione nella pagina o nel *file web.config*.

Pensate ai componenti Razor come si farebbe tipi .NET, perché questo è esattamente quello che sono. Se si fa riferimento all'assieme contenente il componente, il componente è disponibile per l'utilizzo. Per inserire lo spazio dei nomi `@using` del componente nell'ambito, applicare la direttiva:To bring the component's namespace into scope, apply the directive:

```razor
@using MyComponentLib

<Counter />
```

Come illustrato nei progetti Blazor predefiniti, è `@using` comune inserire le direttive in un file *_Imports.razor* in modo che vengano importate in tutti i file *con estensione razor* nella stessa directory e nelle directory figlio.

Se lo spazio dei nomi per un componente non si trova nell'ambito, è possibile specificare un componente usando il nome completo del tipo, come è possibile in C:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Parametri del componente

In ASP.NET Web Form è possibile eseguire il flusso di parametri e dati ai controlli utilizzando le proprietà pubbliche. Queste proprietà possono essere impostate nel markup utilizzando gli attributi o impostate direttamente nel codice. I componenti Blazor funzionano in modo simile, anche `[Parameter]` se le proprietà del componente devono anche essere contrassegnate con l'attributo per essere considerate parametri del componente.

Il `Counter` componente seguente definisce `IncrementAmount` un parametro del componente chiamato `Counter` che può essere utilizzato per specificare la quantità che deve essere incrementata ogni volta che si fa clic sul pulsante.

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

Per specificare un parametro del componente in Blazor, utilizzare un attributo come in ASP.NET Web Form:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>Gestori eventi

Sia ASP.NET Web Form che Blazor forniscono un modello di programmazione basato su eventi per la gestione degli eventi dell'interfaccia utente. Esempi di tali eventi includono i clic sui pulsanti e l'input di testo. In ASP.NET Web Form, si utilizzano i controlli server HTML per gestire gli eventi dell'interfaccia utente esposti dal DOM oppure è possibile gestire gli eventi esposti dai controlli server Web. Gli eventi vengono visualizzati nel server tramite le richieste di postback del form. Si consideri il seguente esempio di clic sul pulsante Web Form:

*Contatore.ascx*

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

In Blazor è possibile registrare i gestori per gli `@on{event}`eventi dell'interfaccia utente DOM direttamente utilizzando gli attributi della direttiva nel formato . Il `{event}` segnaposto rappresenta il nome dell'evento. Ad esempio, è possibile ascoltare i clic sui pulsanti in questo modo:For example, you can listen for button clicks like this:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

I gestori eventi possono accettare un argomento facoltativo specifico dell'evento per fornire ulteriori informazioni sull'evento. Ad esempio, gli eventi `MouseEventArgs` del mouse possono accettare un argomento, ma non è obbligatorio.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

Anziché fare riferimento a un gruppo di metodi per un gestore eventi, è possibile usare un'espressione lambda. Un'espressione lambda consente di chiudere su altri valori nell'ambito.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

I gestori eventi possono essere eseguiti in modo sincrono o asincrono. Ad esempio, `OnClick` il gestore eventi seguente viene eseguito in modo asincrono:For example, the following event handler executes asynchronously:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

Dopo la gestione di un evento, viene eseguito il rendering del componente per tenere conto delle modifiche apportate allo stato del componente. Con i gestori eventi asincroni, il rendering del componente viene eseguito immediatamente dopo il completamento dell'esecuzione del gestore. Il rendering del componente `Task` viene *eseguito nuovamente* dopo il completamento dell'asincrono. Questa modalità di esecuzione asincrona offre l'opportunità di eseguire il rendering di un'interfaccia utente appropriata mentre l'asincrono `Task` è ancora in corso.

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

I componenti possono inoltre definire i propri `EventCallback<TValue>`eventi definendo un parametro di componente di tipo . I callback di eventi supportano tutte le varianti dei gestori eventi dell'interfaccia utente DOM: argomenti facoltativi, sincroni o asincroni, gruppi di metodi o espressioni lambda.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>Associazione dati

Blazor fornisce un semplice meccanismo per associare i dati da un componente dell'interfaccia utente allo stato del componente. Questo approccio è diverso dalle funzionalità di ASP.NET Web Form per l'associazione di dati da origini dati ai controlli dell'interfaccia utente. Nella sezione Gestione dei [dati](data.md) verrà illustrato il trattamento dei dati provenienti da origini dati diverse.

Per creare un'associazione dati bidirezionale da un componente dell'interfaccia utente allo stato del componente, usare l'attributo della `@bind` direttiva. Nell'esempio seguente, il valore della casella `isChecked` di controllo è associato al campo.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

Quando viene eseguito il rendering del componente, il `isChecked` valore della casella di controllo viene impostato sul valore del campo. Quando l'utente attiva o `onchange` disattiva la `isChecked` casella di controllo, l'evento viene generato e il campo viene impostato sul nuovo valore. La `@bind` sintassi in questo caso è equivalente al markup seguente:The syntax in this case is equivalent to the following markup:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Per modificare l'evento utilizzato per `@bind:event` l'associazione, utilizzare l'attributo .

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

I componenti possono inoltre supportare l'associazione dati ai relativi parametri. Per l'associazione dati, definire un parametro di callback eventi con lo stesso nome del parametro associabile. Il suffisso "Changed" viene aggiunto al nome.

*PasswordBox.razor*

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

Per concatenare un'associazione dati a un elemento dell'interfaccia utente sottostante, imposta il valore e gestisci l'evento direttamente nell'elemento dell'interfaccia utente anziché usare l'attributo. `@bind`

Per eseguire l'associazione `@bind-{Parameter}` a un parametro del componente, utilizzare un attributo per specificare il parametro a cui si desidera eseguire l'associazione.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Modifiche stato

Se lo stato del componente è stato modificato al di fuori di un normale callback di eventi o eventi dell'interfaccia utente, il componente deve segnalare manualmente che deve essere eseguito nuovamente il rendering. Per segnalare che lo stato di `StateHasChanged` un componente è cambiato, chiamare il metodo sul componente.

Nell'esempio seguente, un componente visualizza `AppState` un messaggio da un servizio che può essere aggiornato da altre parti dell'app. Il componente registra `StateHasChanged` il `AppState.OnChange` relativo metodo con l'evento in modo che il componente viene eseguito il rendering ogni volta che il messaggio viene aggiornato.

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

## <a name="component-lifecycle"></a>Ciclo di vita dei componenti

Il framework Web Form ASP.NET dispone di metodi del ciclo di vita ben definiti per moduli, pagine e controlli. Ad esempio, il controllo seguente implementa `Init` `Load`i `UnLoad` gestori eventi per gli eventi del ciclo di vita , , e :

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

I componenti Blazor hanno anche un ciclo di vita ben definito. Il ciclo di vita di un componente può essere utilizzato per inizializzare lo stato del componente e implementare comportamenti avanzati del componente.

Tutti i metodi del ciclo di vita dei componenti di Blazor hanno versioni sincrone e asincrone. Il rendering dei componenti è sincrono. Non è possibile eseguire la logica asincrona come parte del rendering del componente. Tutta la logica asincrona `async` deve essere eseguita come parte di un metodo del ciclo di vita.

### <a name="oninitialized"></a>OnInitialized (in grado di essere inizializzato)

I `OnInitialized` `OnInitializedAsync` metodi e vengono utilizzati per inizializzare il componente. Un componente viene in genere inizializzato dopo il primo rendering. Dopo l'inizializzazione di un componente, è possibile che venga eseguito il rendering più volte prima che venga eliminato. Il `OnInitialized` metodo è `Page_Load` simile all'evento in ASP.NET pagine e controlli Web Form.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

I `OnParametersSet` `OnParametersSetAsync` metodi e vengono chiamati quando un componente ha ricevuto parametri dal relativo elemento padre e il valore vengono assegnati alle proprietà. Questi metodi vengono eseguiti dopo l'inizializzazione del componente e *ogni volta che viene eseguito il rendering del componente.*

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

I `OnAfterRender` `OnAfterRenderAsync` metodi e vengono chiamati al termine del rendering di un componente. I riferimenti a elementi e componenti vengono popolati a questo punto (ulteriori informazioni su questi concetti di seguito). L'interattività con il browser è abilitata a questo punto. Le interazioni con l'esecuzione di DOM e JavaScript possono avvenire in modo sicuro.

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

Il `firstRender` parametro è `true` la prima volta che viene eseguito il rendering del componente; in caso contrario, il relativo valore è `false`.

### <a name="idisposable"></a>IDisposable

I componenti Blazor possono implementare `IDisposable` per eliminare le risorse quando il componente viene rimosso dall'interfaccia utente. Un componente Razor `IDispose` può `@implements` implementare utilizzando la direttiva:A Razor component can implement by using the directive:

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

## <a name="capture-component-references"></a>Acquisire riferimenti ai componenti

In ASP.NET Web Form, è comune modificare un'istanza del controllo direttamente nel codice facendo riferimento al relativo ID. In Blazor, è anche possibile catturare e manipolare un riferimento a un componente, anche se è molto meno comune.

Per acquisire un riferimento al componente in `@ref` Blazor, usare l'attributo della direttiva. Il valore dell'attributo deve corrispondere al nome di un campo impostabile con lo stesso tipo del componente di riferimento.

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

Quando viene eseguito il rendering del componente padre, il campo viene popolato con l'istanza del componente figlio. È quindi possibile chiamare i metodi sull'istanza del componente o modificare in altro modo.

La modifica diretta dello stato del componente tramite i riferimenti dei componenti non è consigliata. In questo modo si impedisce il rendering automatico del componente nei momenti corretti.

## <a name="capture-element-references"></a>Riferimenti agli elementi di acquisizione

I componenti Blazor possono acquisire riferimenti a un elemento. A differenza dei controlli server HTML in ASP.NET Web Form, non è possibile modificare il DOM direttamente utilizzando un riferimento all'elemento in Blazor. Blazor gestisce la maggior parte delle interazioni DOM per l'utente utilizzando il relativo algoritmo di diffing DOM. I riferimenti agli elementi acquisiti in Blazor sono opachi. Tuttavia, vengono utilizzati per passare un riferimento a un elemento specifico in una chiamata di interoperabilità JavaScript.However, they're used to pass a specific element reference in a JavaScript interop call. Per ulteriori informazioni sull'interoperabilità JavaScript, vedere [ASP.NETcore Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).

## <a name="templated-components"></a>Componenti basati su modelli

In ASP.NET Web Form è possibile creare *controlli basati su modelli.* I controlli basati su modelli consentono allo sviluppatore di specificare una parte del codice HTML utilizzato per eseguire il rendering di un controllo contenitore. I meccanismi di creazione di controlli server basati su modelli sono complessi, ma consentono scenari potenti per il rendering dei dati in modo personalizzabile dall'utente. Esempi di controlli `Repeater` basati su modelli includono e `DataList`.

I componenti Blazor possono anche essere basati su modelli definendo parametri di tipo `RenderFragment` componente o `RenderFragment<T>`. Oggetto `RenderFragment` rappresenta un blocco di Razor markup che può quindi essere eseguito il rendering dal componente. Un `RenderFragment<T>` è un blocco di Razor markup che accetta un parametro che può essere specificato quando viene eseguito il rendering del frammento di rendering.

### <a name="child-content"></a>Contenuto per bambini

I componenti Blazor possono acquisire `RenderFragment` il contenuto figlio come e renderizzarlo come parte del rendering del componente. Per acquisire contenuto figlio, definire `RenderFragment` un parametro del componente di tipo e denominarlo `ChildContent`.

*ChildContentComponent.razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

Un componente padre può quindi fornire contenuto figlio utilizzando la normale sintassi Razor.A parent component can then supply child content using normal Razor syntax.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>Parametri del modello

Un componente Blazor basato su modelli `RenderFragment` può `RenderFragment<T>`inoltre definire più parametri del componente di tipo o . Il parametro `RenderFragment<T>` per un oggetto può essere specificato quando viene richiamato. Per specificare un parametro di `@typeparam` tipo generico per un componente, utilizzare la direttiva Razor.

*SimpleListView.razor*

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

Quando si utilizza un componente basato su modelli, i parametri del modello possono essere specificati utilizzando elementi figlio che corrispondono ai nomi dei parametri. Gli argomenti `RenderFragment<T>` del componente di tipo `context`passato come elementi dispongono di un parametro implicito denominato . È possibile modificare il nome di `Context` questo parametro di implementazione utilizzando l'attributo nell'elemento figlio. È possibile specificare qualsiasi parametro di tipo generico utilizzando un attributo che corrisponde al nome del parametro di tipo. Il parametro di tipo verrà dedotto se possibile:The type parameter will be inferred if possible:

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

L'output di questo componente è simile al seguente:The output of this component looks like this:

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>Code-behind

Un componente Blazor viene in genere creato in un singolo file *.razor.* Tuttavia, è anche possibile separare il codice e il markup utilizzando un file code-behind. Per utilizzare un file di componente, aggiungere un file di C, che corrisponda al nome del file del componente ma con l'estensione *cs* aggiunta (*Counter.razor.cs*). Utilizzare il file di C , per definire una classe di base per il componente. È possibile denominare la classe base in qualsiasi elemento desiderato, ma è comune denominare la classe come la classe del componente, ma con un'estensione `Base` aggiunta ( ).`CounterBase` Anche la classe basata `ComponentBase`su componenti deve derivare da . Quindi, nel file del componente `@inherits` Razor, aggiungere la direttiva`@inherits CounterBase`per specificare la classe di base per il componente ( ).

*Contatore.rasoio*

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

La visibilità dei membri del componente nella `protected` `public` classe base deve essere o deve essere visibile alla classe del componente.

## <a name="additional-resources"></a>Risorse aggiuntive

Il precedente non è un trattamento esaustivo di tutti gli aspetti dei componenti Blazor. Per ulteriori informazioni su come [creare e utilizzare ASP.NET componenti Core Razor](/aspnet/core/blazor/components), vedere la documentazione di Blazor .

>[!div class="step-by-step"]
>[Successivo](app-startup.md)
>[precedente](pages-routing-layouts.md)
