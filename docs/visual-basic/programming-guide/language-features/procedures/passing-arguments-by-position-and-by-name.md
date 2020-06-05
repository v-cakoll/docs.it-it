---
title: Passaggio di argomenti in base alla posizione e al nome
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: 686b64977f086c8128e56298a0ed8c5aa0c51efa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364032"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Passaggio di argomenti in base alla posizione e al nome (Visual Basic)

Quando si chiama una `Sub` `Function` routine o, è possibile passare gli argomenti in *base alla posizione* , nell'ordine in cui sono visualizzati nella definizione della procedura, oppure è possibile passarli in base al *nome*, senza considerare la posizione.

Quando si passa un argomento in base al nome, si specifica il nome dichiarato dell'argomento seguito da due punti e da un segno di uguale ( `:=` ), seguito dal valore dell'argomento. Gli argomenti denominati possono essere forniti in qualsiasi ordine.

Ad esempio, la `Sub` procedura seguente accetta tre argomenti:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

Quando si chiama questa procedura, è possibile fornire gli argomenti in base alla posizione, al nome o utilizzando una combinazione di entrambi.

## <a name="passing-arguments-by-position"></a>Passaggio di argomenti in base alla posizione

È possibile chiamare il `Display` metodo con i relativi argomenti passati in base alla posizione e delimitati da virgole, come illustrato nell'esempio seguente:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Se si omette un argomento facoltativo in un elenco di argomenti posizionali, è necessario mantenere la relativa posizione con una virgola. Nell'esempio seguente viene chiamato il `Display` metodo senza l' `age` argomento:

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Passaggio di argomenti in base al nome

In alternativa, è possibile chiamare `Display` con gli argomenti passati in base al nome, anche delimitati da virgole, come illustrato nell'esempio seguente:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Il passaggio di argomenti in base al nome in questo modo è particolarmente utile quando si chiama una routine con più di un argomento facoltativo. Se si forniscono gli argomenti in base al nome, non è necessario usare virgole consecutive per indicare gli argomenti posizionali mancanti. Il passaggio di argomenti in base al nome rende anche più semplice tenere traccia degli argomenti passati e di quelli che vengono omessi.

## <a name="mixing-arguments-by-position-and-by-name"></a>Combinazione di argomenti in base alla posizione e al nome

È possibile specificare gli argomenti sia per posizione che per nome in una singola chiamata di procedura, come illustrato nell'esempio seguente:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

Nell'esempio precedente, non è necessaria alcuna virgola aggiuntiva per conservare il posto dell'argomento omesso `age` , poiché `birth` viene passato in base al nome.

Nelle versioni di Visual Basic prima del 15,5, quando si forniscono argomenti in base a una combinazione di posizione e nome, gli argomenti posizionali devono essere tutti primi. Una volta specificato un argomento in base al nome, tutti gli argomenti rimanenti devono essere tutti passati in base al nome.  Ad esempio, la chiamata seguente al `Display` Metodo Visualizza l'errore del compilatore [BC30241: è previsto l'argomento denominato](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

A partire da Visual Basic 15,5, gli argomenti posizionali possono seguire gli argomenti denominati se gli argomenti posizionali finali sono nella posizione corretta. Se compilata in Visual Basic 15,5, la chiamata precedente al `Display` metodo viene compilata correttamente e non genera più l'errore del compilatore [BC30241](../../../misc/bc30241.md).

Questa possibilità di combinare gli argomenti denominati e posizionali in qualsiasi ordine è particolarmente utile quando si vuole usare un argomento denominato per rendere il codice più leggibile. Ad esempio, il `Person` costruttore di classe seguente richiede due argomenti di tipo `Person` , entrambi possibili `Nothing` .

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

L'utilizzo di argomenti denominati e posizionali misti consente di rendere chiaro lo scopo del codice quando il valore `father` degli `mother` argomenti e è `Nothing` :

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Per seguire gli argomenti posizionali con argomenti denominati, è necessario aggiungere l'elemento seguente al file del progetto Visual Basic ( \* . vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Restrizioni relative alla fornitura di argomenti in base al nome

Non è possibile passare argomenti per nome per evitare di immettere argomenti obbligatori. È possibile omettere solo gli argomenti facoltativi.

Non è possibile passare una matrice di parametri in base al nome. Questo perché quando si chiama la routine, si fornisce un numero indefinito di argomenti delimitati da virgole per la matrice di parametri e il compilatore non può associare più di un argomento con un solo nome.

## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Facoltativo](../../../language-reference/modifiers/optional.md)
- [ParamArray](../../../language-reference/modifiers/paramarray.md)
