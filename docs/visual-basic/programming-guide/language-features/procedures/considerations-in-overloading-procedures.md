---
title: Considerazioni sull'overload di routine
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
ms.openlocfilehash: c4075c87df8b9daa56ca1d35e0d6661598895fdc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403369"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Considerazioni sull'overload di routine (Visual Basic)
Quando si esegue l'overload di una routine, è necessario utilizzare una *firma* diversa per ogni versione di overload. Ciò significa in genere che ogni versione deve specificare un elenco di parametri diverso. Per ulteriori informazioni, vedere "firma diversa" nell'argomento relativo all' [Overload delle procedure](./procedure-overloading.md).  
  
 È possibile eseguire l'overload di una `Function` routine con una `Sub` procedura e viceversa, purché dispongano di firme diverse. Due overload non possono differire solo per i quali hanno un valore restituito e l'altro no.  
  
 È possibile eseguire l'overload di una proprietà nello stesso modo in cui si esegue l'overload di una routine e con le stesse restrizioni. Tuttavia, non è possibile eseguire l'overload di una routine con una proprietà o viceversa.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternative alle versioni di overload  
 Talvolta si hanno alternative alle versioni di overload, in particolare quando la presenza di argomenti è facoltativa o il numero è variabile.  
  
 Tenere presente che gli argomenti facoltativi non sono necessariamente supportati da tutti i linguaggi e le matrici di parametri sono limitate ai Visual Basic. Se si sta scrivendo una procedura che è probabile che venga chiamata dal codice scritto in uno dei diversi linguaggi, le versioni di overload offrono la massima flessibilità.  
  
### <a name="overloads-and-optional-arguments"></a>Overload e argomenti facoltativi  
 Quando il codice chiamante può facoltativamente fornire o omettere uno o più argomenti, è possibile definire più versioni di overload o utilizzare parametri facoltativi.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando usare le versioni di overload  
 È possibile considerare la definizione di una serie di versioni di overload nei casi seguenti:  
  
- La logica nel codice della procedura è significativamente diversa a seconda che il codice chiamante fornisca o meno un argomento facoltativo.  
  
- Il codice della procedura non può verificare in modo affidabile se il codice chiamante ha fornito un argomento facoltativo. Questo è il caso, ad esempio, se non esiste un possibile candidato per un valore predefinito che non è previsto per il codice chiamante.  
  
#### <a name="when-to-use-optional-parameters"></a>Quando usare i parametri facoltativi  
 È possibile che si preferisca uno o più parametri facoltativi nei casi seguenti:  
  
- L'unica azione richiesta quando il codice chiamante non fornisce un argomento facoltativo consiste nell'impostare il parametro su un valore predefinito. In tal caso, il codice della procedura può essere meno complesso se si definisce una singola versione con uno o più `Optional` parametri.  
  
 Per ulteriori informazioni, vedere [parametri facoltativi](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Overload e ParamArray  
 Quando il codice chiamante può passare un numero variabile di argomenti, è possibile definire più versioni di overload o usare una matrice di parametri.  
  
#### <a name="when-to-use-overloaded-versions"></a>Quando usare le versioni di overload  
 È possibile considerare la definizione di una serie di versioni di overload nei casi seguenti:  
  
- Si sa che il codice chiamante non passa mai più di un numero ridotto di valori alla matrice di parametri.  
  
- La logica nel codice della procedura è significativamente diversa a seconda del numero di valori passati dal codice chiamante.  
  
- Il codice chiamante può passare valori di tipi di dati diversi.  
  
#### <a name="when-to-use-a-parameter-array"></a>Quando usare una matrice di parametri  
 È possibile servire in modo più efficiente da un `ParamArray` parametro nei casi seguenti:  
  
- Non è possibile stimare il numero di valori che il codice chiamante può passare alla matrice di parametri e potrebbe essere un numero elevato.  
  
- La logica della routine si presta a scorrere tutti i valori passati dal codice chiamante, eseguendo essenzialmente le stesse operazioni su ogni valore.  
  
 Per altre informazioni, vedere [matrici di parametri](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Overload impliciti per i parametri facoltativi  
 Una routine con un parametro [facoltativo](../../../language-reference/modifiers/optional.md) è equivalente a due procedure di overload, una con il parametro facoltativo e l'altra senza di essa. Non è possibile eseguire l'overload di questa procedura con un elenco di parametri corrispondente a uno di questi. Questa operazione viene illustrata nelle dichiarazioni seguenti.  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 Per una procedura con più di un parametro facoltativo, è disponibile un set di overload impliciti, arrivati da una logica simile a quella dell'esempio precedente.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Overload impliciti per un parametro ParamArray  
 Il compilatore considera una routine con un parametro [ParamArray](../../../language-reference/modifiers/paramarray.md) per avere un numero infinito di overload, che differiscono tra loro in quanto il codice chiamante passa alla matrice di parametri, come indicato di seguito:  
  
- Un overload per quando il codice chiamante non fornisce un argomento al parametro`ParamArray`  
  
- Un overload per quando il codice chiamante fornisce una matrice unidimensionale del tipo di `ParamArray` elemento  
  
- Per ogni intero positivo, un overload per quando il codice chiamante fornisce tale numero di argomenti, ognuno dei quali è il `ParamArray` tipo di elemento  
  
 Le dichiarazioni seguenti illustrano questi overload impliciti.  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Non è possibile eseguire l'overload di questa procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri. Tuttavia, è possibile usare le firme degli altri overload impliciti. Questa operazione viene illustrata nelle dichiarazioni seguenti.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programmazione non tipizzata come alternativa all'overload  
 Se si desidera consentire al codice chiamante di passare tipi di dati diversi a un parametro, un approccio alternativo è la programmazione senza tipi. È possibile impostare l'opzione di controllo del tipo su `Off` con l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md) o l'opzione del compilatore [-OptionStrict (](../../../reference/command-line-compiler/optionstrict.md) . Non è quindi necessario dichiarare il tipo di dati del parametro. Tuttavia, questo approccio presenta gli svantaggi seguenti rispetto all'overload:  
  
- La programmazione senza tipo produce codice di esecuzione meno efficiente.  
  
- La procedura deve verificare la presenza di tutti i tipi di dati previsti.  
  
- Il compilatore non può segnalare un errore se il codice chiamante passa un tipo di dati non supportato dalla procedura.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Risoluzione dell'overload](./overload-resolution.md)
- [Overload](../../../language-reference/modifiers/overloads.md)
