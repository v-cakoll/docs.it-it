---
title: Istruzioni
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
ms.openlocfilehash: 09fe53f4bc2b6d025b762c6595c5337263456bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401979"
---
# <a name="statements-in-visual-basic"></a>Istruzioni in Visual Basic

Un'istruzione in Visual Basic è un'istruzione completa. Può contenere parole chiave, operatori, variabili, costanti ed espressioni. Ogni istruzione appartiene a una delle categorie seguenti:

- Le **istruzioni di dichiarazione**, che denominano una variabile, una costante o una routine, possono anche specificare un tipo di dati.

- **Istruzioni eseguibili**, che avviano le azioni. Queste istruzioni possono chiamare un metodo o una funzione e possono eseguire il ciclo o il branching tramite blocchi di codice. Le istruzioni eseguibili includono **istruzioni di assegnazione**che assegnano un valore o un'espressione a una variabile o a una costante.

In questo argomento viene descritta ogni categoria. Inoltre, in questo argomento viene descritto come combinare più istruzioni su una sola riga e come continuare un'istruzione su più righe.

## <a name="declaration-statements"></a>Istruzioni di dichiarazione

Usare le istruzioni di dichiarazione per assegnare un nome e una definizione a procedure, variabili, proprietà, matrici e costanti. Quando si dichiara un elemento di programmazione, è anche possibile definire il tipo di dati, il livello di accesso e l'ambito. Per altre informazioni, vedere [caratteristiche degli elementi dichiarati](./declared-elements/declared-element-characteristics.md).

Nell'esempio seguente sono contenute tre dichiarazioni.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

La prima dichiarazione è l' `Sub` istruzione. Insieme alla relativa `End Sub` istruzione corrispondente, viene dichiarata una stored procedure denominata `applyFormat` . Specifica anche che `applyFormat` è `Public` , il che significa che qualsiasi codice che può farvi riferimento può chiamarlo.

La seconda dichiarazione è l' `Const` istruzione, che dichiara la costante `limit` , specificando il `Integer` tipo di dati e un valore di 33.

La terza dichiarazione è l' `Dim` istruzione, che dichiara la variabile `thisWidget` . Il tipo di dati è un oggetto specifico, ovvero un oggetto creato dalla `Widget` classe. È possibile dichiarare una variabile come qualsiasi tipo di dati elementare o qualsiasi tipo di oggetto esposto nell'applicazione in uso.

### <a name="initial-values"></a>Valori iniziali

Quando viene eseguito il codice contenente un'istruzione di dichiarazione, Visual Basic riserva la memoria necessaria per l'elemento dichiarato. Se l'elemento include un valore, Visual Basic lo inizializza sul valore predefinito per il tipo di dati. Per ulteriori informazioni, vedere "comportamento" nell' [istruzione Dim](../../language-reference/statements/dim-statement.md).

È possibile assegnare un valore iniziale a una variabile come parte della relativa dichiarazione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Se una variabile è una variabile oggetto, è possibile creare in modo esplicito un'istanza della relativa classe quando viene dichiarata tramite la parola chiave [new operator](../../language-reference/operators/new-operator.md) , come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Si noti che il valore iniziale specificato in un'istruzione di dichiarazione non viene assegnato a una variabile finché l'esecuzione non raggiunge la relativa istruzione di dichiarazione. Fino a quel momento, la variabile contiene il valore predefinito per il tipo di dati.

## <a name="executable-statements"></a>Istruzioni eseguibili

Un'istruzione eseguibile esegue un'azione. Può chiamare una routine, creare un ramo in un'altra posizione nel codice, eseguire il ciclo di diverse istruzioni o valutare un'espressione. Un'istruzione di assegnazione è un caso speciale di un'istruzione eseguibile.

Nell'esempio seguente viene utilizzata una `If...Then...Else` struttura di controllo per eseguire blocchi di codice diversi in base al valore di una variabile. All'interno di ogni blocco di codice, un `For...Next` ciclo viene eseguito un numero specificato di volte.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

L' `If` istruzione nell'esempio precedente verifica il valore del parametro `clockwise` . Se il valore è `True` , viene chiamato il `spinClockwise` metodo di `aWidget` . Se il valore è `False` , viene chiamato il `spinCounterClockwise` metodo di `aWidget` . La `If...Then...Else` struttura del controllo termina con `End If` .

