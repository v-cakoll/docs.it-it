---
title: + Operatore (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: 91806c204c313956b292eb9c9be078991f733b4e
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258098"
---
# <a name="-operator-visual-basic"></a>Operatore + (Visual Basic)
Somma due numeri o restituisce il valore positivo di un'espressione numerica. È anche utilizzabile per concatenare due espressioni di stringa.  
  
## <a name="syntax"></a>Sintassi  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`expression1`|Obbligatorio. Qualsiasi espressione numerica o stringa.|  
|`expression2`|Obbligatorio solo se il `+` operatore sta calcolando un valore negativo. Qualsiasi espressione numerica o stringa.|  
  
## <a name="result"></a>Risultato  
 Se `expression1` e `expression2` sono entrambi numerici, il risultato è la somma di operazioni aritmetica.  
  
 Se `expression2` è assente, la `+` operatore è la *unario* operatore di identità per il valore non modificato di un'espressione. In questo senso, l'operazione consiste nel mantenere il segno di `expression1`, in modo che il risultato sarà negativo se `expression1` è negativo.  
  
 Se `expression1` e `expression2` sono entrambe stringhe, il risultato è la concatenazione dei valori.  
  
 Se `expression1` e `expression2` sono di tipo misto, l'azione eseguita dipende dal tipo, i relativi contenuti e l'impostazione delle [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md). Per altre informazioni, vedere le tabelle in "Osservazioni".  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal`, e `String`.  
  
## <a name="remarks"></a>Note  
 In generale, `+` esegue l'addizione aritmetica quando possibile e le concatena solo quando entrambe le espressioni sono stringhe.  
  
 Se nessuna delle due espressioni sono un `Object`, Visual Basic esegue le azioni seguenti.  
  
|Tipi di dati delle espressioni|Azione dal compilatore|  
|---|---|  
|Entrambe le espressioni sono tipi di dati numerici (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, o `Double`)|Aggiungere. Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere le tabelle "Calcoli di interi" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Entrambe le espressioni sono di tipo `String`|Concatenare.|  
|Un'espressione è un tipo di dati numerici e l'altro è una stringa|Se `Option Strict` è `On`, quindi generare un errore del compilatore.<br /><br /> Se `Option Strict` viene `Off`, quindi convertire in modo implicito il `String` a `Double` e aggiungere.<br /><br /> Se il `String` non può essere convertito `Double`, quindi generano un <xref:System.InvalidCastException> eccezione.|  
|Un'espressione è un tipo di dati numerici e l'altro è [Nothing](../../../visual-basic/language-reference/nothing.md)|Aggiungere, con `Nothing` viene visualizzato il valore zero.|  
|Un'espressione è una stringa e l'altro è `Nothing`|La concatenazione, con `Nothing` valutati come "".|  
  
 Se un'espressione è un `Object` espressione, Visual Basic esegue le azioni seguenti.  
  
|Tipi di dati delle espressioni|Azione dal compilatore|  
|---|---|  
|`Object` l'espressione contiene un valore numerico e l'altro è un tipo di dati numerici|Se `Option Strict` è `On`, quindi generare un errore del compilatore.<br /><br /> Se `Option Strict` è `Off`, quindi aggiungere.|  
|`Object` l'espressione contiene un valore numerico e l'altra è di tipo `String`|Se `Option Strict` è `On`, quindi generare un errore del compilatore.<br /><br /> Se `Option Strict` viene `Off`, quindi convertire in modo implicito il `String` a `Double` e aggiungere.<br /><br /> Se il `String` non può essere convertito `Double`, quindi generano un <xref:System.InvalidCastException> eccezione.|  
|`Object` l'espressione contiene una stringa e l'altro è un tipo di dati numerici|Se `Option Strict` è `On`, quindi generare un errore del compilatore.<br /><br /> Se `Option Strict` viene `Off`, quindi convertire in modo implicito la stringa `Object` a `Double` e aggiungere.<br /><br /> Se la stringa `Object` non può essere convertito `Double`, quindi generano un <xref:System.InvalidCastException> eccezione.|  
|`Object` l'espressione contiene una stringa e l'altra è di tipo `String`|Se `Option Strict` è `On`, quindi generare un errore del compilatore.<br /><br /> Se `Option Strict` viene `Off`, quindi la conversione implicita `Object` a `String` e concatenati.|  
  
 Se entrambe le espressioni sono `Object` espressioni di Visual Basic esegue le azioni seguenti (`Option Strict Off` solo).  
  
|Tipi di dati delle espressioni|Azione dal compilatore|  
|---|---|  
|Entrambi `Object` espressioni contengono valori numerici|Aggiungere.|  
|Entrambi `Object` le espressioni sono di tipo `String`|Concatenare.|  
|Uno `Object` l'espressione contiene un valore numerico e l'altra contiene una stringa|Convertire in modo implicito la stringa `Object` a `Double` e aggiungere.<br /><br /> Se la stringa `Object` non può essere convertito in valore numerico, verrà generata un' <xref:System.InvalidCastException> eccezione.|  
  
 Se uno dei due `Object` espressione viene valutata [Nothing](../../../visual-basic/language-reference/nothing.md) o <xref:System.DBNull>, il `+` operatore lo considera come un `String` con un valore di "".  
  
> [!NOTE]
>  Quando si usa il `+` operatore, potrebbe non essere in grado di determinare se verrà eseguita la concatenazione di aggiunta o la stringa. Usare il `&` operatore per la concatenazione per evitare ambiguità e fornire codice autodocumentato.  
  
## <a name="overloading"></a>Overload  
 Il `+` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `+` operaa a add numeri. Se gli operandi sono entrambi numerici, Visual Basic calcola il risultato di operazioni aritmetico. Il risultato di operazioni aritmetico rappresenta la somma dei due operandi.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 È anche possibile usare il `+` operatore per concatenare le stringhe. Se gli operandi sono entrambe le stringhe, Visual Basic li concatena. Il risultato della concatenazione rappresenta una singola stringa costituita dal contenuto dei due operandi uno dopo l'altro.  
  
 Se gli operandi sono di tipo misto, il risultato dipende dall'impostazione delle [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md). L'esempio seguente illustra il risultato quando `Option Strict` è `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 L'esempio seguente illustra il risultato quando `Option Strict` è `Off`.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 Per evitare ambiguità, è consigliabile usare la `&` operatore anziché `+` per la concatenazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore &](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
