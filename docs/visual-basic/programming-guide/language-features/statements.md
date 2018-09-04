---
title: Istruzioni in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506290"
---
# <a name="statements-in-visual-basic"></a>Istruzioni in Visual Basic

Un'istruzione in Visual Basic è un'istruzione completa. Può contenere le parole chiave, operatori, variabili, costanti ed espressioni. Ogni istruzione appartiene a una delle categorie seguenti:

- **Le istruzioni di dichiarazione**, che corrisponde a una variabile, costante o procedure e può anche specificare un tipo di dati.

- **Le istruzioni eseguibili**, quale avviare le operazioni. Queste istruzioni possono chiamare un metodo o funzione e possano ciclo o tramite i blocchi di codice. Includono le istruzioni eseguibili **istruzioni di assegnazione**, che consentono di assegnare un valore o un'espressione a una variabile o costante.

Questo argomento descrive ogni categoria. Inoltre, questo argomento descrive come combinare più istruzioni in una singola riga e su come continuare a un'istruzione su più righe.

## <a name="declaration-statements"></a>Istruzioni di dichiarazione

Utilizzare le istruzioni di dichiarazione per denominare e definire procedure, variabili, proprietà, matrici e costanti. Quando si dichiara un elemento di programmazione, è anche possibile definire il tipo di dati, il livello di accesso e ambito. Per altre informazioni, vedere [caratteristiche di elementi dichiarati](./declared-elements/declared-element-characteristics.md).

L'esempio seguente contiene tre dichiarazioni.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

È la prima dichiarazione il `Sub` istruzione. Con il tipo di corrispondenza `End Sub` istruzione dichiara una routine denominata `applyFormat`. Specifica che anche `applyFormat` è `Public`, il che significa che qualsiasi codice che può fare riferimento ad esso può chiamarlo.

La seconda dichiarazione è il `Const` istruzione che dichiara la costante `limit`, specificando il `Integer` tipo di dati e un valore pari a 33.

La terza dichiarazione è il `Dim` istruzione che dichiara la variabile `thisWidget`. Il tipo di dati è un oggetto specifico, vale a dire un oggetto creato dal `Widget` classe. È possibile dichiarare una variabile di qualsiasi tipo di dati elementare o di qualsiasi tipo di oggetto che viene esposto nell'applicazione in uso.

### <a name="initial-values"></a>Valori iniziali

Quando viene eseguito il codice che contiene un'istruzione di dichiarazione, Visual Basic si riserva di memoria necessaria per l'elemento dichiarato. Se l'elemento contiene un valore, Visual Basic lo inizializza sul valore predefinito per il tipo di dati. Per altre informazioni, vedere "Comportamento di" nella [istruzione Dim](../../language-reference/statements/dim-statement.md).

È possibile assegnare un valore iniziale a una variabile come parte della relativa dichiarazione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Se la variabile è una variabile oggetto, è possibile creare un'istanza della relativa classe in modo esplicito quando si dichiara tramite il [operatore New](../../../visual-basic/language-reference/operators/new-operator.md) (parola chiave), come illustrato nell'esempio seguente viene illustrato.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Si noti che il valore iniziale specificato in un'istruzione di dichiarazione non sia assegnato a una variabile fino a quando l'esecuzione raggiunge relativa istruzione di dichiarazione. Fino a quel momento, la variabile contiene il valore predefinito per il tipo di dati.

## <a name="executable-statements"></a>Istruzioni eseguibili

Un'istruzione eseguibile esegue un'azione. È possibile chiamare una routine, ramo da un'altra posizione nel codice, esecuzione di varie istruzioni, o valutare un'espressione. Un'istruzione di assegnazione è un caso speciale di un'istruzione eseguibile.

L'esempio seguente usa un `If...Then...Else` struttura di controllo per eseguire blocchi di codice in base al valore di una variabile. All'interno di ogni blocco di codice, un `For...Next` ciclo viene eseguito un numero di volte specificato.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

Il `If` istruzione nell'esempio precedente viene controllato il valore del parametro `clockwise`. Se il valore è `True`, chiama il `spinClockwise` metodo `aWidget`. Se il valore è `False`, chiama il `spinCounterClockwise` metodo `aWidget`. Il `If...Then...Else` struttura di controllo termina con `End If`.

Il `For...Next` ciclo all'interno di ogni blocco viene chiamato il metodo appropriato un numero di volte uguale al valore della `revolutions` parametro.

## <a name="assignment-statements"></a>Istruzioni di assegnazione

Istruzioni di assegnazione di eseguire operazioni di assegnazione, costituiti da prendendo il valore sul lato destro dell'operatore di assegnazione (`=`) e archiviarlo nell'elemento a sinistra, come nell'esempio seguente.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

Nell'esempio precedente, l'istruzione di assegnazione archivia il valore letterale 42 nella variabile `v`.

### <a name="eligible-programming-elements"></a>Elementi di programmazione idonei

