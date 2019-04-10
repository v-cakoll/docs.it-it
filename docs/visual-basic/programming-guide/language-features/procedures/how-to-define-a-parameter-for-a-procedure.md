---
title: 'Procedura: Definire un parametro per una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 55925b0f007b1be2f5d46ffc0854601f483b2e2d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333834"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Procedura: Definire un parametro per una routine (Visual Basic)
Oggetto *parametro* consente di passare un valore per la procedura quando si chiama il codice chiama. Ciascun parametro viene dichiarato per una procedura simile a quello si dichiara una variabile, che specifica il nome e tipo di dati. Specificare inoltre il meccanismo di passaggio e indica se il parametro è facoltativo.  
  
 Per altre informazioni, vedere [parametri delle Procedure e argomenti](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Per definire un parametro di routine  
  
1. Nella dichiarazione di routine, aggiungere il nome del parametro all'elenco di parametri della stored procedure, separandolo dalle altri parametri con virgole.  
  
2. Decidere il tipo di dati del parametro.  
  
3. Seguire il nome del parametro con un `As` clausola per specificare il tipo di dati.  
  
4. Decidere il meccanismo di passaggio desiderato per il parametro. In genere si passa un parametro per valore, a meno che non si desidera essere in grado di modificare il relativo valore nel codice chiamante alla routine.  
  
5. Anteporre il nome del parametro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per specificare il meccanismo di passaggio. Per altre informazioni, vedere [differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6. Se il parametro è facoltativo, anteporre il meccanismo di passaggio [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) e seguire il tipo di dati del parametro con un segno di uguale (`=`) e un valore predefinito.  
  
     L'esempio seguente definisce la struttura di un `Sub` routine con tre parametri. Le prime due sono necessari e il terzo è facoltativo. Le dichiarazioni dei parametri sono separate nell'elenco dei parametri da una virgola.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     Il primo parametro accetta una `customer` oggetti, e `updateCustomer` possibile aggiornare direttamente la variabile passata a `c` perché l'argomento viene passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). La procedura non è possibile modificare i valori degli ultimi due argomenti in quanto vengono passati [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Se il codice chiamante non specifica un valore per il `level` parametro, Visual Basic lo imposta sul valore predefinito pari a 0.  
  
     Se il controllo del tipo passa ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) viene `Off`, il `As` clausola è facoltativa quando si definisce un parametro. Tuttavia, se un parametro viene utilizzato un `As` clausola, tutti gli elementi deve essere utilizzata. Se il tipo di opzione di controllo `On`, il `As` clausola è obbligatoria per ogni definizione di parametro.  
  
     Specifica dei tipi di dati per tutti gli elementi di programmazione è detta *tipizzazione forte*. Quando si imposta `Option Strict On`, Visual Basic applica la tipizzazione forte. Questa opzione è fortemente consigliata per i motivi seguenti:  
  
    -   Consente il supporto IntelliSense per le variabili e parametri. In questo modo è possibile visualizzare le relative proprietà e gli altri membri durante la digitazione del codice.  
  
    -   Consente al compilatore di eseguire il controllo dei tipi. Ciò risulta utile per intercettare le istruzioni possono avere esito negativo in fase di esecuzione a causa di errori, ad esempio overflow. Anche intercetta le chiamate ai metodi su oggetti che non li supportano.  
  
    -   Restituisce un'esecuzione più rapida del codice. Uno dei motivi è che se non si specifica un tipo di dati per un elemento di programmazione, il compilatore Visual Basic assegna il `Object` tipo. Il codice compilato potrebbe essere necessario convertire spostarsi tra `Object` e altri tipi di dati, riducendo le prestazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload delle routine](./procedure-overloading.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programmazione orientata agli oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
