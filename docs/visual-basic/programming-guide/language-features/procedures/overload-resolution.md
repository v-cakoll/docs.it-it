---
title: Overload Resolution
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 84d52bbbfb34c2e5d67ed6a1810ab3e32fafda22
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266872"
---
# <a name="overload-resolution-visual-basic"></a>Risoluzione dell'overload (Visual Basic)
Quando il compilatore Visual Basic rileva una chiamata a una routine definita in diverse versioni di overload, il compilatore deve decidere quale degli overload chiamare. A tale scopo, eseguire le seguenti operazioni:  
  
1. **Accessibilità.** Elimina qualsiasi overload con un livello di accesso che impedisce al codice chiamante di chiamarlo.  
  
2. **Numero di parametri.** Elimina qualsiasi overload che definisce un numero di parametri diverso da quello fornito nella chiamata.  
  
3. **Tipi di dati dei parametri.** Il compilatore fornisce ai metodi di istanza la preferenza rispetto ai metodi di estensione. Se viene trovato un metodo di istanza che richiede solo conversioni di ampliamento in modo che corrispondano alla chiamata di routine, tutti i metodi di estensione vengono eliminati e il compilatore continua con solo i candidati al metodo di istanza. Se tale metodo di istanza non viene trovato, continua con i metodi di istanza e di estensione.  
  
     In questo passaggio viene eliminato qualsiasi overload per il quale i tipi di dati degli argomenti chiamanti non possono essere convertiti nei tipi di parametro definiti nell'overload.  
  
4. **Conversioni di restrizione.** Elimina qualsiasi overload che richiede una conversione verso un tipo di dati più piccolo dai tipi di argomento chiamante ai tipi di parametro definiti. Ciò è vero se l'opzione di `On` `Off`controllo dei tipi ( Option[Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è o .  
  
5. **Almeno allargamento.** Il compilatore considera gli overload rimanenti in coppie. Per ogni coppia, confronta i tipi di dati dei parametri definiti. Se i tipi in uno degli overload si ampliano tutti ai tipi corrispondenti nell'altro, il compilatore elimina quest'ultimo. Ovvero, mantiene l'overload che richiede la minima quantità di ampliamento.  
  
6. **Candidato singolo.** Continua a considerare gli overload in coppie fino a quando non rimane un solo overload e risolve la chiamata a tale overload. Se il compilatore non è in grado di ridurre gli overload a un singolo candidato, viene generato un errore.  
  
 Nella figura seguente viene illustrato il processo che determina quale di un set di versioni di overload da chiamare.  
  
 ![Diagramma di flusso del processo di risoluzione degli overload](./media/overload-resolution/determine-overloaded-version.gif "Risoluzione tra versioni di overloadResolving among overloaded versions")
  
 Nell'esempio seguente viene illustrato questo processo di risoluzione dell'overload.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 Nella prima chiamata, il compilatore elimina il primo overload`Short`perché il tipo del primo argomento`Byte`( ) si restringe al tipo del parametro corrispondente ( ). Viene quindi eliminato il terzo overload perché ogni`Short` tipo `Single`di argomento nel secondo overload (`Integer` `Single`e ) si allarga al tipo corrispondente nel terzo overload ( e ). Il secondo overload richiede meno ampliamento, pertanto il compilatore lo utilizza per la chiamata.  
  
 Nella seconda chiamata, il compilatore non può eliminare nessuno degli overload in base al narrowing. Elimina il terzo overload per lo stesso motivo della prima chiamata, perché può chiamare il secondo overload con meno ampliamento dei tipi di argomento. Tuttavia, il compilatore non può risolvere tra il primo e il secondo overload. Ognuno ha un tipo di parametro definito che`Byte` `Short`si `Single` allarga al tipo corrispondente nell'altro ( a , ma a `Double`). Il compilatore genera pertanto un errore di risoluzione dell'overload.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Argomenti facoltativi e paramArray di overloadOverloaded Optional and ParamArray Arguments  
 Se due overload di una routine hanno firme identiche, ad eccezione del fatto che l'ultimo parametro viene dichiarato [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in uno e [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) nell'altro, il compilatore risolve una chiamata a tale routine come segue:  
  
|Se la chiamata fornisce l'ultimo argomento come|Il compilatore risolve la chiamata all'overload dichiarando l'ultimo argomento come|  
|---|---|  
|Nessun valore (argomento omesso)|`Optional`|  
|Un singolo valore|`Optional`|  
|Due o più valori in un elenco separato da virgole|`ParamArray`|  
|Una matrice di qualsiasi lunghezza (inclusa una matrice vuota)|`ParamArray`|  
  
## <a name="see-also"></a>Vedere anche

- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Metodi di estensione](./extension-methods.md)