L'elemento di programmazione sul lato sinistro dell'operatore di assegnazione deve essere in grado di accettare e archiviare un valore. Ciò significa che deve essere una variabile o proprietà che non è [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), o deve essere un elemento della matrice. Nel contesto di un'istruzione di assegnazione, tale elemento viene talvolta chiamato un' *lvalue*, per "valore a sinistra".

Il valore sul lato destro dell'operatore di assegnazione viene generato da un'espressione che può contenere qualsiasi combinazione di valori letterali, costanti, variabili, proprietà, gli elementi della matrice, altre espressioni o le chiamate di funzione. Questa condizione è illustrata nell'esempio seguente.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

Nell'esempio precedente viene aggiunto al valore contenuto nella variabile `y` sul valore incluso nella variabile `z`, quindi aggiunge il valore restituito dalla chiamata alla funzione `findResult`. Il valore totale di questa espressione viene quindi archiviato nella variabile `x`.

### <a name="data-types-in-assignment-statements"></a>Tipi di dati nelle istruzioni di assegnazione

Oltre a valori numerici, è possibile anche assegnare l'operatore di assegnazione `String` valori, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

È anche possibile assegnare `Boolean` valori, utilizzando un `Boolean` letterale o un `Boolean` espressione, come illustrato nell'esempio seguente viene illustrato.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Analogamente, è possibile assegnare i valori appropriati per elementi di programmazione del `Char`, `Date`, o `Object` tipo di dati. È anche possibile assegnare un'istanza dell'oggetto a un elemento dichiarato come della classe da cui viene creato tale istanza.

### <a name="compound-assignment-statements"></a>Istruzioni di assegnazione composta

*Istruzioni di assegnazione composta* innanzitutto eseguire un'operazione su un'espressione prima di assegnarlo a un elemento di programmazione. L'esempio seguente illustra uno di questi operatori, `+=`, il quale viene incrementato il valore della variabile sul lato sinistro dell'operatore tramite il valore dell'espressione a destra.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Nell'esempio precedente aggiunge 1 al valore di `n`e quindi archivia tale valore nuovo in `n`. Una sintassi abbreviata è equivalente dell'istruzione seguente:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Una serie di operazioni di assegnazione composto può essere eseguita usando gli operatori di questo tipo. Per un elenco di questi operatori e altre informazioni, vedere [gli operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md).

L'operatore di assegnazione di concatenazione (`&=`) è utile per l'aggiunta di una stringa alla fine dell'ultima contiene già le stringhe, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Conversioni di tipi in istruzioni di assegnazione

Il valore assegnato a una variabile, una proprietà o un elemento della matrice deve essere di un tipo di dati appropriato per tale elemento di destinazione. In generale, è consigliabile generare un valore dello stesso tipo di dati a quello dell'elemento di destinazione. Tuttavia, alcuni tipi possono essere convertiti in altri tipi di durante l'assegnazione.

