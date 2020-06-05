---
title: Novità in Visual Basic
ms.date: 10/24/2018
f1_keywords:
- VB.StartPage.WhatsNew
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
ms.openlocfilehash: a9bac04a7839796229a2e1c61771ca32573f8fcd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374512"
---
# <a name="whats-new-for-visual-basic"></a>Novità in Visual Basic

Questo argomento elenca i nomi delle funzionalità principali per ogni versione di Visual Basic, con descrizioni dettagliate delle funzionalità nuove e migliorate nelle più recenti versioni del linguaggio.

## <a name="current-version"></a>Versione corrente

Visual Basic 16,0/Visual Studio 2019 versione 16,0 \
Per le nuove funzionalità, vedere [Visual Basic 16,0](#visual-basic-160).

## <a name="previous-versions"></a>Versioni precedenti

Visual Basic 15,8/Visual Studio 2017 versione 15,8 \
Per le nuove funzionalità, vedere [Visual Basic 15,8](#visual-basic-158).

Visual Basic 15,5/Visual Studio 2017 versione 15,5 \
Per le nuove funzionalità, vedere [Visual Basic 15,5](#visual-basic-155).

Visual Basic 15,3/Visual Studio 2017 versione 15,3 \
Per le nuove funzionalità, vedere [Visual Basic 15,3](#visual-basic-153).

Visual Basic 2017/Visual Studio 2017 \
Per le nuove funzionalità, vedere [Visual Basic 2017](#visual-basic-2017).

Visual Basic/Visual Studio 2015 \
Per le nuove funzionalità, vedere [Visual Basic 14](#visual-basic-14).

Visual Basic/Visual Studio 2013 \
Anteprime tecnologiche del .NET Compiler Platform ("Roslyn")

Visual Basic/Visual Studio 2012 \
Parole chiave `Async` e `await`, iteratori, attributi relativi alle informazioni sul chiamante

Visual Basic, Visual Studio 2010 \
Proprietà implementate automaticamente, inizializzatori di insieme, continuazione di riga implicita, elementi dinamici, covarianza/controvarianza generica, accesso agli spazi dei nomi globali

Visual Basic/Visual Studio 2008 \
Language Integrated Query (LINQ), valori letterali XML, inferenza del tipo di variabile locale, inizializzatori di oggetto, tipi anonimi, metodi di estensione, inferenza del tipo `var` locale, espressioni lambda, operatore `if`, metodi parziali, tipi di valore nullable

Visual Basic/Visual Studio 2005 \
Tipo `My` e tipi di helper (accesso all'app, al computer, al file system, alla rete)

Visual Basic/Visual Studio .NET 2003 \
Operatori di scorrimento bit, dichiarazione di variabile del ciclo

Visual Basic/Visual Studio .NET 2002 \
Prima versione di Visual Basic .NET

## <a name="visual-basic-160"></a>Visual Basic 16,0

Visual Basic 16,0 è incentrato sulla fornitura di più funzionalità del runtime di Visual Basic (Microsoft. VisualBasic. dll) a .NET Core ed è la prima versione di Visual Basic incentrata su .NET Core. Molte parti del runtime di Visual Basic dipendono da WinForms e verranno aggiunte in una versione successiva di Visual Basic.

**Commenti consentiti in più posizioni all'interno delle istruzioni**

In Visual Basic 15,8 e versioni precedenti, i commenti sono consentiti solo su righe vuote, alla fine di un'istruzione o in punti specifici all'interno di un'istruzione in cui è consentita una continuazione di riga implicita. A partire da Visual Basic 16,0, i commenti sono consentiti anche dopo le continuazioni di riga esplicite e all'interno di un'istruzione su una riga che inizia con uno spazio seguito da un carattere di sottolineatura.

```vb
Public Sub Main()
    cmd.CommandText = ' Comment is allowed here without _
        "SELECT * FROM Titles JOIN Publishers " _ ' This is a comment
        & "ON Publishers.PubId = Titles.PubID " _
 _ ' This is a comment on a line without code
        & "WHERE Publishers.State = 'CA'"
End Sub
```

## <a name="visual-basic-158"></a>Visual Basic 15.8

**Ottimizzazione della conversione da virgola mobile a Integer**

Nelle versioni precedenti di Visual Basic, le prestazioni della conversione dei valori [Double](../language-reference/data-types/double-data-type.md) e [Single](../language-reference/data-types/single-data-type.md) in valori Integer erano relativamente scarse. Visual Basic 15.8 migliora significativamente le prestazioni delle conversioni di valori da virgola mobile a Integer quando il valore restituito da uno dei metodi seguenti viene passato a una delle [funzioni intrinseche di conversione di interi di Visual Basic](../language-reference/functions/type-conversion-functions.md) (CByte, CShort, CInt, CLng, CSByte, CUShort, CUInt, CULng) o quando per il valore restituito da uno dei metodi seguenti viene eseguito il cast implicito a un tipo Integer e [Option Strict](../language-reference/statements/option-strict-statement.md) è `Off`:

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Questa ottimizzazione consente un'esecuzione più rapida del codice, fino a due volte più rapida nei casi di esecuzione di un numero elevato di conversioni a tipi Integer. L'esempio seguente illustra alcune semplici chiamate di metodi interessati da questa ottimizzazione:

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

Si noti che in questo caso i valori a virgola mobile vengono troncati anziché arrotondati.

## <a name="visual-basic-155"></a>Visual Basic 15.5

[Argomenti denominati non finali](../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md#mixing-arguments-by-position-and-by-name)

In Visual Basic 15.3 e versioni precedenti, quando una chiamata al metodo includeva argomenti in base alla posizione e al nome, gli argomenti posizionali dovevano precedere gli argomenti denominati. A partire da Visual Basic 15,5, gli argomenti posizionali e denominati possono trovarsi in qualsiasi ordine, purché tutti gli argomenti fino all'ultimo argomento posizionale si trovino nella posizione corretta. Ciò è particolarmente utile quando gli argomenti denominati vengono utilizzati per rendere il codice più leggibile.

Ad esempio, la seguente chiamata al metodo ha due argomenti posizionali tra un argomento denominato. L'argomento denominato chiarisce che il valore 19 rappresenta un'età.

```vb
StudentInfo.Display("Mary", age:=19, #9/21/1998#)
```

[`Private Protected`modificatore di accesso ai membri](../language-reference/modifiers/private-protected.md)

Questa nuova combinazione di parole chiave definisce un membro accessibile da tutti i membri nella classe che lo contiene, oltre che dai tipi derivati dalla classe che lo contiene, ma solo se si trovano anche nell'assembly che lo contiene. Poiché le strutture non possono essere ereditate, è possibile applicare `Private Protected` solo ai membri di una classe.

**Separatore esadecimale/binario/ottali iniziale**

Visual Basic 2017 ha aggiunto il supporto del carattere di sottolineatura (`_`) come separatore di cifre. A partire da Visual Basic 15.5, è possibile usare il carattere di sottolineatura come separatore iniziale tra il prefisso e la cifra esadecimale, binaria o ottale. L'esempio seguente usa il separatore di cifra iniziali per definire 3.271.948.384 come numero esadecimale:

```vb
Dim number As Integer = &H_C305_F860
```

Per usare il carattere di sottolineatura come separatore iniziale, è necessario aggiungere l'elemento seguente al file di progetto (\*.vbproj) di Visual Basic:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="visual-basic-153"></a>Visual Basic 15.3

[**Inferenza di tupla denominata**](../programming-guide/language-features/data-types/tuples.md#inferred-tuple-element-names)

Quando si assegna il valore di elementi di tupla provenienti da variabili, Visual Basic deduce il nome degli elementi di tupla dai nomi di variabili corrispondenti; non è necessario assegnare esplicitamente un nome a un elemento di tupla. L'esempio seguente usa l'inferenza per creare una tupla con tre elementi denominati, `state`, `stateName`, e `capital`.

[!code-vb[Inferred tuple names](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

**Nuove opzioni del compilatore**

Il compilatore della riga di comando di Visual Basic ora supporta le opzioni [**-refout**](../reference/command-line-compiler/refout-compiler-option.md) e [**-refonly**](../reference/command-line-compiler/refonly-compiler-option.md) per il controllo dell'output degli assembly di riferimento. **-refout** definisce la directory di output dell'assembly di riferimento, mentre **-refonly** specifica che il risultato della compilazione può essere solo un assembly di riferimento.

## <a name="visual-basic-2017"></a>Visual Basic 2017

[**Tuple**](../programming-guide/language-features/data-types/tuples.md)

Le tuple sono una semplice struttura dei dati che viene solitamente usata per restituire più valori da una singola chiamata al metodo. In genere, per restituire più valori da un metodo, è necessario eseguire una delle operazioni seguenti:

- Definire un tipo personalizzato (`Class` o `Structure`). Si tratta di una soluzione complicata.

- Definire uno o più parametri `ByRef` e restituire un valore dal metodo.

Grazie al supporto per tuple di Visual Basic è possibile definire rapidamente una tupla, assegnare facoltativamente nomi semantici ai rispettivi valori e recuperare rapidamente i relativi valori. L'esempio seguente esegue il wrapping di una chiamata al metodo <xref:System.Int32.TryParse%2A> e restituisce una tupla.

[!code-vb[Tuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

A questo punto è possibile chiamare il metodo e gestire la tupla restituita con codice simile al seguente.

[!code-vb[ReturnTuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

**Valori letterali binari e separatori di cifre**

È possibile definire un valore letterale binario usando il prefisso `&B` o `&b`. È anche possibile usare il carattere di sottolineatura `_` come separatore di cifre per rendere il codice più leggibile. Nell'esempio seguente vengono usate entrambe le funzionalità per assegnare un valore `Byte` e visualizzarlo come un numero decimale, esadecimale e binario.

[!code-vb[Binary](../../../samples/snippets/visualbasic/getting-started/bin-example.vb#1)]

Per altre informazioni, vedere la sezione dedicata alle assegnazioni di valori letterali dei tipi di dati [Byte](../language-reference/data-types/byte-data-type.md#literal-assignments), [Integer](../language-reference/data-types/integer-data-type.md#literal-assignments), [Long](../language-reference/data-types/long-data-type.md#literal-assignments), [Short](../language-reference/data-types/short-data-type.md#literal-assignments), [SByte](../language-reference/data-types/sbyte-data-type.md#literal-assignments), [UInteger](../language-reference/data-types/uinteger-data-type.md#literal-assignments), [ULong](../language-reference/data-types/ulong-data-type.md#literal-assignments) e [UShort](../language-reference/data-types/ushort-data-type.md#literal-assignments).

[**Supporto per i valori restituiti di riferimento C#**](../programming-guide/language-features/procedures/ref-return-values.md)

A partire dalla versione 7.0, C# supporta i valori di riferimento restituiti. Pertanto, quando la chiamata al metodo riceve un valore di riferimento restituito, lo può modificare. Visual Basic non consente di creare metodi con valori di riferimento restituiti, ma consente di usare e modificare tali valori.

Ad esempio, la classe `Sentence` seguente scritta in C# include un metodo `FindNext` che rileva la parola successiva in una frase che inizia con una sottostringa specificata. La stringa viene restituita come valore di riferimento restituito. Una variabile `Boolean` passata dal riferimento al metodo indica se la ricerca ha avuto esito positivo. Ciò significa che, oltre a leggere il valore restituito, il chiamante può anche modificarlo e tale modifica viene riflessa nella `Sentence` classe.

[!code-csharp[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

In parole semplici, è possibile modificare la parola trovata nella frase usando un codice simile al seguente. Si noti che non si sta assegnando un valore al metodo, ma all'espressione che il metodo restituisce, ovvero il valore di riferimento restituito.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#1)]

Esiste tuttavia un problema con questo codice. Se non viene trovata una corrispondenza, il metodo restituisce la prima parola. L'esempio non esamina il valore dell'argomento `Boolean` per determinare se viene trovata una corrispondenza. Modifica quindi la prima parola se non esiste corrispondenza. Nell'esempio seguente questo problema viene risolto sostituendo la prima parola con la parola stessa se non esiste corrispondenza.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#2)]

Una soluzione migliore consiste nell'usare un metodo helper al quale il riferimento passa il valore di riferimento restituito. Il metodo helper può quindi modificare l'argomento passato dal riferimento. Nell'esempio seguente viene eseguita questa operazione.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

Per altre informazioni, vedere [valori restituiti di riferimento](../programming-guide/language-features/procedures/ref-return-values.md).

## <a name="visual-basic-14"></a>Visual Basic 14

[NameOf](../language-reference/operators/nameof.md)

È possibile ottenere il nome di stringa non qualificato di un tipo o di un membro, da usare in un messaggio di errore senza definire una stringa a livello di codice.  In questo modo il codice sarà corretto anche durante il refactoring.  Questa funzionalità è utile anche per l'associazione di collegamenti MVC (Modello-Vista-Controller) e la generazione di eventi di modifica di proprietà.

[Interpolazione di stringhe](../programming-guide/language-features/strings/interpolated-strings.md)

È possibile usare espressioni di interpolazione di stringhe per costruire stringhe.  Un'espressione di stringa interpolata è simile a una stringa di modello che contiene espressioni.  In relazione agli argomenti, è più facile comprendere una stringa interpolata che la [formattazione composita](../../standard/base-types/composite-formatting.md).

[Indicizzazione e accesso ai membri condizionali null](../language-reference/operators/null-conditional-operators.md)

È possibile verificare la presenza di valori null con una sintassi molto leggera prima di eseguire un'operazione di accesso ai membri (`?.`) o di indice (`?[]`).  Questi operatori consentono di scrivere meno codice per gestire i controlli null, soprattutto per l'ordinamento decrescente delle strutture di dati.  Se l'operando di sinistra o il riferimento a un oggetto è null, le operazioni restituiscono null.

[Valori letterali stringa a più righe](../programming-guide/language-features/strings/string-basics.md)

I valori letterali stringa possono contenere sequenze di nuove righe.  Non è più necessario usare `<xml><![CDATA[...text with newlines...]]></xml>.Value` come soluzione alternativa.

**Commenti**

È possibile inserire commenti dopo le continuazioni di riga implicita, all'interno delle espressioni dell'inizializzatore e tra i termini delle espressioni LINQ.

**Risoluzione dei nomi completi più intelligente**

In precedenza, con un codice come `Threading.Thread.Sleep(1000)`, Visual Basic cercava lo spazio dei nomi "Threading", individuava un'ambiguità tra System.Threading e System.Windows.Threading e quindi segnalava un errore.  Visual Basic ora prende in considerazione entrambi gli spazi dei nomi possibili.  Se si visualizza l'elenco di completamento, l'editor di Visual Studio elenca i membri di entrambi i tipi in questo elenco.

**Valori letterali data anno-primo**

I valori letterali data possono avere il formato aaaa-mm-gg, `#2015-03-17 16:10 PM#`.

**Proprietà dell'interfaccia ReadOnly**

È possibile implementare proprietà dell'interfaccia readonly usando una proprietà readonly. L'interfaccia garantisce la funzionalità minima e le classi di implementazione non smettono di consentire l'impostazione della proprietà.

[Non \<expr> typeof\<type>](../language-reference/operators/typeof-operator.md)

Per una maggiore leggibilità del codice, ora è possibile usare `TypeOf` con `IsNot`.

[Avviso #Disable \<ID> e #Enable avviso\<ID>](../language-reference/directives/index.md)

È possibile disabilitare e abilitare avvisi specifici per le aree all'interno di un file di origine.

**Miglioramenti dei commenti in formato documentazione XML**

Quando si scrivono commenti ai documenti, si accede a Smart Editor e al supporto per la compilazione per la convalida di nomi di parametro, la corretta gestione di `crefs` (generics, operatori e così via), la colorazione e il refactoring.

[Definizioni di interfacce e moduli parziali](../language-reference/modifiers/partial.md)

Oltre a classi e struct, è possibile dichiarare interfacce e moduli parziali.

[#Region direttive all'interno di corpi del metodo](../language-reference/directives/region-directive.md)

È possibile inserire delimitatori #Region...#End Region in qualsiasi punto di un file, nelle funzioni o nei corpi delle funzioni.

[Le definizioni delle sostituzioni sono overload impliciti](../language-reference/modifiers/overrides.md)

Se si aggiunge il modificatore `Overrides` a una definizione, il compilatore aggiunge in modo implicito `Overloads`. In questo modo è possibile digitare meno codice nella maggior parte dei casi.

**CObj consentito negli argomenti degli attributi**

Il compilatore generava un errore indicante che CObj(...), se usato nelle costruzioni degli attributi, non era una costante.

**Dichiarazione e utilizzo di metodi ambigui da interfacce diverse**

In precedenza il codice seguente restituiva errori che impedivano di dichiarare `IMock` o di chiamare `GetDetails` (se questi erano stati dichiarati in c#):

```vb
Interface ICustomer
  Sub GetDetails(x As Integer)
End Interface

Interface ITime
  Sub GetDetails(x As String)
End Interface

Interface IMock : Inherits ICustomer, ITime
  Overloads Sub GetDetails(x As Char)
End Interface

Interface IMock2 : Inherits ICustomer, ITime
End Interface
```

Ora il compilatore userà le normali regole di risoluzione dell'overload per scegliere l'oggetto `GetDetails` più appropriato da chiamare ed è possibile dichiarare le relazioni tre le interfacce in Visual Basic, come quelle mostrate nell'esempio.

## <a name="see-also"></a>Vedere anche

- [Novità di Visual Studio 2017](/visualstudio/ide/whats-new-visual-studio-2017)
- [Novità di Visual Studio 2019](/visualstudio/ide/whats-new-visual-studio-2019)
