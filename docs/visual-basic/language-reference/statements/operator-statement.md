---
title: Istruzione operator (Visual Basic)
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
ms.openlocfilehash: 69dea99cf71bd1e091116e54e244abfca291ffdb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170873"
---
# <a name="operator-statement"></a>Operator Statement
Dichiara il simbolo dell'operatore, gli operandi e il codice che definiscono una routine di operatore in una classe o struttura.  
  
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
 Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Obbligatorio. Indica che la routine di operatore abbia [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso.  
  
 `Overloads`  
 Facoltativo. Visualizzare [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Obbligatorio. Indica che la routine di operatore è un [condiviso](../../../visual-basic/language-reference/modifiers/shared.md) procedure.  
  
 `Shadows`  
 Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Obbligatorio per un operatore di conversione solo se si specifica `Narrowing`. Indica che la routine di operatore definisce una [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversione. In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".  
  
 `Narrowing`  
 Obbligatorio per un operatore di conversione solo se si specifica `Widening`. Indica che la routine di operatore definisce una [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversione. In questa pagina della Guida, vedere "Ampliamento e restrizione conversioni".  
  
 `operatorsymbol`  
 Obbligatorio. Il simbolo o l'identificatore dell'operatore che definisce questa routine di operatore.  
  
 `operand1`  
 Obbligatorio. Il nome e tipo di operando sinistro dell'operatore binario o l'unico operando dell'operatore unario (incluso un operatore di conversione).  
  
 `operand2`  
 Obbligatorio per gli operatori binari. Il nome e il tipo dell'operando destro dell'operatore binario.  
  
 `operand1` e `operand2` hanno la sintassi e le parti seguenti:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`ByVal`|Facoltativo, ma il meccanismo di passaggio deve essere [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|  
|`operandname`|Obbligatorio. Nome della variabile che rappresenta l'operando. Visualizzare [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Facoltativo, a meno che `Option Strict` è `On`. Tipo di dati di operando.|  
  
 `type`  
 Facoltativo, a meno che `Option Strict` è `On`. Restituisce il tipo di dati del valore della routine di operatore.  
  
 `statements`  
 Facoltativo. Blocco di istruzioni che esegue la routine di operatore.  
  
 `returnvalue`  
 Obbligatorio. Il valore che la routine di operatore restituisce al codice chiamante.  
  
 `End` `Operator`  
 Obbligatorio. Termina la definizione di questa routine di operatore.  
  
## <a name="remarks"></a>Note  
 È possibile usare `Operator` solo in una classe o struttura. Ciò significa che il *contesto della dichiarazione* per un operatore non può essere un file di origine, lo spazio dei nomi, modulo, interfaccia, routine o blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Tutti gli operatori devono essere `Public Shared`. Non è possibile specificare `ByRef`, `Optional`, o `ParamArray` per degli operandi.  
  
 È possibile usare il simbolo dell'operatore o l'identificatore per contenere un valore restituito. È necessario usare il `Return` istruzione che è necessario specificare un valore. Un numero qualsiasi di `Return` istruzioni possono trovarsi in qualsiasi punto della procedura.  
  
 La definizione di un operatore in questo modo viene definita *overload degli operatori*, se si utilizza il `Overloads` (parola chiave). La tabella seguente elenca gli operatori che è possibile definire.  
  
|Tipo|Operatori|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binario|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversione (unario)|`CType`|  
  
 Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.  
  
 Quando si definiscono `CType`, è necessario specificare `Widening` o `Narrowing`.  
  
## <a name="matched-pairs"></a>Coppie appaiate  
 È necessario definire determinati operatori come coppie associate. Se si definisce l'operatore di una coppia di questo tipo, è necessario definire anche a altro. Le coppie appaiate sono i seguenti:  
  
-   `=` e `<>`  
  
-   `>` e `<`  
  
-   `>=` e `<=`  
  
-   `IsTrue` e `IsFalse`  
  
## <a name="data-type-restrictions"></a>Restrizioni sul tipo di dati  
 Ogni operatore definito deve comportare la classe o struttura in cui si definiscono. Ciò significa che la classe o struttura deve essere visualizzato come il tipo di dati delle operazioni seguenti:  
  
-   L'operando dell'operatore unario.  
  
-   Almeno uno degli operandi di un operatore binario.  
  
-   L'operando o il tipo restituito di un operatore di conversione.  
  
 Alcuni operatori hanno dati aggiuntivi digitare restrizioni, come indicato di seguito:  
  
-   Se si definiscono i `IsTrue` e `IsFalse` operatori, devono entrambe restituire il `Boolean` tipo.  
  
-   Se si definisce la `<<` e `>>` operatori, devono entrambe specificare il `Integer` tipo per il `operandtype` di `operand2`.  
  
 Il tipo restituito non devono corrispondere al tipo degli operandi. Ad esempio, un operatore di confronto, ad esempio `=` oppure `<>` può restituire `Boolean` anche se nessuno dei due operandi `Boolean`.  
  
## <a name="logical-and-bitwise-operators"></a>Operatori logici e bit per bit  
 Il `And`, `Or`, `Not`, e `Xor` gli operatori possono eseguire operazioni logiche o bit per bit in Visual Basic. Tuttavia, se si definisce uno di questi operatori in una classe o struttura, è possibile definire solo l'operazione OR bit per bit.  
  
 Non è possibile definire le `AndAlso` operatore direttamente con un `Operator` istruzione. Tuttavia, è possibile usare `AndAlso` se si sono soddisfatte le condizioni seguenti:  
  
-   Sono stati definiti `And` sugli stessi tipi di operando da usare per `AndAlso`.  
  
-   La definizione di `And` restituisce lo stesso tipo della classe o struttura in cui si è definita.  
  
-   Sono stati definiti i `IsFalse` operatore nella classe o struttura in cui hanno definito `And`.  
  
 Analogamente, è possibile usare `OrElse` se è stata definita `Or` sugli operandi stesso, sono definiti con il tipo restituito della classe o struttura e si `IsTrue` nella classe o struttura.  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 Oggetto *conversione di ampliamento* avrà sempre esito positivo in fase di esecuzione, mentre un *conversione di narrowing* può non riuscire in fase di esecuzione. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Se si dichiara una routine di conversione sia `Widening`, il codice di procedure non deve generare gli eventuali errori. Ciò significa che:  
  
-   App deve sempre restituire un valore valido di tipo `type`.  
  
-   È necessario gestire tutte le eccezioni e altre condizioni di errore.  
  
-   L'applicazione deve gestire qualsiasi errore restituito da qualsiasi routine che chiama.  
  
 Se vi è una possibilità che una routine di conversione potrebbe avere esito negativo o che potrebbe causare un'eccezione non gestita, è necessario dichiararla come `Narrowing`.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come utilizzare il `Operator` istruzione per definire la struttura di una struttura che include routine di operatore per il `And`, `Or`, `IsFalse`, e `IsTrue` operatori. `And` e `Or` ognuno accettano due operandi di tipo `abc` e il tipo restituito `abc`. `IsFalse` e `IsTrue` ognuna delle quali accetta un singolo operando di tipo `abc` e restituire `Boolean`. Queste definizioni consentono al codice chiamante di usare `And`, `AndAlso`, `Or`, e `OrElse` con gli operandi di tipo `abc`.  
  
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
