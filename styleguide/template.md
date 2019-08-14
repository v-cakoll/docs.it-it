---
title:
- TITOLO ARTICOLO
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - mm/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: 0e8548745768bc9137e8fc76f86fc9fc7982b8de
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "68616351"
---
# <a name="metadata-and-markdown-template"></a>Modello Markdown e metadati

Il modello di dotnet/docs contiene esempi di sintassi di Markdown, nonché indicazioni su come impostare i metadati. Per esaminarne la maggior parte, è necessario visualizzare sia il [Markdown non elaborato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) che la [visualizzazione sottoposta a rendering](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (ad esempio, il Markdown non elaborato mostra il blocco dei metadati, che non è visibile nella visualizzazione sottoposta a rendering).

Quando si crea un file Markdown, è necessario copiare il modello in un nuovo file, compilare i metadati come specificato di seguito, impostare l'intestazione H1 sopra il titolo dell'articolo ed eliminare il contenuto.

## <a name="metadata"></a>Metadati

Il blocco di metadati completo è nella parte superiore (in formato [Markdown non elaborato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), suddiviso in campi obbligatori e facoltativi. Alcune note importanti:

- È **necessario** includere uno spazio tra i due punti (:) e il valore di un elemento di metadati.
- Se a un elemento di metadati facoltativo non è associato un valore, impostare l'elemento come commento con un # o rimuoverlo (non lasciarlo vuoto o usare "na"). Se si aggiunge un valore a un elemento impostato come commento, assicurarsi di rimuovere il simbolo #.
- La presenza dei due punti in un valore (ad esempio, un titolo) causa l'interruzione del parser dei metadati. In questo caso, racchiudere il titolo tra virgolette doppie (ad esempio, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: viene visualizzato nei risultati del motore di ricerca. Il titolo non deve essere identico al titolo nell'intestazione H1 e può contenere al massimo 60 caratteri.
- **description**: riepiloga il contenuto dell'articolo. In genere, viene visualizzato nella pagina dei risultati della ricerca ma non viene usato per classificare i risultati. La lunghezza deve essere inclusa tra 115 e 145 caratteri, spazi inclusi.
- **author** e **ms.author**: il campo dell'autore deve contenere il **nome utente GitHub** dell'autore, non il relativo alias.  Il campo **ms.author** deve contenere invece un alias Microsoft e indica la persona responsabile della gestione dell'articolo.
- **ms.topic**: tipo di argomento. Il valore più comune è `conceptual` e viene impostato a livello globale. Altri valori comunemente usati sono `tutorial`, `overview` e `reference`.
- **ms.devlang** definisce il filtro linguaggio visualizzato per l'argomento. È possibile visualizzare un elenco dei valori supportati nella sezione [Linguaggi supportati](#supported-languages). Deve essere impostato solo se nell'argomento è presente più di un linguaggio di programmazione. Nei contenuti trattati, per questo valore vengono generalmente usati solo `csharp`, `vb`, `fsharp` e `cpp`.
- **ms.prod**: identificazione del prodotto usata per scopi di business intelligence. In genere, viene impostato a livello globale e non viene quindi visualizzato nel blocco di metadati di ogni articolo.
- **ms.technology**: classificazione di business intelligence aggiuntiva. Alcuni dei valori supportati sono: `devlang-csharp` per gli argomenti su C#, `devlang-fsharp` per gli argomenti su F# e `devlang-visual-basic` per gli argomenti su VB. Per le altre guide, i valori sono diversi ed è quindi opportuno chiedere al membro del team per informazioni in proposito.
- **ms.date**: data nel formato MM/gg/aaaa. Viene visualizzata nella pagina pubblicata per indicare l'ultima volta in cui l'articolo è stato modificato in modo sostanziale o garantito "aggiornato" (l'articolo è stato esaminato e considerato aggiornato).
- **helpviewer_keywords**: voci usate per l'indice dei libri offline (funzionalità di Visual Studio).
- **f1_keywords**: connette l'articolo al tasto F1 (funzionalità di Visual Studio).

## <a name="basic-markdown-gfm-and-special-characters"></a>Markdown di base, GFM e caratteri speciali

Sono supportati sia Markdown di base che GitHub Flavored Markdown (GFM). Per altre informazioni su questi elementi, vedere:

- [Sintassi Markdown di base](https://daringfireball.net/projects/markdown/syntax)
- [Documentazione di GFM](https://guides.github.com/features/mastering-markdown)

Markdown usa caratteri speciali, ad esempio \*, \` e \#, per la formattazione. Se si vuole includere uno di questi caratteri nel contenuto, è necessario eseguire una delle seguenti operazioni:

- Inserire una barra rovesciata prima del carattere speciale come "escape" (ad esempio, `\*` per \*)
- Usare il [codice entità HTML](https://www.ascii.cl/htmlcodes.htm) per il carattere (ad esempio, `&#42;` per &#42;).

## <a name="file-name"></a>Nome file

Per i nomi di file vengono usate le regole seguenti:

* Devono contenere solo lettere minuscole, numeri e trattini.
* Non possono contenere spazi o caratteri di punteggiatura. Usare i trattini per separare le parole e i numeri nel nome del file.
* Usare verbi di azione specifici, ad esempio sviluppare, acquistare, compilare, risolvere i problemi. Evitare i sostantivi.
* Non includere parole brevi, come un, e, il, in, o e così via.
* Usare il formato Markdown e l'estensione di file md.
* Mantenere i nomi di file relativamente brevi. Fanno parte dell'URL degli articoli.

## <a name="headings"></a>Intestazioni

Usare l'iniziale maiuscola solo per la prima parola. Scrivere sempre in maiuscolo:

- La prima parola di un'intestazione.
- La parola che segue i due punti in un titolo o un'intestazione (ad esempio, "Procedura: Ordinare una matrice").

È necessario creare le intestazioni in stile atx, ovvero usare 1-6 simboli di cancelletto (#) all'inizio della riga per indicare un'intestazione, corrispondenti ai livelli delle intestazioni HTML da H1 a H6. Alcuni esempi di intestazioni di primo e secondo livello sono stati usati in precedenza.

Nell'argomento **deve** essere presente una sola intestazione di primo livello (H1), che verrà visualizzata come titolo della pagina.

Se l'intestazione termina con un carattere `#`, è necessario aggiungere un ulteriore carattere `#` alla fine per garantire che il rendering del titolo venga eseguito correttamente. Ad esempio `# Async Programming in F# #`.

Le intestazioni di secondo livello verranno usate per generare il sommario della pagina, visualizzato nella sezione "Contenuto dell'articolo" sotto il titolo della pagina.

### <a name="third-level-heading"></a>Intestazione di terzo livello
#### <a name="fourth-level-heading"></a>Intestazione di quarto livello
##### <a name="fifth-level-heading"></a>Intestazione di quinto livello
###### <a name="sixth-level-heading"></a>Intestazione di sesto livello

## <a name="text-styling"></a>Stile del testo

*Corsivo*: da usare per file, cartelle, percorsi (posizionare gli elementi lunghi su una riga distinta), nuovi termini.

**Grassetto**: da usare per gli elementi dell'interfaccia utente.

`Code` usarlo per il codice inline, le parole chiave del linguaggio, i nomi di pacchetti NuGet, i comandi della riga di comando, i nomi di tabella e colonna del database e gli URL sui quali non è possibile fare clic.

## <a name="links"></a>Collegamenti

### <a name="internal-links"></a>Collegamenti interni

Per creare un collegamento a un'intestazione nello stesso file Markdown (anche denominato collegamento di ancoraggio), è necessario individuare l'ID dell'intestazione da collegare. Per verificare l'ID, visualizzare l'origine dell'articolo sottoposto a rendering, trovare l'ID dell'intestazione (ad esempio, `id="blockquote"`) e specificare il collegamento usando il simbolo # e l'ID (ad esempio, `#blockquote`).
L'ID viene generato automaticamente in base al testo dell'intestazione. Ad esempio, per una sezione univoca denominata `## Step 2`, l'ID sarà simile a `id="step-2"`.

- Esempio: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produce [Dichiara blocchi inline con un identificatore di lingua](#inline-code-blocks-with-language-identifier).

Per creare un collegamento a un file Markdown nello stesso repository, usare [collegamenti relativi](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), includendo "md" alla fine del nome del file.

- Esempio: `[Readme file](../README.md)` produce [File leggimi](../README.md). Questi valori distinguono tra maiuscole e minuscole.
- Esempio: `[Welcome to .NET](../docs/welcome.md)` produce [Introduzione a .NET](../docs/welcome.md).

Per creare un collegamento a un'intestazione in un file Markdown nello stesso repository, usare il collegamento relativo e il collegamento con hashtag.

- Esempio: `[.NET Community](../docs/welcome.md#open-source)` produce [Community .NET](../docs/welcome.md#open-source).

Nella maggior parte dei casi si usano collegamenti relativi e si sconsiglia l'uso di `~/` nei collegamenti, perché i collegamenti relativi vengono risolti nell'origine in GitHub. Tuttavia quando si definisce il collegamento a un file in un repository dipendente, viene usato il carattere `~/` per fornire il percorso. Dato che i file nel repository dipendente si trovano in una posizione diversa in GitHub, i collegamenti non vengono risolti correttamente con collegamenti relativi, indipendentemente da come sono stati scritti.

La specifica del linguaggio C# e la specifica del linguaggio Visual Basic sono incluse nei documenti .NET mediante l'aggiunta dell'origine dai repository del linguaggio. Le origini di markdown vengono gestite nei repository [csharplang](https://github.com/dotnet/csharplang) e [visual basic](https://github.com/dotnet/vblang).

I collegamenti a una specifica devono fare riferimento alle directory di origine che includono le specifiche corrispondenti. Per C# la directory è **~/_csharplang/spec** e per VB la directory è **~/_vblang/spec**.

- Esempio: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` genera [Espressioni di query C#](~/_csharplang/spec/expressions.md#query-expressions).

### <a name="external-links"></a>Collegamenti esterni

Per creare un collegamento a un file esterno, usare l'URL completo come collegamento.

- Esempio: `[GitHub](https://www.github.com)` genera [GitHub](https://www.github.com).

Se un file Markdown contiene un URL, questo verrà trasformato in un collegamento ipertestuale.

- Esempio: `<https://www.github.com>` genera <https://www.github.com>.

Preferire il protocollo `https` per i collegamenti esterni. Usare i collegamenti `http` solo per i siti che non supportano `https`.

### <a name="links-to-apis"></a>Collegamenti ad API

Il sistema di compilazione dispone di alcune estensioni che consentono di collegare API .NET senza che sia necessario usare collegamenti esterni.
Quando si crea un collegamento a un'API, è possibile usare il relativo identificatore univoco (UID), che viene generato automaticamente dal codice sorgente.

L'UID equivale al nome completo di tipo e membro.

Se si aggiunge \* (o %2A) dopo l'UID, il collegamento rappresenta la pagina di overload e non un'API specifica. È ad esempio possibile usare questa opzione per creare un collegamento alla pagina [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) in modo generico anziché un overload specifico come [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_). È anche possibile usare \* per il collegamento a una pagina membro quando il membro non è in overload; in questo modo, è possibile evitare di includere l'elenco di parametri nell'UID.

Per il collegamento all'overload di un metodo specifico, è necessario includere il nome del tipo completo di ciascun parametro del metodo. Ad esempio, \<xref:System.DateTime.ToString> definisce il collegamento al metodo senza parametri [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString), mentre \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> definisce il collegamento al metodo [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_). È possibile trovare gli UID di un particolare membro di overload in `https://xref.docs.microsoft.com/autocomplete`. La stringa di query "?text= *\<type-member-name>* " identifica il tipo o il membro di cui si vogliono visualizzare gli UID. Ad esempio, `https://xref.docs.microsoft.com/autocomplete?text=string.format` recupera gli overload di [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).

Per il collegamento a un tipo generico, ad esempio [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), usare il carattere ` (%60) seguito dal numero dei parametri di tipo generico. Ad esempio, \<xref:System.Nullable%601> definisce il collegamento al tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), mentre \<xref:System.Func%602> definisce il collegamento al delegato [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).

È possibile usare una delle sintassi seguenti:

1. Collegamento automatico: `<xref:UID>` o `<xref:UID?displayProperty=nameWithType>`

   Il parametro di query `displayProperty` produce un testo di collegamento completo. Per impostazione predefinita, il testo del collegamento mostra solo il nome del membro o del tipo.

2. Collegamento Markdown:`[link text](xref:UID)`

   Può essere usato quando si vuole personalizzare il testo del collegamento visualizzato.

Esempi:

- `<xref:System.String>` viene visualizzato come [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` viene visualizzato come [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` viene visualizzato come [String class](https://docs.microsoft.com/dotnet/api/system.string)

Per altre informazioni sull'uso di questa notazione, vedere la pagina relativa all'[uso di riferimenti incrociati](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).

Di seguito sono illustrati i due modi disponibili per trovare l'UID:

- Visualizzare l'origine della pagina API a cui ci si vuole collegare e trovare il valore ms.assetid. Nell'origine, tuttavia, non vengono visualizzati i singoli valori di overload.
- Usare lo strumento seguente per cercare gli UID: https://xref.docs.microsoft.com/autocomplete?text=tostring (sostituire ToString con parti del nome dell'API che si sta tentando di trovare). Lo strumento cerca il parametro di query `text` specificato in qualsiasi parte dell'UID. Ad esempio è possibile cercare il nome membro (ToString), il nome membro parziale (ToStri), il tipo e il nome membro (Double.ToString) e così via.

Se l'UID contiene i caratteri speciali, \`, \# o \*, il valore dell'UID deve essere codificato in formato HTML, rispettivamente come `%60`, `%23` e `%2A`. A volte possono essere codificate anche le parentesi, ma non è obbligatorio.

Esempi:

- System.Threading.Tasks.Task\`1 diventa `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor diventa `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) diventa `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

## <a name="lists"></a>Elenchi

### <a name="ordered-lists"></a>Elenchi ordinati

1. This
1. È
1. Un
1. Ordered
1. Elenco

#### <a name="ordered-list-with-an-embedded-list"></a>Elenco ordinato con un elenco incorporato

1. Questo
1. è
1. any
1. incorporato
    1. Miss Scarlett
    1. Professor Plum
1. ordered
1. list

### <a name="unordered-lists"></a>Elenchi non ordinati

- This
- is
- a
- puntato
- list

#### <a name="unordered-list-with-an-embedded-list"></a>Elenco non ordinato con un elenco incorporato

- This
- puntato
- list
  - Signora Pavone
  - Dottor Verde
- contiene
- altro
  1. Colonnello Mustard
  1. Signora Bianchi
- elenchi

## <a name="horizontal-rule"></a>Righello orizzontale

---

## <a name="tables"></a>Tabelle

| Tabelle        | Sono           | Comode  |
| ------------- |:-------------:| -----:|
| col 3 è      | allineata a destra | $1600 |
| col 2 è      | centrata      |   $12 |
| col 1 è predefinita | allineata a sinistra     |    $1 |

Per creare le tabelle più facilmente, è possibile usare uno [strumento generatore di tabelle Markdown](https://www.tablesgenerator.com/markdown_tables).

## <a name="code"></a>Codice

Il modo migliore per includere codice consiste nell'includere frammenti di codice da un esempio funzionante. Creare l'esempio seguendo le istruzioni nella [guida alla creazione di contributi](../CONTRIBUTING.md#contributing-to-samples).

È possibile includere il codice usando la sintassi seguente:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* `-<language>` (*facoltativo* ma *consigliato*)
  * Linguaggio del frammento di codice al quale si fa riferimento. Per un elenco completo dei valori supportati, vedere [Linguaggi supportate](#supported-languages).

* `<name>` (*facoltativo*)
  * Nome del frammento di codice. Non deve avere alcun impatto sul file HTML di output ma può essere usato per rendere più leggibile l'origine del Markdown.

* `<pathToFile>` (*obbligatorio*)
  * Percorso relativo nel file system che indica il file del frammento di codice a cui fare riferimento.

* `<queryoption>` e `<queryoptionvalue>` (*facoltativi*)
  * Da usare insieme per specificare come deve essere recuperato il codice dal file:
    * `#`:  `#L{startlinenumber}-L{endlinenumber}` (intervallo di righe) *o* `#{tagname}` (nome del tag).
    L'uso dei numeri di riga è sconsigliato in quanto non sufficientemente affidabile. Il nome del tag è il metodo preferibile per il riferimento ai frammenti di codice.
    * `range`: `?range=1,3-5` Intervallo di righe. Questo esempio include le righe 1, 3, 4 e 5.
    * `dedent`: `?dedent=8` Riduce il rientro delle righe di un numero di spazi, in questo caso 8. Questo valore può essere combinato con `range` e altre opzioni di query che consentono di selezionare un subset di righe di un file.
    * `outdent`: `?outdent=8` Inverte il rientro delle righe di un numero di spazi, in questo caso 8. Questo valore può essere combinato con `range` e altre opzioni di query che consentono di selezionare un subset di righe di un file.

Se possibile, è sempre consigliabile usare l'opzione del nome del tag. Il nome del tag è il nome di un'area o di un commento di codice nel formato `Snippettagname` presente nel codice di origine. L'esempio seguente illustra come creare un riferimento al nome di tag `1`:

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

È anche possibile vedere come sono strutturati i tag dei frammenti di codice in [questo file di origine](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs). Per altri dettagli sulla rappresentazione dei nomi di tag nei file di origine dei frammenti di codice in base al linguaggio, vedere le [linee guida per DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

L'inclusione di frammenti di codice da programmi completi assicura che tutto il codice venga eseguito tramite il sistema di Integrazione continua. Se tuttavia è necessario mostrare un elemento che causa errori di runtime o in fase di compilazione, è possibile usare i blocchi di codice inline.

### <a name="inline-code-blocks-with-language-identifier"></a>Blocchi di codice inline con identificatore del linguaggio

Usare tre apici (\`\`\`) e un ID di linguaggio per applicare il codice a colori di uno specifico linguaggio a un blocco di codice. Di seguito è riportato l'elenco dei linguaggi supportati, con l'etichetta Markdown per ogni ID di lingua.

#### <a name="supported-languages"></a>Lingue supportate

|nome|Etichetta Markdown|
|-----|-------|
|ASP.NET con C#|aspx-csharp|
|ASP.NET con VB|aspx-vb|
|Interfaccia della riga di comando di Azure|azurecli|
|AzCopy|azcopy|
|C++|cpp|
|C#|csharp|
|C# nel browser|csharp-interactive|
|Console|console|
|F#|fsharp|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|NodeJS|nodejs|
|Objective-C|objc|
|PHP|php|
|PowerShell|powershell|
|Python|python|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|VB|VB|
|XAML|xaml|
|XML|xml|

Il nome `csharp-interactive` specifica il linguaggio C# e la possibilità di eseguire gli esempi dal browser. Questi frammenti vengono compilati ed eseguiti in un contenitore Docker e i risultati dell'esecuzione del programma vengono visualizzati nella finestra del browser dell'utente.

Di seguito sono riportati esempi di blocchi di codice che usano gli ID linguaggio per C# (\`\`\`csharp), Python (\`\`\`python) e PowerShell (\`\`\`powershell).

##### <a name="c9839"></a>C&#9839;

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a>Python

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a>PowerShell

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a>Blocco di codice generico

Usare tre apici (&#96;&#96;&#96;) per la codifica di un blocco di codice generico.

> L'approccio consigliato è usare blocchi di codice con identificatori di linguaggio, come illustrato nella sezione precedente, per garantire la corretta evidenziazione della sintassi nel sito della documentazione. Usare blocchi di codice generico solo quando necessario.

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a>Citazioni di paragrafi

> La siccità si protraeva ormai da dieci milioni di anni, e il regno delle terribili lucertole era finito da molto tempo. Lì, sull'Equatore, nel continente che un giorno sarebbe stato chiamato Africa, la lotta per la vita aveva raggiunto un nuovo diapason di ferocia, e il vincitore ancora non si intravedeva. In quella terra sterile e arida soltanto le creature piccole o fulminee o feroci potevano prosperare, o appena sperare di sopravvivere.

## <a name="images"></a>Immagini

### <a name="static-image-or-animated-gif"></a>Immagine statica o GIF animata

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![questo è il testo alternativo](../images/Logo_DotNet.png)

### <a name="linked-image"></a>Immagine collegata

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

[![testo alternativo per l'immagine collegata](../images/Logo_DotNet.png)](https://dot.net)

## <a name="videos"></a>Video

Attualmente è possibile incorporare video sia di Channel 9 che di YouTube con la sintassi seguente:

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

Per ottenere l'URL corretto del video, selezionare la scheda **Incorpora** sotto il fotogramma video e copiare l'URL dall'elemento `<iframe>`. Ad esempio:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Per ottenere l'URL corretto del video, fare clic con il pulsante destro del mouse sul video, selezionare **Copia codice di incorporamento** e copiare l'URL dall'elemento `<iframe>`.

```markdown
> [!VIDEO <youtube_video_link>]
```

Ad esempio:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>Estensioni docs.microsoft

docs.microsoft fornisce alcune estensioni aggiuntive a GitHub Flavored Markdown (GFM).

### <a name="alerts"></a>Avvisi

È importante usare gli stili di avviso seguenti, in modo che ne venga eseguito il rendering con lo stile appropriato nel sito della documentazione. Tuttavia, il motore di rendering in GitHub non li differenzia.

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

Il rendering sarà simile al seguente: ![Stili di avviso](../images/alerts.png)

### <a name="includes"></a>Include

È possibile incorporare il Markdown di un file in un altro usando un'inclusione.

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a>Elenchi selezionati

Per gli elenchi è disponibile uno stile personalizzato. È possibile eseguire il rendering degli elenchi con segni di spunta verdi.

> [!div class="checklist"]
> * Come creare un'app .NET Core
> * Come aggiungere un riferimento al pacchetto Microsoft.XmlSerializer.Generator
> * Come modificare il file MyApp.cspro per aggiungere dipendenze
> * Come aggiungere una classe e un oggetto XmlSerializer
> * Come compilare ed eseguire l'applicazione

È possibile vedere un esempio di elenchi selezionati in azione nella [documentazione di .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Pulsanti

> [!div class="button"]
> [collegamenti con pulsanti](../docs/core/index.md)

È possibile vedere un esempio di pulsanti in azione nella [documentazione di Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="selectors"></a>Selettori

> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)

È possibile vedere un esempio di selettori in azione nella [documentazione di Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).

### <a name="step-by-steps"></a>Procedure dettagliate

>[!div class="step-by-step"]
>[Precedente](../docs/csharp/expression-trees-interpreting.md)
>[Successivo](../docs/csharp/expression-trees-translating.md)

È possibile vedere un esempio di procedure dettagliate in azione nella [Guida di C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
