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
ms.openlocfilehash: e1768d0ac03cb6730c4337d7476ae163e75adfd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Considerazioni sull'overload di routine (Visual Basic)
Quando si esegue l'overload di una stored procedure, è necessario utilizzare un altro *firma* per ogni versione di overload. In genere significa che ogni versione è necessario specificare un elenco di parametri diversi. Per ulteriori informazioni, vedere "Firma diversa" in [overload di routine](./procedure-overloading.md).  
  
 È possibile eseguire l'overload un `Function` routine con un `Sub` procedure e viceversa, purché siano firme diverse. Due overload non possono differire solo nel fatto che uno è un valore restituito e l'altro non lo fa.  
  
 È possibile eseguire l'overload una proprietà allo stesso modo, si esegue l'overload di una stored procedure e con le stesse restrizioni. Tuttavia, è possibile eseguire l'overload di una stored procedure con una proprietà o viceversa.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternative per le versioni di overload  
 Talvolta è alternative alle versioni di overload, in particolare quando la presenza di argomenti è facoltativa o il relativo numero è variabile.  
  
 Tenere presente che gli argomenti facoltativi non sono necessariamente supportati da tutti i linguaggi e le matrici di parametri sono limitate a Visual Basic. Se si sta scrivendo una routine che possa essere chiamato dal codice scritto in una delle diverse lingue, la massima flessibilità offerta di versioni di overload.  
  
### <a name="overloads-and-optional-arguments"></a>Gli overload e gli argomenti facoltativi  
 Quando il codice chiamante può facoltativamente specificare o omettere uno o più argomenti, è possibile definire più versioni di overload o utilizzare parametri facoltativi.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando utilizzare le versioni di overload  
 È possibile definire una serie di versioni di overload nei casi seguenti:  
  
-   La logica nel codice della procedura è notevolmente diversa a seconda se il codice chiamante fornisce un argomento facoltativo o non.  
  
-   Il codice della routine non può verificare in modo affidabile se il codice chiamante ha fornito un argomento facoltativo. Ciò avviene, ad esempio, se non è possibile prevedere alcun valore predefinito che il codice chiamante potrebbe non essere previsto per fornire.  
  
#### <a name="when-to-use-optional-parameters"></a>Quando utilizzare parametri facoltativi  
 È possibile scegliere uno o più parametri facoltativi nei casi seguenti:  
  
-   L'azione necessaria solo quando il codice chiamante non fornisce un argomento facoltativo consiste nell'impostare il parametro su un valore predefinito. In tal caso, il codice di stored procedure può essere meno complesso se si definisce una singola versione con uno o più `Optional` parametri.  
  
 Per ulteriori informazioni, vedere [parametri facoltativi](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Overload e ParamArray  
 Quando il codice chiamante può passare un numero variabile di argomenti, è possibile definire più versioni di overload o utilizzare una matrice di parametri.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando utilizzare le versioni di overload  
 È possibile definire una serie di versioni di overload nei casi seguenti:  
  
-   Si sa che il codice chiamante passa sempre un numero ridotto di valori alla matrice di parametri.  
  
-   La logica nel codice della procedura è notevolmente diversa a seconda di quanti valori passa al codice chiamante.  
  
-   Il codice chiamante può passare i valori di tipi di dati diversi.  
  
#### <a name="when-to-use-a-parameter-array"></a>Quando utilizzare una matrice di parametri  
 Consigliabile un `ParamArray` parametro nei seguenti casi:  
  
-   Non sono in grado di stimare quanti valori il codice chiamante può passare alla matrice di parametri e potrebbe essere un numero elevato.  
  
-   La logica della routine si presta a un'iterazione attraverso tutti i valori passa al codice chiamante, essenzialmente le stesse operazioni in ogni valore di esecuzione.  
  
 Per ulteriori informazioni, vedere [matrici di parametro](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Overload impliciti per i parametri facoltativi  
 Una routine con un [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametro è equivalente a due routine di overload, uno con il parametro facoltativo e uno senza di esso. È possibile eseguire l'overload di una routine con un elenco di parametri corrispondente a uno di questi. Le seguenti dichiarazioni di illustrare questo concetto.  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Per una routine con più di un parametro facoltativo, è un set di overload impliciti, una logica simile a quello nell'esempio precedente.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Overload impliciti per un parametro ParamArray  
 Il compilatore considera una routine con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro venga specificato un numero infinito di overload, che differiscono tra loro per ciò che il codice chiamante passa alla matrice di parametri, come indicato di seguito:  
  
-   Quando il codice chiamante non fornisce un argomento a un overload di `ParamArray`  
  
-   Quando il codice chiamante fornisce una matrice unidimensionale di un overload di `ParamArray` tipo di elemento  
  
-   Per ogni integer positivo, un overload quando il codice chiamante fornisce tale numero di argomenti, ognuno del `ParamArray` tipo di elemento  
  
 Le dichiarazioni seguenti illustrano questi overload impliciti.  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 È possibile eseguire l'overload di una procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri. Tuttavia, è possibile utilizzare le firme di overload impliciti. Le seguenti dichiarazioni di illustrare questo concetto.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programmazione senza tipi come alternativa all'overload  
 Se si desidera consentire al codice chiamante passare i tipi di dati diversi a un parametro, un approccio alternativo è costituito dalla programmazione. È possibile impostare il tipo di controllo passa a `Off` con il [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) l'opzione del compilatore. Quindi non è necessario dichiarare il tipo di dati del parametro. Tuttavia, questo approccio presenta i seguenti svantaggi rispetto all'overload:  
  
-   Programmazione senza tipi produce codice meno efficiente di esecuzione.  
  
-   La procedura è necessario testare per ogni tipo di dati che anticipa il passaggio.  
  
-   Il compilatore non è possibile segnalare un errore se il codice chiamante passa un tipo di dati che non supporta la procedura.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)  
 [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)  
 [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Risoluzione dell'overload](./overload-resolution.md)  
 [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)
