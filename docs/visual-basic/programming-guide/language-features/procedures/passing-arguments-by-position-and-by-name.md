---
title: Passaggio di argomenti in base alla posizione e al nome (Visual Basic)
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
ms.openlocfilehash: b872eda97d1e349ad781b12810e4b166d6e46fe1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837312"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Passaggio di argomenti in base alla posizione e al nome (Visual Basic)
Quando si chiama un `Sub` o `Function` procedura, è possibile passare argomenti *in base alla posizione* , ovvero nell'ordine in cui appaiono nella definizione della stored procedure, oppure è possibile passare loro *in base al nome*, senza tener conto della posizione.  
  
 Quando si passa un argomento in base al nome, specificare il dichiarato dell'argomento nome seguito da due punti e un segno di uguale (`:=`), seguito dal valore dell'argomento. È possibile fornire gli argomenti denominati in qualsiasi ordine.  
  
 Ad esempio, il seguente `Sub` procedura accetta tre argomenti:  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 Quando si chiama questa procedura, è possibile fornire gli argomenti in base alla posizione, in base al nome o utilizzando una combinazione di entrambi.  
  
## <a name="passing-arguments-by-position"></a>Passaggio di argomenti in base alla posizione  
 È possibile chiamare il `Display` con i relativi argomenti metodo passati per posizione e delimitato da virgole, come illustrato nell'esempio seguente:  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 Se si omette un argomento facoltativo in un elenco di argomenti posizionali, è necessario tenere sostituirla con una virgola. L'esempio seguente chiama il `Display` metodo senza il `age` argomento:  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>Passaggio di argomenti in base al nome  
 In alternativa, è possibile chiamare `Display` con gli argomenti passati in base al nome, delimitati da virgole, come illustrato nell'esempio seguente:  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 Passaggio di argomenti in base al nome in questo modo è particolarmente utile quando si chiama una routine che ha più di un argomento facoltativo. Se si specificano gli argomenti in base al nome, non è necessario utilizzare virgole per indicare gli argomenti posizionali mancante. Passaggio di argomenti in base al nome inoltre rende più semplice tenere traccia di argomenti passati e quelle che sono omessi.  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Combinazione di argomenti in base alla posizione e al nome  

È possibile fornire argomenti in base alla posizione e in base al nome in un'unica chiamata di routine, come illustrato nell'esempio seguente:  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 Nell'esempio precedente, non è necessario indicare la posizione dell'omessi nessuna virgola aggiuntiva `age` argomento, poiché `birth` viene passato in base al nome.  
  
Nelle versioni precedenti alla 15.5 di Visual Basic, quando si specificano argomenti per una combinazione di posizione e il nome, gli argomenti posizionali devono provenire tutte prima. Una volta che viene fornito un argomento in base al nome, tutti gli argomenti rimanenti devono essere passati per nome.  Ad esempio, la chiamata seguente al `Display` metodo viene visualizzato l'errore del compilatore [BC30241: È previsto un argomento denominato](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

A partire da Visual Basic 15.5, gli argomenti posizionali possono seguire gli argomenti denominati se gli argomenti posizionali finali sono nella posizione corretta. Se compilato in Visual Basic 15.5, chiamata precedente al `Display` metodo viene compilato correttamente e non genera l'errore del compilatore [BC30241](../../../misc/bc30241.md).  

La possibilità di combinare e abbinare gli argomenti denominati e posizionali in qualsiasi ordine è particolarmente utile quando si vuole usare un argomento denominato per rendere il codice più leggibile. Ad esempio, il seguente `Person` costruttore di classe richiede due argomenti di tipo `Person`, che può essere `Nothing`. 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

Utilizzo misti argomenti denominati e posizionali per rendere lo scopo del codice consente di cancellare quando il valore della `father` e `mother` argomenti sono `Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

Per seguire gli argomenti posizionali con gli argomenti denominati, è necessario aggiungere l'elemento seguente al progetto Visual Basic (\*vbproj) file:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Per altre informazioni, vedere [impostando la versione del linguaggio Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Restrizioni per l'impostazione degli argomenti in base al nome  

È possibile passare argomenti in base al nome di evitare l'immissione di argomenti obbligatori. È possibile omettere solo gli argomenti facoltativi.  
  
È possibile passare una matrice di parametri in base al nome. Infatti, quando si chiama la procedura, si fornisce un numero indefinito di argomenti delimitati da virgole per la matrice di parametri e il compilatore non è possibile associare più di un argomento con lo stesso nome.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
