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
ms.openlocfilehash: 411959a7be92ea49a59558b508e992bfba8eff95
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344879"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Procedura: definire un parametro per una routine (Visual Basic)
Un *parametro* consente al codice chiamante di passare un valore alla routine quando lo chiama. Si dichiara ogni parametro per una routine nello stesso modo in cui si dichiara una variabile, specificandone il nome e il tipo di dati. Si specifica anche il meccanismo di passaggio e se il parametro è facoltativo.  
  
 Per ulteriori informazioni, vedere [parametri e argomenti delle procedure](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Per definire un parametro di routine  
  
1. Nella dichiarazione di routine aggiungere il nome del parametro all'elenco di parametri della stored procedure, separandoli da altri parametri per virgole.  
  
2. Decidere il tipo di dati del parametro.  
  
3. Per specificare il tipo di dati, seguire il nome del parametro con una clausola `As`.  
  
4. Decidere il meccanismo di passaggio desiderato per il parametro. In genere si passa un parametro per valore, a meno che non si desideri che la procedura sia in grado di modificare il valore nel codice chiamante.  
  
5. Anteporre [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) al nome del parametro per specificare il meccanismo di passaggio. Per ulteriori informazioni, vedere [differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6. Se il parametro è facoltativo, precedere il meccanismo di passaggio con [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) e seguire il tipo di dati del parametro con un segno di uguale (`=`) e un valore predefinito.  
  
     Nell'esempio seguente viene definita la struttura di una routine `Sub` con tre parametri. Le prime due sono obbligatorie e la terza è facoltativa. Le dichiarazioni di parametro sono separate da virgole nell'elenco di parametri.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     Il primo parametro accetta un oggetto `customer` e `updateCustomer` può aggiornare direttamente la variabile passata a `c` perché all'argomento viene passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). La stored procedure non può modificare i valori degli ultimi due argomenti perché vengono passati [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Se il codice chiamante non fornisce un valore per il parametro `level`, Visual Basic lo imposta sul valore predefinito 0.  
  
     Se l'opzione di controllo del tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `Off`, la clausola `As` è facoltativa quando si definisce un parametro. Tuttavia, se uno dei parametri usa una clausola `As`, è necessario utilizzarli tutti. Se l'opzione di controllo del tipo è `On`, la clausola `As` è obbligatoria per ogni definizione di parametro.  
  
     Specificare i tipi di dati per tutti gli elementi di programmazione è noto come tipizzazione *forte*. Quando si imposta `Option Strict On`, Visual Basic impone la tipizzazione forte. Questa operazione è fortemente consigliata per i motivi seguenti:  
  
    - Abilita il supporto IntelliSense per le variabili e i parametri. In questo modo è possibile visualizzare le relative proprietà e altri membri durante la digitazione nel codice.  
  
    - Consente al compilatore di eseguire il controllo dei tipi. Questo consente di intercettare le istruzioni che possono avere esito negativo in fase di esecuzione a causa di errori come l'overflow. Rileva inoltre le chiamate ai metodi su oggetti che non li supportano.  
  
    - Questo comporta un'esecuzione più rapida del codice. Un motivo è che se non si specifica un tipo di dati per un elemento di programmazione, il compilatore Visual Basic lo assegna al tipo di `Object`. Il codice compilato potrebbe dover eseguire la conversione tra `Object` e altri tipi di dati, riducendo così le prestazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
