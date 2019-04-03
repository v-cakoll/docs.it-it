---
title: Passaggio di argomenti per valore e per riferimento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: c23ca51322f57dc13a85c3ea94e0d335dc50ca13
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830357"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Passaggio di argomenti per valore e per riferimento (Visual Basic)
In Visual Basic, è possibile passare un argomento a una routine *dal valore* oppure *per riferimento*. Questo è noto come il *meccanismo di trasferimento*, e determina se la routine può modificare l'elemento di programmazione sottostante all'argomento nel codice chiamante. La dichiarazione di routine determina il meccanismo di passaggio per ogni parametro specificando il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave).  
  
## <a name="distinctions"></a>Differenze  
 Quando si passa un argomento a una routine, occorre considerare diverse differenze diversi che interagiscono tra loro:  
  
-   Se l'elemento di programmazione sottostante è modificabile o meno  
  
-   Indica se l'argomento stesso è modificabile o meno  
  
-   Indica se l'argomento viene passato per valore o per riferimento  
  
-   Indica se il tipo di dati di argomento è un tipo di valore o un tipo riferimento  
  
 Per altre informazioni, vedere [argomenti non è modificabile e le differenze tra modificabile](./differences-between-modifiable-and-nonmodifiable-arguments.md) e [le differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Scelta del meccanismo di trasferimento  
 È consigliabile scegliere il meccanismo di passaggio con attenzione per ogni argomento.  
  
-   **Protezione**. Nella scelta tra i due meccanismi di passaggio, il criterio più importante è l'esposizione della chiamata al metodo le variabili da modificare. Il vantaggio di passaggio di un argomento `ByRef` è che la procedura può restituire un valore al codice chiamante tramite l'argomento. Il vantaggio di passaggio di un argomento `ByVal` è che impedisce che la variabile viene modificato dalla procedura.  
  
-   **Prestazioni**. Anche se il meccanismo di passaggio può influire sulle prestazioni del codice, la differenza non è in genere significativo. Unica eccezione è un tipo di valore passato `ByVal`. In questo caso, Visual Basic copia il contenuto di tutti i dati dell'argomento. Pertanto, per un tipo di valori di grandi dimensioni, ad esempio una struttura, può essere più efficiente per passarlo `ByRef`.  
  
     Per i tipi di riferimento, solo il puntatore ai dati viene copiati (quattro byte sulle piattaforme a 32 bit, otto byte sulle piattaforme a 64 bit). Pertanto, è possibile passare argomenti di tipo `String` o `Object` dal valore senza compromettere le prestazioni.  
  
## <a name="determination-of-the-passing-mechanism"></a>Determinazione del meccanismo di passaggio  
 La dichiarazione di routine specifica il meccanismo di passaggio per ogni parametro. Il codice chiamante non è possibile sostituire un `ByVal` meccanismo.  
  
 Se un parametro viene dichiarato con `ByRef`, il codice chiamante può forzare il meccanismo `ByVal` racchiudendo il nome dell'argomento racchiuso tra parentesi nella chiamata. Per altre informazioni, vedere [Procedura: Forzare un argomento da passare per valore](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 L'impostazione predefinita in Visual Basic consiste nel passare argomenti per valore.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Quando un argomento venga passato per valore  
  
-   Se l'elemento di codice chiamante sottostante l'argomento non è modificabile, dichiarare il parametro corrispondente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Codice non è possibile modificare il valore di un elemento non è modificabile.  
  
-   Se l'elemento sottostante è modificabile, ma non si desidera la procedura per essere in grado di modificare il relativo valore, dichiarare il parametro `ByVal`. Solo il codice chiamante può modificare il valore di un elemento modificabile passato per valore.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Quando un argomento venga passato per riferimento  
  
-   Se la procedura richiede la modifica dell'elemento sottostante nel codice chiamante, dichiarare il parametro corrispondente [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Se l'esecuzione corretta del codice dipende la procedura di modifica dell'elemento nel codice chiamante, dichiarare il parametro `ByRef`. Se viene passato per valore o se il codice chiamante esegue l'override di `ByRef` meccanismo di trasferimento racchiudendo l'argomento racchiuso tra parentesi, la chiamata di procedura può produrre risultati imprevisti.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrato quando gli argomenti vengono passati per valore e passarle per riferimento. Routine `Calculate` abbia sia un' `ByVal` e un `ByRef` parametro. Dato un tasso di interesse `rate`, nonché la somma di denaro, `debt`, l'attività della procedura consiste nel calcolare un nuovo valore per `debt` che rappresenta il risultato dell'applicazione del tasso di interesse per il valore originale di `debt`. In quanto `debt` è un `ByRef` parametro, il nuovo totale viene riflessa nel valore dell'argomento nel codice chiamante che corrisponde a `debt`. Parametro `rate` è un `ByVal` parametro perché `Calculate` consiglia di non modificare il relativo valore.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Procedura: Modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: Proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedura: Forzare un argomento da passare per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
