---
title: Valori restituiti ref (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: d0600f7d9030324160343e800c37e0f5e68bff61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791807"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Supporto per i valori restituiti di riferimento (Visual Basic)

A partire da C# 7.0, il C# supporta la lingua *fanno riferimento a valori restituiti*. Un modo per comprendere i valori restituiti di riferimento è che sono l'opposto di argomenti che vengono passati per riferimento a un metodo. Quando viene modificato un argomento passato per riferimento, le modifiche si riflettono nel valore della variabile sul chiamante. Quando un metodo non fornisce un valore restituito di riferimento a un chiamante, le modifiche apportate al valore restituito di riferimento dal chiamante vengono riflesse nei dati del metodo chiamato.

Visual Basic non consente di modifica dei metodi con riferimento a valori restituiti, ma consente all'utente i valori restituiti di riferimento. In altre parole, è possibile chiamare un metodo con un valore restituito di riferimento e modificare tale valore restituito e il valore restituito di riferimento vengono riflesse nei dati del metodo chiamato.

## <a name="modifying-the-ref-return-value-directly"></a>Modificare direttamente il valore restituito ref

Per i metodi che abbia esito positivo e non hanno sempre `ByRef` parametri, è possibile modificare direttamente il valore restituito di riferimento. Questo scopo, assegnare il nuovo valore per le espressioni che restituisce il valore restituito di riferimento. 

Il seguente C# esempio definisce un `NumericValue.IncrementValue` valore restituito di metodo che incrementa un valore interno e lo restituisce come riferimento. 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Il riferimento restituito valore viene quindi modificato dal chiamante nell'esempio seguente Visual Basic. Si noti che la riga con il `NumericValue.IncrementValue` chiamata al metodo non assegna un valore al metodo. Al contrario, assegna un valore per il valore restituito di riferimento restituito dal metodo.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Usando un metodo di supporto

In altri casi, modificare direttamente il valore restituito di riferimento di una chiamata al metodo potrebbe non essere sempre auspicabile. Ad esempio, un metodo di ricerca che restituisce una stringa non può sempre trovare una corrispondenza. In tal caso, si desidera modificare il valore restituito di riferimento solo se la ricerca ha esito positivo.

Il seguente C# riportato di seguito viene illustrato questo scenario. Definisce un `Sentence` classe scritta in C# include un `FindNext` metodo che individua la parola successiva in una frase che inizia con una sottostringa specificata. La stringa viene restituita come valore di riferimento restituito. Una variabile `Boolean` passata dal riferimento al metodo indica se la ricerca ha avuto esito positivo. Il valore restituito di riferimento indica che il chiamante non solo può leggere il valore restituito. Egli può anche modificare e tale modifica si riflette i dati contenuti all'interno di `Sentence` classe.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Modificare direttamente il riferimento al valore restituito in questo caso non è affidabile, poiché la chiamata al metodo potrebbe non riuscire a trovare una corrispondenza e restituire la prima parola nella frase. In tal caso, il chiamante modifichi inavvertitamente la prima parola della frase. Ciò potrebbe non essere consentito dal chiamante restituzione di un `null` (o `Nothing` in Visual Basic). Ma in tal caso, il tentativo di modificare una stringa il cui valore è `Nothing` genera un <xref:System.NullReferenceException>. Se è anche possibile prevenire il chiamante restituzione <xref:System.String.Empty?displayProperty=nameWithType>, ma è necessario che il chiamante definire una variabile stringa il cui valore è <xref:System.String.Empty?displayProperty=nameWithType>. Anche se il chiamante può modificare tale stringa, la modifica stessa non ha alcuna utilità, poiché la stringa modificata non ha alcuna relazione con le parole nella frase archiviata dal `Sentence` classe.

Il modo migliore per gestire questo scenario consiste nel passare il valore restituito di riferimento per riferimento a un metodo helper. Quindi, il metodo helper contiene la logica per determinare se la chiamata al metodo ha avuto esito positivo e, in caso contrario, per modificare il valore di riferimento restituito. Nell'esempio seguente fornisce una possibile implementazione.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Passaggio di argomenti per valore e per riferimento](passing-arguments-by-value-and-by-reference.md)
- [Routine in Visual Basic](index.md)
