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
ms.openlocfilehash: bcb99ef3845c1ce3998dc9dc8d9f1d335515c0a9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364370"
---
# <a name="overload-resolution-visual-basic"></a>Risoluzione dell'overload (Visual Basic)
Quando il compilatore di Visual Basic rileva una chiamata a una routine definita in diverse versioni di overload, il compilatore deve decidere quale degli overload chiamare. A tale scopo, eseguire la procedura seguente:  
  
1. **Accessibilità.** Elimina qualsiasi overload con un livello di accesso che impedisce al codice chiamante di chiamarlo.  
  
2. **Numero di parametri.** Elimina qualsiasi overload che definisce un numero diverso di parametri rispetto a quelli forniti nella chiamata.  
  
3. **Tipi di dati dei parametri.** Il compilatore fornisce i metodi di istanza preferenza sui metodi di estensione. Se viene trovato un metodo di istanza che richiede solo le conversioni verso un tipo di oggetto più ampio in modo che corrisponda alla chiamata di routine, tutti i metodi di estensione vengono eliminati e il compilatore continua con solo i candidati del metodo di istanza Se non viene trovato alcun metodo di questo tipo, continua con entrambi i metodi di istanza e di estensione.  
  
     In questo passaggio viene eliminato qualsiasi overload per il quale non è possibile convertire i tipi di dati degli argomenti chiamante nei tipi di parametro definiti nell'overload.  
  
4. **Conversioni verso un tipo di caratteri più piccolo.** Elimina tutti gli overload che richiedono una conversione verso un tipo di caratteri più piccolo dai tipi di argomento chiamante ai tipi di parametro definiti. Questo vale se l'opzione di controllo del tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) `On` è `Off` o.  
  
5. **Meno ampio.** Il compilatore considera gli overload rimanenti nelle coppie. Per ogni coppia, confronta i tipi di dati dei parametri definiti. Se i tipi in uno degli overload vengono tutti ampliati ai tipi corrispondenti nell'altro, il compilatore Elimina quest'ultimo. Ovvero, mantiene l'overload che richiede il minor numero di allargamento.  
  
6. **Singolo candidato.** Continua a considerare gli overload nelle coppie fino a quando non rimane un solo overload e risolve la chiamata a tale overload. Se il compilatore non è in grado di ridurre gli overload a un singolo candidato, viene generato un errore.  
  
 Nella figura seguente viene illustrato il processo che determina quale di un set di versioni di overload da chiamare.  
  
 ![Diagramma di flusso del processo di risoluzione degli overload](./media/overload-resolution/determine-overloaded-version.gif "Risoluzione tra versioni di overload")
  
 Nell'esempio seguente viene illustrato questo processo di risoluzione dell'overload.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 Nella prima chiamata, il compilatore elimina il primo overload perché il tipo del primo argomento ( `Short` ) si restringe al tipo del parametro corrispondente ( `Byte` ). Elimina quindi il terzo overload perché ogni tipo di argomento nel secondo overload ( `Short` e) viene `Single` ampliato al tipo corrispondente nel terzo overload ( `Integer` e `Single` ). Il secondo overload richiede un numero meno ampio, pertanto il compilatore lo utilizza per la chiamata.  
  
 Nella seconda chiamata, il compilatore non è in grado di eliminare gli overload sulla base della riduzione. Elimina il terzo overload per lo stesso motivo della prima chiamata, perché può chiamare il secondo overload con un minor numero di tipi di argomenti. Il compilatore, tuttavia, non è in grado di risolversi tra il primo e il secondo overload. Ogni ha un tipo di parametro definito che viene ampliato al tipo corrispondente nell'altro ( `Byte` a `Short` , ma `Single` a `Double` ). Il compilatore genera quindi un errore di risoluzione dell'overload.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Argomenti facoltativi e ParamArray di overload  
 Se due overload di una stored procedure hanno firme identiche, ad eccezione del fatto che l'ultimo parametro è dichiarato [facoltativo](../../../language-reference/modifiers/optional.md) in uno e [ParamArray](../../../language-reference/modifiers/paramarray.md) nell'altro, il compilatore risolve una chiamata a tale procedura come indicato di seguito:  
  
|Se la chiamata fornisce l'ultimo argomento come|Il compilatore risolve la chiamata all'overload che dichiara l'ultimo argomento come|  
|---|---|  
|Nessun valore (argomento omesso)|`Optional`|  
|Un singolo valore|`Optional`|  
|Due o più valori in un elenco delimitato da virgole|`ParamArray`|  
|Matrice di qualsiasi lunghezza (inclusa una matrice vuota)|`ParamArray`|  
  
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
- [Overload](../../../language-reference/modifiers/overloads.md)
- [Metodi di estensione](./extension-methods.md)
