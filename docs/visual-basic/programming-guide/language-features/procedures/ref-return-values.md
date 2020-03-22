---
title: Valori restituiti refRef Return Values
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: f2a92c584dbb12a322e28435d797fa4d7c2f6dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186928"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Supporto per valori restituiti di riferimento (Visual Basic)Support for reference return values (Visual Basic)

A partire dalla versione 7.0 di C, il linguaggio C'è supporta i *valori restituiti*di riferimento. Un modo per comprendere i valori restituiti di riferimento è che sono l'opposto degli argomenti passati per riferimento a un metodo. Quando un argomento passato per riferimento viene modificato, le modifiche vengono riflesse nel valore della variabile nel chiamante. Quando un metodo fornisce un valore restituito di riferimento a un chiamante, le modifiche apportate al valore restituito di riferimento dal chiamante vengono riflesse nei dati del metodo chiamato.

Visual Basic non consente di creare metodi con valori restituiti di riferimento, ma consente di utilizzare i valori restituiti di riferimento. In altre parole, è possibile chiamare un metodo con un valore restituito di riferimento e modificare tale valore restituito e le modifiche al valore restituito di riferimento vengono riflesse nei dati del metodo chiamato.

## <a name="modifying-the-ref-return-value-directly"></a>Modifica diretta del valore restituito ref

Per i metodi che `ByRef` hanno sempre esito positivo e non dispongono di parametri, è possibile modificare direttamente il valore restituito di riferimento. A tale scopo, assegnare il nuovo valore alle espressioni che restituisce il valore restituito di riferimento.

Nell'esempio in Cè `NumericValue.IncrementValue` riportato di seguito viene definito un metodo che incrementa un valore interno e lo restituisce come valore restituito di riferimento.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Il valore restituito di riferimento viene quindi modificato dal chiamante nell'esempio di Visual Basic seguente. Si noti che `NumericValue.IncrementValue` la riga con la chiamata al metodo non assegna un valore al metodo. Al contrario, assegna un valore al valore restituito di riferimento restituito dal metodo.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Utilizzo di un metodo di supportoUsing a helper method

In altri casi, la modifica diretta del valore restituito di riferimento di una chiamata al metodo potrebbe non essere sempre auspicabile. Ad esempio, un metodo di ricerca che restituisce una stringa potrebbe non trovare sempre una corrispondenza. In tal caso, si desidera modificare il valore restituito di riferimento solo se la ricerca ha esito positivo.

Questo scenario viene illustrato nell'esempio in C., riportato di seguito. Viene definita `Sentence` una classe scritta `FindNext` in C, include un metodo che trova la parola successiva in una frase che inizia con una sottostringa specificata. La stringa viene restituita come valore di riferimento restituito. Una variabile `Boolean` passata dal riferimento al metodo indica se la ricerca ha avuto esito positivo. Il valore restituito di riferimento indica che oltre a leggere il valore restituito, il chiamante può anche modificarlo e tale modifica si riflette nei dati contenuti internamente nella `Sentence` classe.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

La modifica diretta del valore restituito di riferimento in questo caso non è affidabile, poiché la chiamata al metodo potrebbe non riuscire a trovare una corrispondenza e restituire la prima parola nella frase. In tal caso, il chiamante modificherà inavvertitamente la prima parola della frase. Ciò potrebbe essere impedito dal `null` chiamante che restituisce un (o `Nothing` in Visual Basic). Ma in questo caso, il tentativo di `Nothing` modificare <xref:System.NullReferenceException>una stringa il cui valore è genera un oggetto . Se potrebbe essere impedito anche <xref:System.String.Empty?displayProperty=nameWithType>il chiamante che restituisce , ma <xref:System.String.Empty?displayProperty=nameWithType>ciò richiede che il chiamante definisca una variabile stringa il cui valore è . Mentre il chiamante può modificare tale stringa, la modifica stessa non serve a nulla, `Sentence` poiché la stringa modificata non ha alcuna relazione con le parole nella frase archiviata dalla classe.

Il modo migliore per gestire questo scenario consiste nel passare il valore restituito di riferimento per riferimento a un metodo di supporto. Il metodo di supporto contiene quindi la logica per determinare se la chiamata al metodo ha avuto esito positivo e, in caso affermativo, per modificare il valore restituito di riferimento. Nell'esempio seguente viene fornita una possibile implementazione.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Passaggio di argomenti per valore e per riferimentoPassing arguments by value and by reference](passing-arguments-by-value-and-by-reference.md)
- [Routine in Visual Basic](index.md)
