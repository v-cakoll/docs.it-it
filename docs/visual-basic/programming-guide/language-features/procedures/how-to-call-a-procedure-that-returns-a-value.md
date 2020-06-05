---
title: 'Procedura: chiamare una routine che restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: a110cf9f3b42c7244d8d5bf7b49d5e6dac8c2e21
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388764"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Procedura: chiamare una routine che restituisce un valore (Visual Basic)
Una `Function` routine restituisce un valore al codice chiamante. È possibile chiamarlo includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Per chiamare una routine di funzione in un'espressione  
  
1. Usare il `Function` nome della procedura nello stesso modo in cui si usa una variabile. È possibile utilizzare una `Function` chiamata di routine in qualsiasi punto in cui è possibile utilizzare una variabile o una costante in un'espressione.  
  
2. Seguire il nome della procedura con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi. Tuttavia, l'utilizzo delle parentesi rende il codice più semplice da leggere.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la `Function` procedura definisce i parametri corrispondenti.  
  
     In alternativa, è possibile passare uno o più argomenti in base al nome. Per ulteriori informazioni, vedere [passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md).  
  
4. Il valore restituito dalla stored procedure fa parte dell'espressione esattamente come il valore di una variabile o di una costante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Per chiamare una routine di funzione in un'istruzione di assegnazione  
  
1. Utilizzare il `Function` nome della procedura dopo il `=` segno di uguale () nell'istruzione di assegnazione.  
  
2. Seguire il nome della procedura con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi. Tuttavia, l'utilizzo delle parentesi rende il codice più semplice da leggere.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la `Function` procedura definisce i parametri corrispondenti, a meno che non vengano passati in base al nome.  
  
4. Il valore restituito dalla routine viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene chiamato il Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> per recuperare il valore di una variabile di ambiente del sistema operativo. La prima riga chiama `Environ` in un'espressione e la seconda riga la chiama in un'istruzione di assegnazione. `Environ`accetta il nome della variabile come unico argomento. Restituisce il valore della variabile al codice chiamante.  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine Function](./function-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../language-reference/statements/function-statement.md)
- [Procedura: creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedura: restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md)
- [Procedura: chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)
