---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: cb7fe7929e4b6e61ca3b39be5615e09182f2fe0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="operator-statement"></a>Operator Statement
Dichiara il simbolo di operatore, gli operandi e il codice che definiscono una routine di operatore in una classe o struttura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a>Parti  
 `attrlist`  
 Facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Obbligatorio. Indica che la routine di operatore esiste [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso.  
  
 `Overloads`  
 Facoltativo. Vedere [overload](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Obbligatorio. Indica che la routine di operatore è un [Shared](../../../visual-basic/language-reference/modifiers/shared.md) stored procedure.  
  
 `Shadows`  
 Facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Obbligatorio per un operatore di conversione, a meno che non si specifica `Narrowing`. Indica che questa routine di operatore definisce un [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversione. In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".  
  
 `Narrowing`  
 Obbligatorio per un operatore di conversione, a meno che non si specifica `Widening`. Indica che questa routine di operatore definisce un [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversione. In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".  
  
 `operatorsymbol`  
 Obbligatorio. Il simbolo o l'identificatore dell'operatore che definisce la routine di operatore.  
  
 `operand1`  
 Obbligatorio. Il nome e tipo di operando singolo di un operatore unario (incluso un operatore di conversione) o l'operando sinistro dell'operatore binario.  
  
 `operand2`  
 Obbligatorio per gli operatori binari. Nome e il tipo dell'operando di destra di un operatore binario.  
  
 `operand1` e `operand2` hanno la sintassi e le parti seguenti:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`ByVal`|Parametro facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|  
|`operandname`|Obbligatorio. Nome della variabile che rappresenta l'operando. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Facoltativo, a meno che `Option Strict` è `On`. Tipo di dati di questo tipo di operando.|  
  
 `type`  
 Facoltativo, a meno che `Option Strict` è `On`. Restituisce il tipo di dati del valore di routine di operatore.  
  
 `statements`  
 Facoltativo. Blocco di istruzioni che esegue la routine di operatore.  
  
 `returnvalue`  
 Obbligatorio. Il valore che la routine di operatore restituisce al codice chiamante.  
  
 `End` `Operator`  
 Obbligatorio. Termina la definizione di questa routine di operatore.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare `Operator` solo in una classe o struttura. Ciò significa che il *contesto della dichiarazione* per un operatore non può essere un file di origine, lo spazio dei nomi, modulo, interfaccia, routine o blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Tutti gli operatori devono essere `Public Shared`. Non è possibile specificare `ByRef`, `Optional`, o `ParamArray` per degli operandi.  
  
 È possibile utilizzare il simbolo dell'operatore o l'identificatore per contenere un valore restituito. È necessario utilizzare il `Return` istruzione e specificare un valore. Un numero qualsiasi di `Return` istruzioni possono trovarsi in qualsiasi punto della procedura.  
  
 Definendo un operatore in questo modo viene chiamato *l'overload degli operatori*, se si utilizza il `Overloads` (parola chiave). La tabella seguente elenca gli operatori che è possibile definire.  
  
|Tipo|Operatori|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binario|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversione (unario)|`CType`|  
  
 Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.  
  
 Quando si definisce `CType`, è necessario specificare `Widening` o `Narrowing`.  
  
## <a name="matched-pairs"></a>Coppie corrispondenti  
 È necessario definire alcuni operatori come coppie associate. Se si definisce un operatore di tale coppia, è necessario definire anche l'altro. Le coppie sono i seguenti:  
  
-   `=` e `<>`  
  
-   `>` e `<`  
  
-   `>=` e `<=`  
  
-   `IsTrue` e `IsFalse`  
  
## <a name="data-type-restrictions"></a>Restrizioni di tipi di dati  
 Ogni operatore definito deve coinvolgere classe o della struttura nella quale è definita. Ciò significa che la classe o struttura deve apparire come tipo di dati delle operazioni seguenti:  
  
-   L'operando dell'operatore unario.  
  
-   Almeno uno degli operandi di un operatore binario.  
  
-   L'operando o il tipo restituito di un operatore di conversione.  
  
 Alcuni operatori hanno dati aggiuntivi digitare restrizioni, come indicato di seguito:  
  
-   Se si definisce la `IsTrue` e `IsFalse` operatori, questi devono restituire entrambi il `Boolean` tipo.  
  
-   Se si definisce la `<<` e `>>` operatori, questi devono entrambi specificare il `Integer` tipo per il `operandtype` di `operand2`.  
  
 Il tipo restituito non deve corrispondere al tipo degli operandi. Ad esempio, un operatore di confronto, ad esempio `=` o `<>` può restituire `Boolean` anche se nessuno dei due operandi sono `Boolean`.  
  
## <a name="logical-and-bitwise-operators"></a>Operatori logici e bit per bit  
 Il `And`, `Or`, `Not`, e `Xor` operatori in Visual Basic possono eseguire operazioni logiche o bit per bit. Tuttavia, se si definisce uno di questi operatori in una classe o struttura, è possibile definire solo l'operazione bit per bit.  
  
 Non è possibile definire il `AndAlso` operatore direttamente con un `Operator` istruzione. Tuttavia, è possibile utilizzare `AndAlso` se si sono soddisfatte le condizioni seguenti:  
  
-   È stato definito `And` sugli stessi tipi di operando da utilizzare per `AndAlso`.  
  
-   La definizione di `And` restituisce lo stesso tipo della classe o struttura in cui sono definite.  
  
-   È stato definito il `IsFalse` operatore nella classe o struttura in cui sono definite `And`.  
  
 Analogamente, è possibile utilizzare `OrElse` se sono stati definiti `Or` negli stessi operandi sono definite con il tipo restituito della classe o struttura e si `IsTrue` nella classe o struttura.  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 Oggetto *conversione di ampliamento* ha sempre esito positivo in fase di esecuzione, mentre un *conversione di restrizione* può non riuscire in fase di esecuzione. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Se si dichiara una routine di conversione da `Widening`, il codice della routine non deve generare gli eventuali errori. Ciò significa che:  
  
-   Deve sempre restituire un valore valido di tipo `type`.  
  
-   È necessario gestire tutte le eccezioni e altre condizioni di errore.  
  
-   L'applicazione deve gestire qualsiasi errore restituito da qualsiasi routine che chiama.  
  
 Se vi è una possibilità che una routine di conversione potrebbe avere esito negativo o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice viene illustrato come utilizzare il `Operator` istruzione per definire la struttura di una struttura che include routine di operatore per il `And`, `Or`, `IsFalse`, e `IsTrue` operatori. `And` e `Or` accettano due operandi di tipo `abc` e il tipo restituito `abc`. `IsFalse` e `IsTrue` ognuna delle quali accetta un singolo operando di tipo `abc` e restituire `Boolean`. Queste definizioni consentono al codice chiamante di usare `And`, `AndAlso`, `Or`, e `OrElse` con gli operandi di tipo `abc`.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Procedura: Chiamare una routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [Procedura: Usare una classe che definisce gli operatori](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
