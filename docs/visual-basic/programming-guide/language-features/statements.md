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
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400890"
---
# <a name="statements-in-visual-basic"></a>Istruzioni in Visual Basic

Un'istruzione in Visual Basic è un'istruzione completa. Può contenere parole chiave, operatori, variabili, costanti ed espressioni. Ogni istruzione appartiene a una delle seguenti categorie:

- **Dichiarazione Istruzioni**, che denominano una variabile, una costante o una routine e possono anche specificare un tipo di dati.

- **Istruzioni eseguibili**, che avviano azioni. Queste istruzioni possono chiamare un metodo o una funzione e possono eseguire cicli o diramazioni tra blocchi di codice. Le istruzioni **eseguibili**includono istruzioni di assegnazione , che assegnano un valore o un'espressione a una variabile o costante.

In questo argomento viene descritta ogni categoria. Inoltre, in questo argomento viene descritto come combinare più istruzioni in una singola riga e come continuare un'istruzione su più righe.

## <a name="declaration-statements"></a>Istruzioni di dichiarazione

Le istruzioni di dichiarazione consentono di denominare e definire routine, variabili, proprietà, matrici e costanti. Quando si dichiara un elemento di programmazione, è anche possibile definirne il tipo di dati, il livello di accesso e l'ambito. Per ulteriori informazioni, vedere [Caratteristiche degli elementi dichiarati](./declared-elements/declared-element-characteristics.md).

L'esempio seguente contiene tre dichiarazioni.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

La prima dichiarazione è la `Sub` dichiarazione. Insieme alla `End Sub` relativa istruzione corrispondente, dichiara `applyFormat`una routine denominata . Specifica inoltre che `applyFormat` `Public`è , il che significa che qualsiasi codice che può farvi riferimento può chiamarlo.

La seconda dichiarazione è `Const` l'istruzione `limit`, che `Integer` dichiara la costante , specificando il tipo di dati e un valore pari a 33.

La terza dichiarazione è `Dim` l'istruzione `thisWidget`, che dichiara la variabile . Il tipo di dati è un oggetto specifico, ovvero un oggetto creato dalla `Widget` classe. È possibile dichiarare una variabile di qualsiasi tipo di dati elementare o di qualsiasi tipo di oggetto esposto nell'applicazione in uso.

### <a name="initial-values"></a>Valori iniziali

Quando viene eseguito il codice contenente un'istruzione di dichiarazione, Visual Basic riserva la memoria necessaria per l'elemento dichiarato. Se l'elemento contiene un valore, Visual Basic lo inizializza sul valore predefinito per il relativo tipo di dati. Per ulteriori informazioni, vedere "Comportamento" [nell'istruzione Dim](../../language-reference/statements/dim-statement.md).

È possibile assegnare un valore iniziale a una variabile come parte della relativa dichiarazione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Se una variabile è una variabile oggetto, è possibile creare in modo esplicito un'istanza della relativa classe quando la si dichiara utilizzando la parola [chiave New Operator,](../../../visual-basic/language-reference/operators/new-operator.md) come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Si noti che il valore iniziale specificato in un'istruzione di dichiarazione non viene assegnato a una variabile fino a quando l'esecuzione non raggiunge l'istruzione di dichiarazione. Fino a quel momento, la variabile contiene il valore predefinito per il relativo tipo di dati.

## <a name="executable-statements"></a>Istruzioni eseguibili

Un'istruzione eseguibile esegue un'azione. Può chiamare una routine, creare un ramo in un'altra posizione nel codice, scorrere in ciclo diverse istruzioni o valutare un'espressione. Un'istruzione di assegnazione è un caso speciale di un'istruzione eseguibile.

Nell'esempio seguente `If...Then...Else` viene utilizzata una struttura di controllo per eseguire diversi blocchi di codice in base al valore di una variabile. All'interno di ogni `For...Next` blocco di codice, un ciclo viene eseguito un numero specificato di volte.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

