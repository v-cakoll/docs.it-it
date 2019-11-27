---
title: Valori restituiti Ref
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: 2d2a302a899fbde549161469f281d3e580bcb71f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352546"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Supporto per i valori restituiti di riferimento (Visual Basic)

A partire C# da 7,0, C# il linguaggio supporta i *valori restituiti di riferimento*. Un modo per comprendere i valori restituiti di riferimento è che si tratta del contrario degli argomenti passati per riferimento a un metodo. Quando viene modificato un argomento passato per riferimento, le modifiche vengono riflesse nel valore della variabile nel chiamante. Quando un metodo fornisce un valore restituito di riferimento a un chiamante, le modifiche apportate al valore restituito di riferimento dal chiamante vengono riflesse nei dati del metodo chiamato.

Visual Basic non consente di creare metodi con valori restituiti di riferimento, ma consente di utilizzare valori restituiti di riferimento. In altre parole, è possibile chiamare un metodo con un valore restituito di riferimento e modificare il valore restituito e le modifiche apportate al valore restituito di riferimento vengono riflesse nei dati del metodo chiamato.

## <a name="modifying-the-ref-return-value-directly"></a>Modifica diretta del valore restituito Ref

Per i metodi che hanno sempre esito positivo e non hanno parametri di `ByRef`, è possibile modificare direttamente il valore restituito di riferimento. A tale scopo, assegnare il nuovo valore alle espressioni che restituiscono il valore restituito di riferimento.

Nell'esempio C# seguente viene definito un metodo di `NumericValue.IncrementValue` che incrementa un valore interno e lo restituisce come valore restituito di riferimento.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Il valore restituito di riferimento viene quindi modificato dal chiamante nell'esempio di Visual Basic seguente. Si noti che la riga con la chiamata al metodo `NumericValue.IncrementValue` non assegna un valore al metodo. Assegna invece un valore al valore restituito di riferimento restituito dal metodo.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Uso di un metodo helper

In altri casi, la modifica del valore restituito di riferimento di una chiamata al metodo può non essere sempre auspicabile. Un metodo di ricerca che restituisce una stringa, ad esempio, potrebbe non essere sempre in grado di trovare una corrispondenza. In tal caso, si desidera modificare il valore restituito di riferimento solo se la ricerca ha esito positivo.

Nell'esempio C# seguente viene illustrato questo scenario. Definisce una classe `Sentence` scritta in C# include un metodo `FindNext` che trova la parola successiva in una frase che inizia con una sottostringa specificata. La stringa viene restituita come valore di riferimento restituito. Una variabile `Boolean` passata dal riferimento al metodo indica se la ricerca ha avuto esito positivo. Il valore restituito di riferimento indica che il chiamante non solo può leggere il valore restituito. può anche modificarla e tale modifica viene riflessa nei dati contenuti internamente nella classe `Sentence`.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

La modifica diretta del valore restituito di riferimento in questo caso non è affidabile, perché la chiamata al metodo potrebbe non riuscire a trovare una corrispondenza e restituire la prima parola nella frase. In tal caso, il chiamante modificherà inavvertitamente la prima parola della frase. Questa operazione può essere impedita dal chiamante che restituisce una `null` (o `Nothing` in Visual Basic). In tal caso, tuttavia, il tentativo di modificare una stringa il cui valore è `Nothing` genera un'<xref:System.NullReferenceException>. Se può essere impedito anche dal chiamante che restituisce <xref:System.String.Empty?displayProperty=nameWithType>, ma ciò richiede che il chiamante definisca una variabile di stringa il cui valore è <xref:System.String.Empty?displayProperty=nameWithType>. Sebbene il chiamante possa modificare tale stringa, la modifica non ha alcun effetto, perché la stringa modificata non ha alcuna relazione con le parole nella frase archiviata dalla classe `Sentence`.

Il modo migliore per gestire questo scenario è passare il valore restituito di riferimento per riferimento a un metodo helper. Il metodo helper contiene quindi la logica per determinare se la chiamata al metodo ha avuto esito positivo e, in caso affermativo, per modificare il valore restituito di riferimento. Nell'esempio seguente viene fornita un'implementazione possibile.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Passaggio di argomenti per valore e per riferimento](passing-arguments-by-value-and-by-reference.md)
- [Routine in Visual Basic](index.md)