Il `For...Next` ciclo all'interno di ogni blocco chiama il metodo appropriato un numero di volte uguale al valore del `revolutions` parametro.

## <a name="assignment-statements"></a>Istruzioni di assegnazione

Le istruzioni di assegnazione eseguono operazioni di assegnazione, che sono costituite dall'acquisizione del valore sul lato destro dell'operatore di assegnazione ( `=` ) e dall'archiviazione nell'elemento a sinistra, come nell'esempio seguente.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

Nell'esempio precedente, l'istruzione di assegnazione archivia il valore letterale 42 nella variabile `v` .

### <a name="eligible-programming-elements"></a>Elementi di programmazione idonei

L'elemento di programmazione sul lato sinistro dell'operatore di assegnazione deve essere in grado di accettare e archiviare un valore. Questo significa che deve essere una variabile o una proprietà che non è [ReadOnly](../../language-reference/modifiers/readonly.md)o deve essere un elemento di matrice. Nel contesto di un'istruzione di assegnazione, tale elemento viene talvolta denominato *lvalue*, per "valore a sinistra".

Il valore a destra dell'operatore di assegnazione viene generato da un'espressione, che può essere costituita da qualsiasi combinazione di valori letterali, costanti, variabili, proprietà, elementi di matrice, altre espressioni o chiamate di funzione. Questa condizione è illustrata nell'esempio seguente.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

Nell'esempio precedente il valore contenuto nella variabile viene aggiunto `y` al valore contenuto nella variabile `z` , quindi viene aggiunto il valore restituito dalla chiamata al funzione `findResult` . Il valore totale di questa espressione viene quindi archiviato nella variabile `x` .

### <a name="data-types-in-assignment-statements"></a>Tipi di dati nelle istruzioni di assegnazione

Oltre ai valori numerici, l'operatore di assegnazione può anche assegnare `String` valori, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

È anche possibile assegnare `Boolean` valori, usando un `Boolean` valore letterale o un' `Boolean` espressione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Analogamente, è possibile assegnare valori appropriati agli elementi di programmazione `Char` del `Date` tipo di `Object` dati, o. È inoltre possibile assegnare un'istanza di oggetto a un elemento dichiarato come della classe da cui viene creata l'istanza.

### <a name="compound-assignment-statements"></a>Istruzioni di assegnazione composta

Le *istruzioni di assegnazione composta* eseguono innanzitutto un'operazione su un'espressione prima di assegnarla a un elemento di programmazione. Nell'esempio seguente viene illustrato uno di questi operatori, `+=` , che incrementa il valore della variabile sul lato sinistro dell'operatore in base al valore dell'espressione a destra.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Nell'esempio precedente viene aggiunto 1 al valore di `n` , quindi il nuovo valore viene archiviato in `n` . Si tratta di un equivalente a sintassi abbreviata dell'istruzione seguente:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

È possibile eseguire un'ampia gamma di operazioni di assegnazione composta utilizzando operatori di questo tipo. Per un elenco di questi operatori e altre informazioni su di essi, vedere [operatori di assegnazione](../../language-reference/operators/assignment-operators.md).

L'operatore di assegnazione di concatenazione ( `&=` ) è utile per aggiungere una stringa alla fine di stringhe già esistenti, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Conversioni di tipi nelle istruzioni di assegnazione

Il valore assegnato a una variabile, una proprietà o un elemento di matrice deve essere di un tipo di dati appropriato a tale elemento di destinazione. In generale, è consigliabile provare a generare un valore dello stesso tipo di dati dell'elemento di destinazione. Tuttavia, alcuni tipi possono essere convertiti in altri tipi durante l'assegnazione.