L'istruzione `If` nell'esempio precedente controlla il `clockwise`valore del parametro . Se il `True`valore è `spinClockwise` , `aWidget`chiama il metodo di . Se il `False`valore è `spinCounterClockwise` , `aWidget`chiama il metodo di . La `If...Then...Else` struttura del `End If`controllo termina con .

Il `For...Next` ciclo all'interno di ogni blocco chiama il metodo `revolutions` appropriato un numero di volte uguale al valore del parametro.

## <a name="assignment-statements"></a>Rendiconti di assegnazione

Le istruzioni di assegnazione eseguono operazioni di assegnazione, che consistono nell'assunzione del valore sul lato destro dell'operatore di assegnazione (`=`) e nell'archiviarlo nell'elemento a sinistra, come nell'esempio seguente.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

Nell'esempio precedente, l'istruzione di assegnazione archivia `v`il valore letterale 42 nella variabile .

### <a name="eligible-programming-elements"></a>Elementi di programmazione idonei

L'elemento di programmazione sul lato sinistro dell'operatore di assegnazione deve essere in grado di accettare e archiviare un valore. Ciò significa che deve essere una variabile o una proprietà che non è [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)o deve essere un elemento di matrice. Nel contesto di un'istruzione di assegnazione, tale elemento viene talvolta chiamato *lvalue*, per "valore sinistro".

Il valore sul lato destro dell'operatore di assegnazione è generato da un'espressione, che può essere costituita da qualsiasi combinazione di valori letterali, costanti, variabili, proprietà, elementi di matrice, altre espressioni o chiamate di funzione. Questa condizione è illustrata nell'esempio seguente.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

Nell'esempio precedente il valore `y` mantenuto in variable `z`viene aggiunto al valore contenuto nella `findResult`variabile , quindi il valore restituito dalla chiamata alla funzione . Il valore totale di questa espressione `x`viene quindi archiviato nella variabile .

### <a name="data-types-in-assignment-statements"></a>Tipi di dati nelle istruzioni di assegnazioneData types in assignment statements

Oltre ai valori numerici, l'operatore di assegnazione può anche assegnare `String` valori, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

È anche `Boolean` possibile assegnare `Boolean` valori, `Boolean` usando un valore letterale o un'espressione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Analogamente, è possibile assegnare valori `Char` `Date`appropriati `Object` agli elementi di programmazione del tipo di dati , , o . È inoltre possibile assegnare un'istanza dell'oggetto a un elemento dichiarato della classe da cui viene creata l'istanza.

### <a name="compound-assignment-statements"></a>Istruzioni di assegnazione composteCompound assignment statements

Le istruzioni di *assegnazione composta eseguono* prima un'operazione su un'espressione prima di assegnarla a un elemento di programmazione.Compound assignment statements first perform an operation on an expression before assigning it to a programming element. Nell'esempio seguente viene illustrato `+=`uno di questi operatori, , che incrementa il valore della variabile sul lato sinistro dell'operatore in base al valore dell'espressione a destra.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

Nell'esempio precedente viene aggiunto `n`1 al valore di `n`, quindi il nuovo valore viene memorizzato in . È un equivalente abbreviato della seguente affermazione:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Un'ampia gamma di operazioni di assegnazione composta può essere eseguita utilizzando operatori di questo tipo. Per un elenco di questi operatori e ulteriori informazioni su di essi, vedere [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md).

L'operatore di`&=`assegnazione di concatenazione ( ) è utile per aggiungere una stringa alla fine di stringhe già esistenti, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Conversioni di tipi nelle istruzioni di assegnazioneType Conversions in Assignment Statements

Il valore assegnato a una variabile, una proprietà o un elemento di matrice deve essere di un tipo di dati appropriato per tale elemento di destinazione. In generale, è consigliabile provare a generare un valore dello stesso tipo di dati dell'elemento di destinazione. Tuttavia, alcuni tipi possono essere convertiti in altri tipi durante l'assegnazione.

