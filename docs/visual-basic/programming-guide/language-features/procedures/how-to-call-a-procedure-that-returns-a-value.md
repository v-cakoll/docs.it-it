---
title: 'Procedura: Chiamare una routine che restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 8d9c7f3eadfa0095e0ed49b3a7a207fd3f7f8769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525456"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Procedura: Chiamare una routine che restituisce un valore (Visual Basic)
Oggetto `Function` routine restituisce un valore al codice chiamante. È chiamarlo includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Per chiamare una routine di funzione all'interno di un'espressione  
  
1.  Usare il `Function` procedure assegnare un nome simile a quello è necessario usare una variabile. È possibile usare un `Function` ovunque è possibile usare una variabile o costante in un'espressione di chiamata di procedura.  
  
2.  Seguire il nome della routine tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi. Tuttavia, usando le parentesi che rende il codice più facile da leggere.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi di inserire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti.  
  
     In alternativa, è possibile passare uno o più argomenti in base al nome. Per altre informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md).  
  
4.  Il valore restituito dalla procedura fa parte dell'espressione come valore di una variabile o costante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Per chiamare una routine di funzione in un'istruzione di assegnazione  
  
1.  Usare la `Function` nome procedura che segue l'uguale (`=`) Accedi l'istruzione di assegnazione.  
  
2.  Seguire il nome della routine tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi. Tuttavia, usando le parentesi che rende il codice più facile da leggere.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi di inserire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti, a meno che vengano passati in base al nome.  
  
4.  Il valore restituito dalla routine viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente chiama il Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> per recuperare il valore di una variabile di ambiente del sistema operativo. La prima riga chiama `Environ` all'interno di un'espressione e il secondo viene chiamata in un'istruzione di assegnazione. `Environ` accetta il nome della variabile come unico argomento. Restituisce il valore della variabile al codice chiamante.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Routine Function](./function-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Procedura: Creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedura: Restituisce il valore da una routine](./how-to-return-a-value-from-a-procedure.md)
- [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)
