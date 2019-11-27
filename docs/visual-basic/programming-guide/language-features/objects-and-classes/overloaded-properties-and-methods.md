---
title: Metodi e proprietà di overload
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: a5017d371f8a01436020443b2e3466c78fc35d21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346095"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Metodi e proprietà di overload (Visual Basic)

L'overload è la creazione di più di una routine, di un costruttore di istanza o di una proprietà in una classe con lo stesso nome ma con tipi di argomenti diversi.

## <a name="overloading-usage"></a>Overload dell'utilizzo

L'overload è particolarmente utile quando il modello a oggetti impone l'utilizzo di nomi identici per le procedure che operano su tipi di dati diversi. Una classe in grado di visualizzare diversi tipi di dati, ad esempio, potrebbe avere `Display` procedure simili alle seguenti:

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

Senza l'overload, è necessario creare nomi distinti per ogni routine, anche se eseguono la stessa operazione, come illustrato di seguito:

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

L'overload rende più semplice l'utilizzo di proprietà o metodi perché fornisce una scelta dei tipi di dati che è possibile utilizzare. Ad esempio, il metodo di `Display` di overload illustrato in precedenza può essere chiamato con una delle righe di codice seguenti:

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

In fase di esecuzione Visual Basic chiama la procedura corretta in base ai tipi di dati dei parametri specificati.

## <a name="overloading-rules"></a>Overload di regole

 Per creare un membro di overload per una classe, è necessario aggiungere due o più proprietà o metodi con lo stesso nome. Ad eccezione dei membri derivati in overload, ogni membro di overload deve avere elenchi di parametri diversi e gli elementi seguenti non possono essere usati come funzionalità di differenziazione quando si esegue l'overload di una proprietà o di una routine:

- Modificatori, ad esempio `ByVal` o `ByRef`, che si applicano a un membro o a parametri del membro.

- Nomi dei parametri

- Tipi restituiti di routine

La parola chiave `Overloads` è facoltativa quando si esegue l'overload, ma se un membro di overload usa la parola chiave `Overloads`, tutti gli altri membri di overload con lo stesso nome devono specificare anche questa parola chiave.

Le classi derivate possono eseguire l'overload di membri ereditati con membri che hanno parametri e tipi di parametro identici, un processo noto come *ombreggiatura per nome e firma*. Se la parola chiave `Overloads` viene utilizzata per l'ombreggiatura in base al nome e alla firma, l'implementazione della classe derivata del membro verrà utilizzata al posto dell'implementazione nella classe di base e tutti gli altri overload per quel membro saranno disponibili per le istanze della classe derivata.

Se la parola chiave `Overloads` viene omessa quando si esegue l'overload di un membro ereditato con un membro che ha parametri e tipi di parametro identici, l'overload viene chiamato *ombreggiatura in base al nome*. Lo shadowing in base al nome sostituisce l'implementazione ereditata di un membro e rende non disponibili tutti gli altri overload per le istanze della classe derivata e il relativo discendenti.

I modificatori `Overloads` e `Shadows` non possono essere usati entrambi con la stessa proprietà o metodo.

### <a name="example"></a>Esempio

Nell'esempio seguente vengono creati metodi di overload che accettano una rappresentazione `String` o `Decimal` di un importo in dollari e restituiscono una stringa che contiene l'imposta sulle vendite.

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Per usare questo esempio per creare un metodo di overload

1. Aprire un nuovo progetto e aggiungere una classe denominata `TaxClass`.

2. Aggiungere il codice seguente alla classe `TaxClass` .

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. Aggiungere la procedura seguente al form.

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. Aggiungere un pulsante al form e chiamare la procedura `ShowTax` dall'evento `Button1_Click` del pulsante.

5. Eseguire il progetto e fare clic sul pulsante nel form per testare la procedura di `ShowTax` di overload.

In fase di esecuzione, il compilatore sceglie la funzione di overload appropriata che corrisponde ai parametri utilizzati. Quando si fa clic sul pulsante, il metodo di overload viene chiamato prima con un `Price` parametro che è una stringa e il messaggio "Price è una stringa. L'imposta è pari a $5,12 ". `TaxAmount` viene chiamato con un valore `Decimal` la seconda volta e il messaggio "Price è un numero decimale. L'imposta è pari a $5,12 ".

## <a name="see-also"></a>Vedere anche

- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Nozioni fondamentali sull'ereditarietà](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)
- [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
