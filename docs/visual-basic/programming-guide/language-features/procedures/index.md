---
title: Procedure
ms.date: 04/28/2017
helpviewer_keywords:
- procedures [Visual Basic], structured code
- Visual Basic code, procedures
- procedures [Visual Basic], types of
- structured code [Visual Basic], procedures
- procedures
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
ms.openlocfilehash: c0d9921704570c6984b203817aed8f5546b2f936
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408790"
---
# <a name="procedures-in-visual-basic"></a>Routine in Visual Basic
Una *routine* è un blocco di istruzioni Visual Basic racchiuso tra un'istruzione di dichiarazione ( `Function` ,, `Sub` `Operator` , `Get` , `Set` ) e una `End` dichiarazione corrispondente. Tutte le istruzioni eseguibili in Visual Basic devono essere incluse in alcune procedure.  
  
## <a name="calling-a-procedure"></a>Chiamata di una routine  
 Una routine viene richiamata da altre parti del codice. Questa operazione è nota come *chiamata di routine*. Al termine dell'esecuzione della routine, il controllo viene restituito al codice che ha richiamato la routine, noto come *codice chiamante*. Il codice chiamante è un'istruzione o un'espressione all'interno di un'istruzione, che specifica la routine tramite nome e le trasferisce il controllo.  
  
## <a name="returning-from-a-procedure"></a>Termine di una routine  
 Una routine restituisce il controllo al codice chiamante al termine della sua esecuzione. A tale scopo, può utilizzare un'istruzione [return](../../../language-reference/statements/return-statement.md), l'istruzione [Exit](../../../language-reference/statements/exit-statement.md) appropriata per la routine o l'istruzione End dell'istruzione della [stored \<keyword> ](../../../language-reference/statements/end-keyword-statement.md) procedure. Il controllo passa quindi al codice chiamante che segue il punto della chiamata di routine.  
  
- Con un'istruzione `Return`, il controllo ritorna immediatamente al codice chiamante. Le istruzioni che seguono l'istruzione `Return` non vengono eseguite. Una routine può includere più di un'istruzione `Return`.  
  
- Con un'istruzione `Exit Sub` o `Exit Function`, il controllo ritorna immediatamente al codice chiamante. Le istruzioni che seguono l'istruzione `Exit` non vengono eseguite. Una routine può includere più di un'istruzione `Exit` ed è possibile combinare istruzioni `Return` e `Exit` nella stessa routine.  
  
- Se una routine non contiene istruzioni `Return` o `Exit`, termina con un'istruzione `End Sub` o `End Function`, `End Get` o `End Set` che segue l'ultima istruzione del corpo della routine. L'istruzione `End` restituisce il controllo immediatamente al codice chiamante. Una routine può contenere solo un'istruzione `End`.  
  
## <a name="parameters-and-arguments"></a>Parametri e argomenti  
 Nella maggior parte dei casi, una routine deve usare dati diversi ogni volta che viene chiamata. È possibile passare queste informazioni alla routine come parte della chiamata di routine. La routine definisce zero o più *parametri*, ognuno dei quali rappresenta un valore necessario da passare alla routine. A ogni parametro della definizione della routine corrisponde un *argomento* nella chiamata di routine. Un argomento rappresenta il valore passato al parametro corrispondente in una chiamata di routine specifica.  
  
## <a name="types-of-procedures"></a>Tipi di routine  
 Visual Basic usa diversi tipi di procedure:  
  
- Le [routine Sub](./sub-procedures.md) eseguono operazioni ma non restituiscono un valore al codice chiamante.  
  
- Le routine di gestione degli eventi sono routine `Sub` eseguite in risposta a un evento generato da un'azione utente o da un'occorrenza in un programma.  
  
- Le [routine Function](./function-procedures.md) restituiscono un valore al codice chiamante. Possono eseguire altre azioni prima della restituzione del valore.

    Alcune funzioni scritte in C# restituiscono un *valore di riferimento restituito*. I chiamanti delle routine Function possono modificare il valore restituito e questa modifica si riflette nello stato dell'oggetto chiamato. A partire da Visual Basic 2017, il codice di Visual Basic può usare valori di riferimento restituiti, anche se non può restituire un valore in base al riferimento. Per altre informazioni, vedere [Valori di riferimento restituiti](ref-return-values.md).
  
- Le [routine Property](./property-procedures.md) restituiscono e assegnano valori di proprietà su oggetti o moduli.  
  
- Le [routine Operator](./operator-procedures.md) definiscono il comportamento di un operatore standard quando uno o entrambi gli operandi sono una struttura o classe appena definita.  
  
- Le [routine generiche in Visual Basic](../data-types/generic-procedures.md) definiscono uno o più *parametri di tipo* oltre i relativi parametri normali, per cui il codice chiamante può passare tipi di dati specifici ogni volta che esegue una chiamata.  
  
## <a name="procedures-and-structured-code"></a>Routine e codice strutturato  
 Ogni riga di codice eseguibile nell'applicazione deve essere incluso all'interno di una routine, ad esempio `Main`, `calculate` o `Button1_Click`. Se si suddividono le routine di grandi dimensioni in piccole routine, l'applicazione risulta più leggibile.  
  
 Le routine sono utili per eseguire attività ripetute o condivise, ad esempio calcoli usati frequentemente, modifica di testo e di controllo e operazioni su database. È possibile chiamare una routine da diversi punti del codice, per cui è possibile usare routine come blocchi predefiniti per l'applicazione.  
  
 La strutturazione del codice con routine offre i vantaggi seguenti:  
  
- Le routine consentono di dividere i programmi in unità logiche distinte. È possibile eseguire più facilmente il debug di unità separate, piuttosto che eseguire il debug di un intero programma senza routine.  
  
- Dopo aver sviluppato le routine da usare in un programma, è possibile usarle in altri programmi, spesso senza modificarle o apportando modifiche minime. Questo consente di evitare la duplicazione del codice.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare una routine](./how-to-create-a-procedure.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
- [Generic Procedures in Visual Basic](../data-types/generic-procedures.md)
- [Oggetti e classi](../objects-and-classes/index.md)
