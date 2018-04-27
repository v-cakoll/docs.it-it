---
title: Valori restituiti ref (Visual Basic)
ms.custom: ''
ms.date: 04/28/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6055028ac92016cbc4b6f7bffa7f483e5ea76608
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="support-for-reference-return-values-visual-basic"></a>Supporto per i valori restituiti di riferimento (Visual Basic)

A partire da c# 7.0, supporta il linguaggio c# *fanno riferimento a valori restituiti*. Un modo per comprendere i valori restituiti di riferimento è che sono l'opposto di argomenti che vengono passati per riferimento a un metodo. Quando si modifica un argomento passato per riferimento, le modifiche vengono riflesse nel valore della variabile sul chiamante. Quando un metodo fornisce un valore restituito di riferimento a un chiamante, le modifiche apportate al valore restituito di riferimento dal chiamante vengono riflesse nei dati del metodo chiamato.

Visual Basic non consente di modifica dei metodi con riferimento restituire valori, ma consente di usare i valori restituiti di riferimento. In altre parole, è possibile chiamare un metodo con un valore restituito di riferimento e modificare il valore restituito e il valore restituito di riferimento vengono riflesse nei dati del metodo chiamato.

## <a name="modifying-the-ref-return-value-directly"></a>Modificare direttamente il valore restituito di riferimento

Per i metodi che è sempre esito positivo e non hanno alcun `ByRef` parametri, è possibile modificare direttamente il valore restituito di riferimento. Questo scopo, assegnare il nuovo valore per le espressioni che restituisce il valore restituito di riferimento. 

L'esempio c# seguente definisce un `NumericValue.IncrementValue` metodo che viene incrementato di un valore interno e lo restituisce come riferimento a un valore restituito. 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Il riferimento restituito valore viene quindi modificato dal chiamante nel seguente esempio di Visual Basic. Si noti che la riga con il `NumericValue.IncrementValue` chiamata al metodo non assegna un valore al metodo. Al contrario, assegna un valore per il valore restituito di riferimento restituito dal metodo.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Utilizzo di un metodo di supporto

In altri casi, modificare direttamente il valore restituito di riferimento di una chiamata al metodo potrebbe non essere sempre auspicabile. Ad esempio, un metodo che restituisce una stringa di ricerca non può sempre trovare una corrispondenza. In tal caso, si desidera modificare il valore restituito di riferimento solo se la ricerca ha esito positivo.

Nell'esempio c# seguente viene illustrato questo scenario. Definisce un `Sentence` classe scritta in c# include un `FindNext` metodo che individua la parola successiva in una frase che inizia con una sottostringa specificata. La stringa viene restituita come valore di riferimento restituito. Una variabile `Boolean` passata dal riferimento al metodo indica se la ricerca ha avuto esito positivo. Il valore restituito di riferimento indica che il chiamante può non solo leggere il valore restituito. Egli può inoltre modificarlo e tale modifica viene riflessa nei dati contenuti all'interno di `Sentence` classe.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Modificare direttamente il riferimento restituito valore in questo caso non è affidabile, poiché la chiamata al metodo potrebbe non riuscire a trovare una corrispondenza e restituisce la prima parola della frase. In tal caso, il chiamante inavvertitamente modificherà la prima parola della frase. Questo stato può essere applicato dal chiamante restituendo un `null` (o `Nothing` in Visual Basic). Ma in tal caso, il tentativo di modificare una stringa il cui valore è `Nothing` genera un <xref:System.NullReferenceException>. Se potrebbe essere impedito anche dal chiamante restituzione <xref:System.String.Empty?displayProperty=nameWithType>, ma questa operazione richiede che il chiamante definire una variabile di stringa il cui valore è <xref:System.String.Empty?displayProperty=nameWithType>. Mentre il chiamante è possibile modificare tale stringa, la modifica stessa non ha alcuna utilità, poiché la stringa modificata non ha alcuna relazione con le parole della frase archiviate dalla `Sentence` classe.

Il modo migliore per gestire questo scenario consiste nel passare il valore restituito di riferimento per riferimento a un metodo di supporto. Quindi, il metodo di supporto contiene la logica per determinare se la chiamata al metodo ha avuto esito positivo e, in caso contrario, per modificare il riferimento al valore restituito. Nell'esempio seguente fornisce una possibile implementazione.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Vedere anche

[Passaggio di argomenti per valore e per riferimento](passing-arguments-by-value-and-by-reference.md)   
[Routine in Visual Basic](index.md)   