Per informazioni sulla conversione tra tipi di dati, vedere [conversioni di tipi in Visual Basic](./data-types/type-conversions.md). In breve, Visual Basic converte automaticamente un valore di un determinato tipo in qualsiasi altro tipo a cui viene ampliato. Oggetto *conversione di ampliamento* è più grande sempre esito positivo in fase di esecuzione e non comporta la perdita di tutti i dati. Ad esempio, Visual Basic consente di convertire un' `Integer` valore per `Double` quando appropriato, in quanto `Integer` ampliarsi nel tipo `Double`. Per altre informazioni, vedere [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Conversione di Narrowing* (quelli che non sono di ampliamento) comportano rischi di errore in fase di esecuzione o di perdita dei dati. È possibile eseguire una conversione di narrowing in modo esplicito usando una funzione di conversione di tipi, oppure è possibile indicare al compilatore di eseguire tutte le conversioni in modo implicito tramite l'impostazione `Option Strict Off`. Per altre informazioni, vedere [conversioni implicite ed esplicite](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Inserimento di più istruzioni in una sola riga

È possibile avere più istruzioni in una singola riga, separata da due punti (`:`) caratteri. Questa condizione è illustrata nell'esempio seguente.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Anche se in alcuni casi è utile, questa forma di sintassi rende il codice difficile da leggere e gestire. Di conseguenza, è consigliabile mantenere un'unica istruzione in una riga.

## <a name="continuing-a-statement-over-multiple-lines"></a>Continuazione di un'istruzione su più righe

Un'istruzione che in genere si adatta a una sola riga, ma quando è troppo lungo, è possibile continuare alla riga successiva con una sequenza di continuazione di riga, che consiste in uno spazio seguito da un carattere di sottolineatura (`_`) seguito da un ritorno a capo. Nell'esempio seguente, il `MsgBox` istruzione eseguibile continua su due righe.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Continuazione di riga implicita

In molti casi, è possibile continuare un'istruzione nella riga successiva consecutiva senza usare il carattere di sottolineatura (`_`). I seguenti elementi della sintassi continuano in modo implicito l'istruzione nella riga successiva del codice.

- Dopo la virgola (`,`). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Dopo una parentesi aperta (`(`) o prima di una parentesi di chiusura (`)`). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Dopo una parentesi graffa aperta (`{`) o prima di una parentesi graffa di chiusura (`}`). Ad esempio:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Per altre informazioni, vedere [inizializzatori di oggetto: tipi denominati e anonimi](./objects-and-classes/object-initializers-named-and-anonymous-types.md) oppure [gli inizializzatori di insieme](./collection-initializers/index.md).

- Dopo aver aperto di un'espressione incorporata (`<%=`) o prima della chiusura di un'espressione incorporata (`%>`) all'interno di un valore letterale XML. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Per altre informazioni, vedere [espressioni incorporate in XML](./xml/embedded-expressions-in-xml.md).

- Dopo l'operatore di concatenazione (`&`). Ad esempio:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Per altre informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo gli operatori di assegnazione (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Per altre informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo gli operatori binari (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) all'interno di un'espressione. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Per altre informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo il `Is` e `IsNot` operatori. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Per altre informazioni, vedere [elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo un carattere qualificatore di membro (`.`) e prima del nome del membro. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Tuttavia, è necessario includere un carattere di continuazione di riga (`_`) dopo un carattere qualificatore membro quando si usa il `With` istruzione o specificando i valori nell'elenco di inizializzazione per un tipo. Si consideri l'interruzione di riga dopo l'operatore di assegnazione (ad esempio, `=`) quando si usa `With` istruzioni o elenchi di inizializzazione di oggetti. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Per altre informazioni, vedere [con... Terminare con l'istruzione](../../../visual-basic/language-reference/statements/with-end-with-statement.md) oppure [inizializzatori di oggetto: tipi denominati e anonimi](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Dopo un qualificatore di proprietà axis XML (`.` oppure `.@` o `...`). Tuttavia, è necessario includere un carattere di continuazione di riga (`_`) quando si specifica un qualificatore membro quando si usa il `With` (parola chiave). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Per altre informazioni, vedere [le proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md).

- Dopo un minore di-segno (<) o prima di maggiore-segno di maggiore (`>`) quando si specifica un attributo. Anche dopo un-segno di maggiore (`>`) quando si specifica un attributo. Tuttavia, è necessario includere un carattere di continuazione di riga (`_`) quando si specificano gli attributi a livello di assembly o a livello di modulo. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Per altre informazioni, vedere [Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- Prima e dopo gli operatori di query (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, e `Descending`). Non è possibile interrompere una linea tra le parole chiave degli operatori di query che sono costituiti da più parole chiave (`Order By`, `Group Join`, `Take While`, e `Skip While`). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Per altre informazioni, vedere [query](../../../visual-basic/language-reference/queries/index.md).

- Dopo il `In` parola chiave in un `For Each` istruzione. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Per altre informazioni, vedere [For Each... Istruzione Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- Dopo il `From` parola chiave in un inizializzatore di raccolta. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Per altre informazioni, vedere [Inizializzatori di insieme](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Aggiunta di commenti

Codice sorgente non è sempre chiara interpretazione, anche ai programmatori che lo ha scritto. Per aiutare a documentare il proprio codice, di conseguenza, la maggior parte dei programmatori usano il libero commenti incorporati. I commenti nel codice possono illustrare una procedura o una particolare istruzione a chiunque la lettura o l'uso dei dati in un secondo momento. Visual Basic ignora i commenti durante la compilazione e non influiscono sul codice compilato.

Le righe di commento iniziano con un apostrofo (`'`) o `REM` seguita da uno spazio. Possono essere aggiunti in qualsiasi punto nel codice, tranne all'interno di una stringa. Per aggiungere un commento a un'istruzione, inserire un apostrofo o `REM` dopo l'istruzione, seguito dal testo del commento. I commenti possono anche passare in una riga separata. L'esempio seguente illustra queste possibili.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Verifica degli errori di compilazione

Se, dopo aver digitato una riga di codice, viene visualizzata la riga con una sottolineatura ondulata blu (un messaggio di errore viene visualizzata anche), si verifica un errore di sintassi nell'istruzione. È necessario scoprire qual è il problema con l'istruzione (per la ricerca nell'elenco delle attività o al passaggio del mouse sull'errore con il puntatore del mouse e la lettura del messaggio di errore) e correggere l'errore. Fino a quando non è stato risolto tutti gli errori di sintassi nel codice, il programma avrà esito negativo per una compilazione corretta.

## <a name="related-sections"></a>Sezioni correlate

|Termine|Definizione|
|---|---|
|[Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)|Vengono forniti collegamenti alle pagine di riferimento del linguaggio che copre, ad esempio gli operatori di assegnazione `=`, `*=`, e `&=`.|
|[Operatori ed espressioni](./operators-and-expressions/index.md)|Viene illustrato come combinare elementi e gli operatori per produrre nuovi valori.|
|[Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Viene illustrato come suddividere una singola istruzione in più righe e come eseguire più istruzioni sulla stessa riga.|
|[Procedura: Etichettare le istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Viene illustrato come assegnare un'etichetta di una riga di codice.|
