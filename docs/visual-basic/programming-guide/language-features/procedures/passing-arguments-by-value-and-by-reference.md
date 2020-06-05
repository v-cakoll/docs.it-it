---
title: Passaggio di argomenti per valore e per riferimento
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: 3dd4be6ea6de9dfe8eb165e5d4ba9a990fc40585
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363954"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Passaggio di argomenti per valore e per riferimento (Visual Basic)
In Visual Basic, è possibile passare un argomento a una routine per *valore* o *per riferimento*. Questo meccanismo è noto come *meccanismo di passaggio*e determina se la procedura può modificare l'elemento di programmazione sottostante l'argomento nel codice chiamante. La dichiarazione di routine determina il meccanismo di passaggio per ogni parametro specificando la parola chiave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) .  
  
## <a name="distinctions"></a>Distinzioni  
 Quando si passa un argomento a una routine, tenere presente che diverse differenze che interagiscono tra loro:  
  
- Indica se l'elemento di programmazione sottostante è modificabile o non modificabile  
  
- Indica se l'argomento è modificabile o non modificabile  
  
- Indica se l'argomento viene passato per valore o per riferimento  
  
- Indica se il tipo di dati dell'argomento è un tipo di valore o un tipo di riferimento  
  
 Per ulteriori informazioni, vedere [differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md) e [differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Scelta del meccanismo di passaggio  
 È consigliabile scegliere con attenzione il meccanismo di passaggio per ogni argomento.  
  
- **Protezione**. Quando si sceglie tra i due meccanismi di passaggio, il criterio più importante è l'esposizione delle variabili di chiamata per la modifica. Il vantaggio di passare un argomento `ByRef` è che la procedura può restituire un valore al codice chiamante tramite tale argomento. Il vantaggio di passare un argomento `ByVal` è che protegge una variabile dalla modifica dalla procedura.  
  
- **Prestazioni**. Sebbene il meccanismo di passaggio possa influire sulle prestazioni del codice, la differenza è in genere irrilevante. Un'eccezione è rappresentata da un tipo di valore passato `ByVal` . In questo caso, Visual Basic copia l'intero contenuto dei dati dell'argomento. Pertanto, per un tipo di valore di grandi dimensioni, ad esempio una struttura, può essere più efficiente passarlo `ByRef` .  
  
     Per i tipi di riferimento, viene copiato solo il puntatore ai dati (quattro byte su piattaforme a 32 bit, otto byte su piattaforme a 64 bit). Pertanto, è possibile passare argomenti di tipo `String` o `Object` per valore senza compromettere le prestazioni.  
  
## <a name="determination-of-the-passing-mechanism"></a>Determinazione del meccanismo di passaggio  
 La dichiarazione di routine specifica il meccanismo di passaggio per ogni parametro. Il codice chiamante non può eseguire l'override di un `ByVal` meccanismo.  
  
 Se un parametro viene dichiarato con `ByRef` , il codice chiamante può forzare il meccanismo a `ByVal` racchiudere il nome dell'argomento tra parentesi nella chiamata. Per altre informazioni, vedere [procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Quando passare un argomento per valore  
  
- Se l'elemento di codice chiamante sottostante l'argomento è un elemento non modificabile, dichiarare il parametro corrispondente [ByVal](../../../language-reference/modifiers/byval.md). Nessun codice può modificare il valore di un elemento non modificabile.  
  
- Se l'elemento sottostante è modificabile, ma non si desidera che la procedura sia in grado di modificarne il valore, dichiarare il parametro `ByVal` . Solo il codice chiamante può modificare il valore di un elemento modificabile passato per valore.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Quando passare un argomento per riferimento  
  
- Se la procedura ha la necessità di modificare l'elemento sottostante nel codice chiamante, dichiarare il parametro [ByRef](../../../language-reference/modifiers/byref.md)corrispondente.  
  
- Se l'esecuzione corretta del codice dipende dalla procedura che modifica l'elemento sottostante nel codice chiamante, dichiarare il parametro `ByRef` . Se viene passato in base al valore o se il codice chiamante esegue l'override del `ByRef` meccanismo di passaggio racchiudendo l'argomento tra parentesi, la chiamata alla procedura potrebbe produrre risultati imprevisti.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrato quando passare gli argomenti per valore e quando passarli per riferimento. La stored procedure `Calculate` include sia un `ByVal` parametro che un `ByRef` parametro. Dato un tasso di interesse, `rate` , e una somma di denaro, `debt` , l'attività della procedura consiste nel calcolare un nuovo valore per `debt` che è il risultato dell'applicazione del tasso di interesse al valore originale di `debt` . Poiché `debt` è un `ByRef` parametro, il nuovo totale viene riflesso nel valore dell'argomento nel codice chiamante che corrisponde a `debt` . Il parametro `rate` è un `ByVal` parametro perché `Calculate` non deve modificarne il valore.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