Per informazioni sulla conversione tra tipi di dati, vedere [conversioni di tipi in Visual Basic](./data-types/type-conversions.md). In breve, Visual Basic converte automaticamente un valore di un determinato tipo in un altro tipo a cui viene ampliato. Una *conversione* verso un tipo di dati più ampio è una conversione in che ha sempre esito positivo in fase di esecuzione e non perde i dati. Ad esempio, Visual Basic converte un `Integer` valore in `Double` quando appropriato, perché viene `Integer` ampliato a `Double` . Per altre informazioni, vedere [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

Le *conversioni* verso un tipo di dati più piccolo, ovvero quelle che non si ampliano, presentano un rischio di errore in fase di esecuzione o di perdita di dati. È possibile eseguire una conversione verso un tipo di conversione più piccolo in modo esplicito tramite una funzione di conversione dei tipi oppure è possibile indirizzare il compilatore in modo implicito per eseguire tutte le conversioni `Option Strict Off` . Per ulteriori informazioni, vedere [conversioni implicite ed esplicite](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Inserimento di più istruzioni su una sola riga

È possibile avere più istruzioni su una sola riga separate dal carattere due punti ( `:` ). Questa condizione è illustrata nell'esempio seguente.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Sebbene occasionalmente pratico, questo tipo di sintassi rende il codice difficile da leggere e gestire. È quindi consigliabile usare una sola istruzione per una riga.

## <a name="continuing-a-statement-over-multiple-lines"></a>Continuazione di un'istruzione su più righe

Un'istruzione si trova in genere in una sola riga, ma quando è troppo lunga, è possibile continuare nella riga successiva utilizzando una sequenza di continuazione di riga, costituita da uno spazio seguito da un carattere di sottolineatura ( `_` ) seguito da un ritorno a capo. Nell'esempio seguente l' `MsgBox` istruzione Executable viene continuata su due righe.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Continuazione di riga implicita

In molti casi, è possibile continuare un'istruzione sulla riga consecutiva successiva senza usare il carattere di sottolineatura ( `_` ). Gli elementi di sintassi seguenti continuano in modo implicito l'istruzione alla riga di codice successiva.

- Dopo una virgola ( `,` ). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Dopo una parentesi aperta ( `(` ) o prima di una parentesi di chiusura ( `)` ). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Dopo una parentesi graffa aperta ( `{` ) o prima di una parentesi graffa chiusa ( `}` ). Ad esempio:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Per altre informazioni, vedere [inizializzatori di oggetto: tipi denominati e anonimi](./objects-and-classes/object-initializers-named-and-anonymous-types.md) o [inizializzatori di insieme](./collection-initializers/index.md).

- Dopo un'espressione incorporata aperta ( `<%=` ) o prima della chiusura di un'espressione incorporata ( `%>` ) all'interno di un valore letterale XML. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Per ulteriori informazioni, vedere [espressioni incorporate in XML](./xml/embedded-expressions-in-xml.md).

- Dopo l'operatore di concatenazione ( `&` ). Ad esempio:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Per ulteriori informazioni, vedere [operatori elencati per funzionalità](../../language-reference/operators/operators-listed-by-functionality.md).

- Dopo gli operatori di assegnazione ( `=` , `&=` , `:=` , `+=` , `-=` , `*=` , `/=` , `\=` , `^=` , `<<=` , `>>=` ). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Per ulteriori informazioni, vedere [operatori elencati per funzionalità](../../language-reference/operators/operators-listed-by-functionality.md).

- Dopo gli operatori binari ( `+` ,, `-` `/` , `*` , `Mod` , `<>` , `<` , `>` , `<=` , `>=` , `^` , `>>` , `<<` , `And` , `AndAlso` , `Or` , `OrElse` , `Like` , `Xor` ) in un'espressione. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Per ulteriori informazioni, vedere [operatori elencati per funzionalità](../../language-reference/operators/operators-listed-by-functionality.md).

- Dopo gli `Is` `IsNot` operatori e. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Per ulteriori informazioni, vedere [operatori elencati per funzionalità](../../language-reference/operators/operators-listed-by-functionality.md).

- Dopo un carattere qualificatore del membro ( `.` ) e prima del nome del membro. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Tuttavia, è necessario includere un carattere di continuazione di riga ( `_` ) dopo un carattere qualificatore membro quando si utilizza l' `With` istruzione o specificare valori nell'elenco di inizializzazione per un tipo. Provare a suddividere la riga dopo l'operatore di assegnazione (ad esempio, `=` ) quando si utilizzano `With` istruzioni o elenchi di inizializzazione di oggetti. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Per ulteriori informazioni, vedere [con... Termina con l'istruzione](../../language-reference/statements/with-end-with-statement.md) o gli [inizializzatori di oggetto: tipi denominati e anonimi](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Dopo un qualificatore di proprietà Axis XML ( `.` o `.@` `...` ). Tuttavia, quando si `_` specifica un qualificatore del membro quando si usa la parola chiave, è necessario includere un carattere di continuazione di riga () `With` . Ad esempio:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Per ulteriori informazioni, vedere [Proprietà Axis XML](../../language-reference/xml-axis/index.md).

- Dopo un segno di minore (<) o prima di un segno di maggiore di ( `>` ) quando si specifica un attributo. Anche dopo un segno di maggiore di ( `>` ) quando si specifica un attributo. Tuttavia, `_` quando si specificano gli attributi a livello di assembly o di modulo, è necessario includere un carattere di continuazione di riga (). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Per altre informazioni, vedere [Cenni preliminari sugli attributi](../concepts/attributes/index.md).

- Operatori di query before e After ( `Aggregate` ,, `Distinct` `From` , `Group By` , `Group Join` , `Join` , `Let` , `Order By` , `Select` , `Skip` , `Skip While` , `Take` , `Take While` , `Where` , `In` , `Into` , `On` , `Ascending` e `Descending` ). Non è possibile suddividere una linea tra le parole chiave degli operatori di query che sono costituite da più parole chiave ( `Order By` ,, `Group Join` `Take While` e `Skip While` ). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Per ulteriori informazioni, vedere [query](../../language-reference/queries/index.md).

- Dopo la `In` parola chiave in un' `For Each` istruzione. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Per ulteriori informazioni, vedere [for each... Istruzione successiva](../../language-reference/statements/for-each-next-statement.md).

- Dopo la `From` parola chiave in un inizializzatore di raccolta. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Per altre informazioni, vedere [Inizializzatori di insieme](collection-initializers/index.md).

## <a name="adding-comments"></a>Aggiunta di commenti

Il codice sorgente non è sempre di chiara comprensione, neanche al programmatore che lo ha scritto. Per documentare il codice, la maggior parte dei programmatori fa uso di commenti incorporati. I commenti nel codice possono spiegare una procedura o una particolare istruzione a chiunque legga o funzioni in un secondo momento. Visual Basic ignora i commenti durante la compilazione e non influiscono sul codice compilato.

Le righe di commento iniziano con un apostrofo ( `'` ) o `REM` seguito da uno spazio. Possono essere aggiunti ovunque nel codice, tranne che all'interno di una stringa. Per aggiungere un commento a un'istruzione, inserire un apostrofo o `REM` dopo l'istruzione, seguito dal commento. I commenti possono anche essere inseriti in una riga separata. Nell'esempio seguente vengono illustrate queste possibilità.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Verifica degli errori di compilazione

Se, dopo aver digitato una riga di codice, la riga viene visualizzata con una sottolineatura blu ondulata (potrebbe essere visualizzato anche un messaggio di errore), nell'istruzione si verifica un errore di sintassi. È necessario individuare il problema con l'istruzione (esaminando l'elenco attività oppure passando il puntatore del mouse sull'errore con il puntatore del mouse e leggendo il messaggio di errore) e correggerlo. Fino a quando non sono stati corretti tutti gli errori di sintassi nel codice, il programma non verrà compilato correttamente.

## <a name="related-sections"></a>Sezioni correlate

|Termine|Definizione|
|---|---|
|[Operatori di assegnazione](../../language-reference/operators/assignment-operators.md)|Fornisce collegamenti a pagine di riferimento per il linguaggio che coprono gli operatori di assegnazione, ad esempio `=` , `*=` e `&=` .|
|[Operatori ed espressioni](./operators-and-expressions/index.md)|Viene illustrato come combinare elementi con operatori per restituire nuovi valori.|
|[Procedura: Interrompere e combinare istruzioni nel codice](../program-structure/how-to-break-and-combine-statements-in-code.md)|Viene illustrato come suddividere una singola istruzione in più righe e come inserire più istruzioni nella stessa riga.|
|[Procedura: Etichettare le istruzioni](../program-structure/how-to-label-statements.md)|Viene illustrato come etichettare una riga di codice.|
