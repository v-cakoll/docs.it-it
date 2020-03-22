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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400855"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Passaggio di argomenti in base alla posizione e al nome (Visual Basic)

Quando si `Sub` chiama `Function` una routine o , è possibile passare gli argomenti in base alla *posizione,* nell'ordine in cui appaiono nella definizione della routine, oppure è possibile passarli in base al *nome,* indipendentemente dalla posizione.

Quando si passa un argomento in base al nome, si specifica il`:=`nome dichiarato dell'argomento seguito da due punti e da un segno di uguale ( ), seguito dal valore dell'argomento. È possibile fornire argomenti denominati in qualsiasi ordine.

Ad esempio, `Sub` la procedura seguente accetta tre argomenti:For example, the following procedure takes three arguments:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

Quando si chiama questa routine, è possibile fornire gli argomenti in base alla posizione, al nome o utilizzando una combinazione di entrambi.

## <a name="passing-arguments-by-position"></a>Passaggio di argomenti per posizionePassing Arguments by Position

È possibile `Display` chiamare il metodo con i relativi argomenti passati per posizione e delimitati da virgole, come illustrato nell'esempio seguente:You can call the method with its arguments passed by position and delimited by commas, as shown in the following example:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Se si omette un argomento facoltativo in un elenco di argomenti posizionali, è necessario mantenere la posizione con una virgola. Nell'esempio seguente `Display` viene `age` chiamato il metodo senza l'argomento :

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Passaggio di argomenti per nomePassing Arguments by Name

In alternativa, è `Display` possibile chiamare con gli argomenti passati per nome, anch'imdelimitati da virgole, come illustrato nell'esempio seguente:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Il passaggio di argomenti per nome in questo modo è particolarmente utile quando si chiama una routine con più argomenti facoltativi. Se si specificano argomenti in base al nome, non è necessario utilizzare virgole consecutive per indicare gli argomenti posizionali mancanti. Il passaggio di argomenti per nome rende inoltre più semplice tenere traccia degli argomenti che si stanno passando e di quelli che si omettono.

## <a name="mixing-arguments-by-position-and-by-name"></a>Combinazione di argomenti per posizione e per nome

È possibile fornire argomenti sia in base alla posizione che al nome in una singola chiamata di routine, come illustrato nell'esempio seguente:You can supply arguments both by position and by name in a single procedure call, as shown in the following example:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

Nell'esempio precedente, non è necessaria alcuna virgola aggiuntiva per contenere la posizione dell'argomento omesso, `age` poiché `birth` viene passata per nome.

Nelle versioni di Visual Basic precedenti alla 15.5, quando si forniscono argomenti con una combinazione di posizione e nome, gli argomenti posizionali devono venire tutti prima. Una volta fornito un argomento in base al nome, tutti gli argomenti rimanenti devono essere passati per nome.  Ad esempio, la seguente `Display` chiamata al metodo visualizza l'errore del compilatore [BC30241: argomento denominato previsto](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

A partire da Visual Basic 15.5, gli argomenti posizionali possono seguire argomenti denominati se gli argomenti posizionali finali si trovano nella posizione corretta. Se compilato in Visual Basic 15.5, `Display` la chiamata precedente al metodo viene compilata correttamente e non genera più l'errore del compilatore [BC30241](../../../misc/bc30241.md).

Questa possibilità di combinare e abbinare gli argomenti denominati e posizionali in qualsiasi ordine è particolarmente utile quando si desidera utilizzare un argomento denominato per rendere il codice più leggibile. Ad esempio, `Person` il costruttore di `Person`classe riportato di `Nothing`seguito richiede due argomenti di tipo , entrambi i quali possono essere .

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

L'utilizzo di argomenti denominati misti e posizionali consente `father` di `mother` rendere `Nothing`chiaro lo scopo del codice quando il valore degli argomenti e è :

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Per seguire argomenti posizionali con argomenti denominati, è necessario\*aggiungere il seguente elemento al file di progetto Visual Basic (vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Per ulteriori informazioni, vedere [Impostazione della versione del linguaggio Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Restrizioni sulla fornitura di argomenti in base al nomeRestrictions on Supplying Arguments by Name

Non è possibile passare argomenti in base al nome per evitare di immettere gli argomenti obbligatori. È possibile omettere solo gli argomenti facoltativi.

Non è possibile passare una matrice di parametri in base al nome. Inquesto modo, quando si chiama la routine, si fornisce un numero indefinito di argomenti delimitati da virgole per la matrice di parametri e il compilatore non può associare più di un argomento a un singolo nome.

## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Opzionale](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
