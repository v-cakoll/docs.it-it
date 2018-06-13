---
title: 'Procedura: chiamare una routine che restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 35f757609b6d0b36652db3b14e62ecd299a063ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649412"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Procedura: chiamare una routine che restituisce un valore (Visual Basic)
Oggetto `Function` routine restituisce un valore al codice chiamante. Si chiama, includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Per chiamare una routine di funzione all'interno di un'espressione  
  
1.  Utilizzare il `Function` procedure nome esattamente come si utilizzerebbe una variabile. È possibile utilizzare un `Function` remoto via Internet, è possibile utilizzare una variabile o costante in un'espressione di chiamata di procedura.  
  
2.  Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi. Tuttavia, l'utilizzo delle parentesi, il codice più facile da leggere.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi fornire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti.  
  
     In alternativa, è possibile passare uno o più argomenti in base al nome. Per ulteriori informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md).  
  
4.  Il valore restituito dalla routine fa parte dell'espressione come valore di una variabile o costante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Per chiamare una routine di funzione in un'istruzione di assegnazione  
  
1.  Utilizzare il `Function` nome della stored procedure seguente uguali (`=`) Accedi l'istruzione di assegnazione.  
  
2.  Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi. Tuttavia, l'utilizzo delle parentesi, il codice più facile da leggere.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi fornire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti, a meno che vengano passati in base al nome.  
  
4.  Il valore restituito dalla routine viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente chiama Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> per recuperare il valore di una variabile di ambiente del sistema operativo. Il prima riga chiama `Environ` all'interno di un'espressione, mentre la seconda viene chiamata in un'istruzione di assegnazione. `Environ` accetta il nome della variabile come unico argomento. Restituisce il valore della variabile al codice chiamante.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine Function](./function-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Procedura: Creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Procedura: Restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md)  
 [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)
