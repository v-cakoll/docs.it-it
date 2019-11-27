---
title: Inferenza del tipo di variabile locale
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: f79ac70aecb5805a3a4a4fea8f7e7ccd3f8243fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351841"
---
# <a name="local-type-inference-visual-basic"></a>Inferenza del tipo di variabile locale (Visual Basic)

Il compilatore Visual Basic usa l' *inferenza del tipo* per determinare i tipi di dati delle variabili locali dichiarate senza una clausola `As`. Il compilatore deduce il tipo della variabile dal tipo dell'espressione di inizializzazione. Ciò consente di dichiarare le variabili senza dichiarare esplicitamente un tipo, come illustrato nell'esempio seguente. In seguito alle dichiarazioni, sia `num1` che `num2` sono fortemente tipizzati come numeri interi.

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> Se non si desidera che `num2` nell'esempio precedente siano tipizzate come `Integer`, è possibile specificare un altro tipo utilizzando una dichiarazione come `Dim num3 As Object = 3` o `Dim num4 As Double = 3`.

> [!NOTE]
> L'inferenza del tipo può essere utilizzata solo per le variabili locali non statiche. non può essere utilizzato per determinare il tipo di campi, proprietà o funzioni di classe.

L'inferenza del tipo locale viene applicata a livello di procedura. Non può essere usato per dichiarare variabili a livello di modulo (all'interno di una classe, una struttura, un modulo o un'interfaccia, ma non all'interno di una routine o di un blocco). Se `num2` nell'esempio precedente era un campo di una classe anziché una variabile locale in una routine, la dichiarazione provocherebbe un errore con `Option Strict` in e classifica `num2` come `Object` con `Option Strict` disattivato. Analogamente, l'inferenza del tipo locale non si applica alle variabili a livello di routine dichiarate come `Static`.

## <a name="type-inference-vs-late-binding"></a>Inferenza del tipo e associazione tardiva

Il codice che usa l'inferenza del tipo è simile al codice basato sull'associazione tardiva. Tuttavia, l'inferenza del tipo digita fortemente la variabile anziché lasciarla come `Object`. Il compilatore usa l'inizializzatore di una variabile per determinare il tipo della variabile in fase di compilazione per produrre codice ad associazione anticipata. Nell'esempio precedente `num2`, come `num1`, è tipizzato come `Integer`.

Il comportamento delle variabili con associazione anticipata è diverso da quello delle variabili ad associazione tardiva, per le quali il tipo è noto solo in fase di esecuzione. Conoscendo il tipo in anticipo, il compilatore è in grado di identificare i problemi prima dell'esecuzione, allocare la memoria con precisione ed eseguire altre ottimizzazioni. L'associazione anticipata consente inoltre al Integrated Development Environment di Visual Basic (IDE) di fornire la guida IntelliSense sui membri di un oggetto. Per le prestazioni è preferibile anche l'associazione anticipata. Questo perché tutti i dati archiviati in una variabile ad associazione tardiva devono essere racchiusi come tipo `Object`e l'accesso ai membri del tipo in fase di esecuzione rende il programma più lento.

## <a name="examples"></a>Esempi

L'inferenza del tipo si verifica quando una variabile locale viene dichiarata senza una clausola `As` e inizializzata. Il compilatore usa il tipo del valore iniziale assegnato come tipo della variabile. Ognuna delle righe di codice seguenti, ad esempio, dichiara una variabile di tipo `String`.

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

Nel codice seguente vengono illustrati due modi equivalenti per creare una matrice di numeri interi.

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

È consigliabile usare l'inferenza del tipo per determinare il tipo di una variabile di controllo del ciclo. Nel codice seguente, il compilatore deduce che `number` è un `Integer` perché `someNumbers2` dell'esempio precedente è una matrice di numeri interi.

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

L'inferenza del tipo locale può essere usata nelle istruzioni `Using` per stabilire il tipo di nome della risorsa, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

Il tipo di una variabile può anche essere dedotto dai valori restituiti delle funzioni, come illustrato nell'esempio seguente. Sia `pList1` che `pList2` sono matrici di processi perché `Process.GetProcesses` restituisce una matrice di processi.

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a>Deduce dall'opzione

`Option Infer` consente di specificare se l'inferenza del tipo locale è consentita in un file specifico. Per abilitare o per bloccare l'opzione, digitare una delle seguenti istruzioni all'inizio del file.

`Option Infer On`

`Option Infer Off`

Se non si specifica un valore per `Option Infer` nel codice, viene `Option Infer On`l'impostazione predefinita del compilatore.

Se il valore impostato per `Option Infer` in un file è in conflitto con il valore impostato nell'IDE o sulla riga di comando, il valore nel file ha precedenza.

Per ulteriori informazioni, vedere l' [istruzione Option dedurre](../../../../visual-basic/language-reference/statements/option-infer-statement.md) e la [pagina di compilazione, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

## <a name="see-also"></a>Vedere anche

- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [Istruzione For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Istruzione For...Next](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [-optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