Per informazioni sulla conversione tra tipi di dati, vedere [Conversioni dei](./data-types/type-conversions.md)tipi in Visual Basic . In breve, Visual Basic converte automaticamente un valore di un determinato tipo in qualsiasi altro tipo a cui si allarga. Una *conversione di ampliamento* è uno in quanto riesce sempre in fase di esecuzione e non perde alcun dato. Ad esempio, Visual Basic `Integer` converte un valore `Double` in quando appropriato, poiché `Integer` amplia in `Double`. Per altre informazioni, vedere [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*La riduzione delle conversioni* (quelle che non si stanno ampliando) comporta un rischio di errore in fase di esecuzione o di perdita di dati. È possibile eseguire una conversione verso un tipo di dati più piccolo in modo esplicito utilizzando una funzione di conversione dei tipi oppure è possibile indicare al compilatore di eseguire tutte le conversioni in modo implicito impostando `Option Strict Off`. Per ulteriori informazioni, vedere [Conversioni implicite ed esplicite](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Inserimento di più istruzioni in un'unica riga

È possibile avere più istruzioni su una singola`:`riga separate dal carattere due punti ( ). Questa condizione è illustrata nell'esempio seguente.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Anche se occasionalmente conveniente, questa forma di sintassi rende il codice difficile da leggere e gestire. Pertanto, si consiglia di mantenere un'istruzione a una riga.

## <a name="continuing-a-statement-over-multiple-lines"></a>Continuazione di un'istruzione su più righe

Un'istruzione di solito si adatta a una riga, ma quando è troppo lunga, è possibile continuarla nella riga successiva`_`utilizzando una sequenza di continuazione di riga, costituita da uno spazio seguito da un carattere di sottolineatura ( ) seguito da un ritorno a capo. Nell'esempio seguente `MsgBox` l'istruzione eseguibile continua su due righe.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Continuazione di riga implicita

In molti casi, è possibile continuare un'istruzione nella riga`_`successiva consecutiva senza utilizzare il carattere di sottolineatura ( ). Gli elementi di sintassi seguenti continuano in modo implicito l'istruzione nella riga di codice successiva.

- Dopo una`,`virgola ( ). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Dopo una parentesi`(`aperta ( ) o`)`prima di una parentesi di chiusura ( ). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Dopo una parentesi graffa aperta (`{`) o`}`prima di una parentesi graffa di chiusura ( ). Ad esempio:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Per ulteriori informazioni, vedere [Inizializzatori di oggetto: tipi denominati e anonimi](./objects-and-classes/object-initializers-named-and-anonymous-types.md) o [Inizializzatori di raccolta](./collection-initializers/index.md).

- Dopo un'espressione`<%=`incorporata aperta ( ) o`%>`prima della chiusura di un'espressione incorporata ( ) all'interno di un valore letterale XML. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Per ulteriori informazioni, vedere [Espressioni incorporate in XML](./xml/embedded-expressions-in-xml.md).

- Dopo l'operatore`&`di concatenazione ( ). Ad esempio:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Per ulteriori informazioni, vedere [Operatori elencati per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo gli`=`operatori `&=` `:=`di `+=` `-=`assegnazione ( , , , , `*=`, `/=`, `\=`, `^=` `<<=`, ). `>>=` Ad esempio:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Per ulteriori informazioni, vedere [Operatori elencati per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo gli`+`operatori `-` `/`binari `*` `Mod`( `<>` `<`, `>` `<=`, `>=` `^`, `>>` `<<`, `And` `AndAlso`, `Or` `OrElse`, `Like` `Xor`, , , , , , , , , ) all'interno di un'espressione. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Per ulteriori informazioni, vedere [Operatori elencati per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo `Is` gli `IsNot` operatori e. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Per ulteriori informazioni, vedere [Operatori elencati per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Dopo un carattere`.`qualificatore membro ( ) e prima del nome del membro. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Tuttavia, è necessario includere un`_`carattere di continuazione di `With` riga ( ) dopo un carattere di qualificatore del membro quando si utilizza l'istruzione o si forniscono valori nell'elenco di inizializzazione per un tipo. È consigliabile interrompere la riga dopo `=`l'operatore `With` di assegnazione (ad esempio, ) quando si utilizzano istruzioni o elenchi di inizializzazione di oggetti. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Per ulteriori informazioni, vedere [Con... Istruzione End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md) o [Inizializzatori di oggetto: tipi denominati e anonimi](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Dopo un qualificatore`.` di `.@` `...`proprietà axis XML ( o o ). Tuttavia, è necessario includere un`_`carattere di continuazione di riga `With` ( ) quando si specifica un qualificatore di membro quando si utilizza la parola chiave . Ad esempio:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Per ulteriori informazioni, vedere [Proprietà degli asse XML](../../../visual-basic/language-reference/xml-axis/index.md).

- Dopo un segno di minore di (<) o`>`prima di un segno di maggiore ( ) quando si specifica un attributo. Anche dopo un segno`>`di maggiore di ( ) quando si specifica un attributo. Tuttavia, è necessario includere un`_`carattere di continuazione di riga ( ) quando si specificano gli attributi a livello di assembly o di modulo. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Per ulteriori informazioni, vedere [Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- Prima e dopo`Aggregate`gli `Distinct` `From`operatori `Group By` `Group Join`di `Join` `Let`query `Order By` `Select`( `Skip` `Skip While`, `Take`, , , , , , , `Take While` `Where` `In`, , `Into`, , `On`, `Ascending`, , , , e `Descending`. Non è possibile interrompere una riga tra le parole chiave`Order By` `Group Join`degli `Take While`operatori `Skip While`di query costituite da più parole chiave ( , , e ). Ad esempio:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Per ulteriori informazioni, vedere [Query](../../../visual-basic/language-reference/queries/index.md).

- Dopo `In` la parola `For Each` chiave in un'istruzione. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Per ulteriori informazioni, vedere [For Each... Istruzione Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- Dopo `From` la parola chiave in un inizializzatore di raccolta. Ad esempio:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Per altre informazioni, vedere [Inizializzatori di insieme](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Aggiunta di commenti

Il codice sorgente non è sempre autoesplicativo, anche per il programmatore che lo ha scritto. Per aiutare a documentare il loro codice, quindi, la maggior parte dei programmatori fanno uso liberale di commenti incorporati. I commenti nel codice possono spiegare una routine o una particolare istruzione a chiunque la legga o la utilizzi in un secondo momento. Visual Basic ignora i commenti durante la compilazione e non influisce sul codice compilato.

Le righe di commento iniziano`'`con `REM` un apostrofo ( ) o seguite da uno spazio. Possono essere aggiunti in qualsiasi punto del codice, ad eccezione di una stringa. Per aggiungere un commento a un'istruzione, `REM` inserire un apostrofo o dopo l'istruzione, seguito dal commento. I commenti possono anche andare sulla propria riga separata. Nell'esempio seguente vengono illustrate queste possibilità.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Controllo degli errori di compilazione

Se, dopo aver digitato una riga di codice, la riga viene visualizzata con una sottolineatura blu ondulata (potrebbe essere visualizzato anche un messaggio di errore), si verifica un errore di sintassi nell'istruzione. È necessario scoprire che cosa è sbagliato con l'istruzione (cercando nell'elenco delle attività, o passando il mouse sopra l'errore con il puntatore del mouse e la lettura del messaggio di errore) e correggerlo. Fino a quando non sono stati corretti tutti gli errori di sintassi nel codice, il programma non verrà compilato correttamente.

## <a name="related-sections"></a>Sezioni correlate

|Termine|Definizione|
|---|---|
|[Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)|Vengono forniti collegamenti a pagine di `=` `*=`riferimento `&=`del linguaggio relative agli operatori di assegnazione, ad esempio , e .|
|[Operatori ed espressioni](./operators-and-expressions/index.md)|Viene illustrato come combinare gli elementi con gli operatori per produrre nuovi valori.|
|[Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Viene illustrato come suddividere una singola istruzione in più righe e come inserire più istruzioni nella stessa riga.|
|[Procedura: Etichettare le istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Viene illustrato come etichettare una riga di codice.|
