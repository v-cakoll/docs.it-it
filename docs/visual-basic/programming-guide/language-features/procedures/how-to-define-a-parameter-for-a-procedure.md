---
title: 'Procedura: definire un parametro per una routine'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: e703346113348556b8a3ea41a7934a55a8008522
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388076"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Procedura: definire un parametro per una routine (Visual Basic)
Un *parametro* consente al codice chiamante di passare un valore alla routine quando lo chiama. Si dichiara ogni parametro per una routine nello stesso modo in cui si dichiara una variabile, specificandone il nome e il tipo di dati. Si specifica anche il meccanismo di passaggio e se il parametro è facoltativo.  
  
 Per ulteriori informazioni, vedere [parametri e argomenti delle procedure](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Per definire un parametro di routine  
  
1. Nella dichiarazione di routine aggiungere il nome del parametro all'elenco di parametri della stored procedure, separandoli da altri parametri per virgole.  
  
2. Decidere il tipo di dati del parametro.  
  
3. Seguire il nome del parametro con una `As` clausola per specificare il tipo di dati.  
  
4. Decidere il meccanismo di passaggio desiderato per il parametro. In genere si passa un parametro per valore, a meno che non si desideri che la procedura sia in grado di modificare il valore nel codice chiamante.  
  
5. Anteporre [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) al nome del parametro per specificare il meccanismo di passaggio. Per ulteriori informazioni, vedere [differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6. Se il parametro è facoltativo, precedere il meccanismo di passaggio con [facoltativo](../../../language-reference/modifiers/optional.md) e seguire il tipo di dati del parametro con un segno di uguale ( `=` ) e un valore predefinito.  
  
     Nell'esempio seguente viene definita la struttura di una `Sub` routine con tre parametri. Le prime due sono obbligatorie e la terza è facoltativa. Le dichiarazioni di parametro sono separate da virgole nell'elenco di parametri.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     Il primo parametro accetta un `customer` oggetto e `updateCustomer` può aggiornare direttamente la variabile passata a `c` perché all'argomento viene passato [ByRef](../../../language-reference/modifiers/byref.md). La stored procedure non può modificare i valori degli ultimi due argomenti perché vengono passati [ByVal](../../../language-reference/modifiers/byval.md).  
  
     Se il codice chiamante non fornisce un valore per il `level` parametro, Visual Basic lo imposta sul valore predefinito 0.  
  
     Se l'opzione di controllo del tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) è `Off` , la `As` clausola è facoltativa quando si definisce un parametro. Tuttavia, se uno dei parametri usa una `As` clausola, è necessario utilizzarli tutti. Se l'opzione di controllo del tipo è `On` , la `As` clausola è obbligatoria per ogni definizione di parametro.  
  
     Specificare i tipi di dati per tutti gli elementi di programmazione è noto come tipizzazione *forte*. Quando si imposta `Option Strict On` , Visual Basic impone la tipizzazione forte. Questa operazione è fortemente consigliata per i motivi seguenti:  
  
    - Abilita il supporto IntelliSense per le variabili e i parametri. In questo modo è possibile visualizzare le relative proprietà e altri membri durante la digitazione nel codice.  
  
    - Consente al compilatore di eseguire il controllo dei tipi. Questo consente di intercettare le istruzioni che possono avere esito negativo in fase di esecuzione a causa di errori come l'overflow. Rileva inoltre le chiamate ai metodi su oggetti che non li supportano.  
  
    - Questo comporta un'esecuzione più rapida del codice. Un motivo è che se non si specifica un tipo di dati per un elemento di programmazione, il compilatore Visual Basic lo assegna al `Object` tipo. Il codice compilato potrebbe dover eseguire la conversione tra `Object` e altri tipi di dati, riducendo così le prestazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
- [Oggetti e classi](../objects-and-classes/index.md)
- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
