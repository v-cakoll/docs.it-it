---
title: Considerazioni sull'overload di routine (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: f14cc28960af28530bda9a78c1309dea10c18b8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864351"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Considerazioni sull'overload di routine (Visual Basic)
Quando si esegue l'overload di una procedura, è necessario utilizzare un diverso *firma* per ogni versione di overload. Ciò significa in genere che ogni versione è necessario specificare un elenco di parametri diverso. Per altre informazioni, vedere "Firma diversa" nella [overload della routine](./procedure-overloading.md).  
  
 È possibile eseguire l'overload una `Function` routine con un `Sub` procedure e viceversa, purché siano firme diverse. Due overload non possono distinguersi solo in quanto uno ha un valore restituito e l'altro no.  
  
 È possibile eseguire l'overload una proprietà allo stesso modo si esegue l'overload di una stored procedure e con le stesse restrizioni. Tuttavia, è possibile eseguire l'overload di una procedura con una proprietà o viceversa.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternative per le versioni di overload  
 Alternative per le versioni di overload, è talvolta necessario in particolare durante la presenza di argomenti è facoltativa o il relativo numero è variabile.  
  
 Tenere presente che gli argomenti facoltativi non sono necessariamente supportati da tutti i linguaggi e le matrici di parametri sono limitate a Visual Basic. Se si sta scrivendo una routine che probabilmente continuerà a essere chiamato dal codice scritto in uno dei diversi linguaggi diversi, sottoposti a overload versioni offerta la massima flessibilità.  
  
### <a name="overloads-and-optional-arguments"></a>Argomenti facoltativi e overload  
 Quando il codice chiamante può facoltativamente specificare o omettere uno o più argomenti, è possibile definire più versioni di overload o usare i parametri facoltativi.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando usare le versioni di overload  
 È possibile definire una serie di versioni di overload nei casi seguenti:  
  
-   La logica nel codice della procedura è significativamente diversa a seconda del fatto che il codice chiamante fornisce un argomento facoltativo o No.  
  
-   Il codice della routine in modo affidabile non è possibile verificare se il codice chiamante ha fornito un argomento facoltativo. Ciò avviene, ad esempio, se non è disponibile alcun possibile candidato per un valore predefinito che il codice chiamante non prevedibili per fornire.  
  
#### <a name="when-to-use-optional-parameters"></a>Quando usare i parametri facoltativi  
 Potrebbe essere preferibile una o più parametri facoltativi nei casi seguenti:  
  
-   L'azione necessaria solo quando il codice chiamante non fornisce un argomento facoltativo consiste nell'impostare il parametro su un valore predefinito. In tal caso, il codice della routine può essere meno complesso se si definisce una singola versione con uno o più `Optional` parametri.  
  
 Per altre informazioni, vedere [parametri facoltativi](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Gli overload e i parametri ParamArray  
 Quando il codice chiamante può passare un numero variabile di argomenti, è possibile definire più versioni di overload o usare una matrice di parametri.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando usare le versioni di overload  
 È possibile definire una serie di versioni di overload nei casi seguenti:  
  
-   Sai che il codice chiamante non passa mai più di un numero ridotto di valori nella matrice di parametri.  
  
-   La logica nel codice della procedura è significativamente diversa a seconda di quanti valori passa al codice chiamante.  
  
-   Il codice chiamante può passare i valori dei tipi di dati diversi.  
  
#### <a name="when-to-use-a-parameter-array"></a>Quando usare una matrice di parametri  
 Meglio vengono gestite da un `ParamArray` parametro nei casi seguenti:  
  
-   Non si è in grado di stimare quanti valori il codice chiamante può passare alla matrice di parametri e potrebbe essere un numero elevato.  
  
-   La logica della routine si presta a scorrere tutti i valori passati al codice chiamante, esegue essenzialmente le stesse operazioni in ogni valore.  
  
 Per altre informazioni, vedere [matrici di parametri](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Overload impliciti per i parametri facoltativi  
 Una procedura con un [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametro equivale al due routine di overload, uno con il parametro facoltativo e l'altra senza. È possibile eseguire l'overload di una routine con un elenco di parametri corrispondenti a uno di questi. Le seguenti dichiarazioni di illustrare questo concetto.  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 Per una procedura con più di un parametro facoltativo, è presente un set di overload impliciti, una logica simile a quello nell'esempio precedente.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Overload impliciti per un parametro ParamArray  
 Il compilatore prende in considerazione una procedura con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro in modo che un numero infinito di overload, che si differenziano tra loro in ciò che il codice chiamante passa alla matrice di parametri, come indicato di seguito:  
  
-   Uno degli overload quando il codice chiamante non fornisce un argomento per il `ParamArray`  
  
-   Uno degli overload quando il codice chiamante fornisce una matrice unidimensionale del `ParamArray` tipo di elemento  
  
-   Per ogni numero intero positivo, un overload quando il codice chiamante fornisce tale numero di argomenti, ognuno del `ParamArray` tipo di elemento  
  
 Le dichiarazioni seguenti illustrano questi overload impliciti.  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 È possibile eseguire l'overload di una procedura con un elenco di parametri che accetta una matrice unidimensionale la matrice di parametri. Tuttavia, è possibile utilizzare le firme degli altri overload impliciti. Le seguenti dichiarazioni di illustrare questo concetto.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>La programmazione alternativa per l'overload  
 Se si desidera il codice chiamante può passare diversi tipi di dati a un parametro, un approccio alternativo è costituito dalla programmazione. È possibile impostare il tipo di opzione di controllo `Off` con il [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o il [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) opzione del compilatore. Non è quindi necessario dichiarare il tipo di dati del parametro. Tuttavia, questo approccio presenta i seguenti svantaggi rispetto all'overload:  
  
-   La programmazione produce codice di esecuzione meno efficiente.  
  
-   La procedura è necessario testare ogni tipo di dati che anticipa il passaggio.  
  
-   Il compilatore non è possibile segnalare un errore se il codice chiamante passa un tipo di dati che non supporta la routine.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Risoluzione dell'overload](./overload-resolution.md)
- [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)
