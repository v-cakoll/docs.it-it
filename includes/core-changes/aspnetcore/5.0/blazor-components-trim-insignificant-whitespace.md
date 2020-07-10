---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174263"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a>Blazer: spazi vuoti non significativi rimossi dai componenti in fase di compilazione

A partire da ASP.NET Core 5,0 Preview 7, il compilatore Razor omette gli spazi vuoti non significativi nei componenti blazer (file*Razor* ) in fase di compilazione. Per informazioni, vedere Issue [DotNet/aspnetcore # 23568](https://github.com/dotnet/aspnetcore/issues/23568).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 7

#### <a name="old-behavior"></a>Comportamento precedente

Nelle versioni 3. x di Blazer server e del webassembly blazer, lo spazio vuoto viene rispettato nel codice sorgente di un componente. I nodi di testo con solo spazi vuoti vengono visualizzati nel DOM (Document Object Model) del browser anche quando non sono presenti effetti visivi.

Si consideri il seguente codice componente Blazer:

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

Nell'esempio precedente viene eseguito il rendering di due nodi dello spazio vuoto:

* All'esterno del `@foreach` blocco di codice.
* Intorno all' `<li>` elemento.
* Intorno all' `@item.Text` output.

Un elenco contenente 100 elementi restituisce i nodi con spazio 402. Questa è la metà di tutti i nodi di cui è stato eseguito il rendering, anche se nessuno dei nodi spazio ha effetto visivo sull'output sottoposto a rendering.

Quando si esegue il rendering del codice HTML statico per i componenti, gli spazi vuoti all'interno di un tag Ad esempio, visualizzare l'origine del componente seguente:

```razor
<foo        bar="baz"     />
```

Lo spazio vuoto non viene mantenuto. L'output di cui è stato eseguito il rendering è:

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a>Nuovo comportamento

A meno che la `@preservewhitespace` direttiva non venga usata con value `true` , i nodi dello spazio vuoto vengono rimossi se:

* Sono iniziali o finali all'interno di un elemento.
* Sono iniziali o finali in un `RenderFragment` parametro. Ad esempio, il contenuto figlio viene passato a un altro componente.
* Precede o segue un blocco di codice C#, ad esempio `@if` e `@foreach` .

#### <a name="reason-for-change"></a>Motivo della modifica

Uno degli obiettivi di Blazer in ASP.NET Core 5,0 è quello di migliorare le prestazioni del rendering e delle differenze. I nodi dell'albero degli spazi vuoti non significativi hanno consumato fino al 40% del tempo di rendering nei benchmark.

#### <a name="recommended-action"></a>Azione consigliata

Nella maggior parte dei casi, il layout visivo del componente di cui è stato eseguito il rendering non è interessato. Tuttavia, la rimozione degli spazi vuoti potrebbe influire sull'output sottoposto a rendering quando si usa una regola CSS come `white-space: pre` . Per disabilitare questa ottimizzazione delle prestazioni e mantenere lo spazio vuoto, effettuare una delle operazioni seguenti:

* Aggiungere la `@preservewhitespace true` direttiva all'inizio del file *Razor* per applicare la preferenza a un componente specifico.
* Aggiungere la `@preservewhitespace true` direttiva all'interno di un file *_Imports. Razor* per applicare la preferenza a un'intera sottodirectory o all'intero progetto.

Nella maggior parte dei casi, non è necessaria alcuna azione, perché le applicazioni in genere continuano a funzionare normalmente (ma più velocemente). Se la rimozione degli spazi vuoti causa problemi per un particolare componente, utilizzare `@preservewhitespace true` in tale componente per disabilitare questa ottimizzazione.

#### <a name="category"></a>Categoria

Risultato dell'azione di

#### <a name="affected-apis"></a>API interessate

Nessuno

<!--

#### Affected APIs

Not detectable via API analysis

-->
