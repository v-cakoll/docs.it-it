---
title: + Operatore
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
ms.openlocfilehash: 6ae3feae6ecb63b82426f2aa69359625bbffcec8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372116"
---
# <a name="-operator-visual-basic"></a>Operatore + (Visual Basic)
Somma due numeri o restituisce il valore positivo di un'espressione numerica. Può essere usato anche per concatenare due espressioni stringa.  
  
## <a name="syntax"></a>Sintassi  
  
```vb
expression1 + expression2
```
  
Oppure

```vb  
+expression1  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`expression1`|Obbligatorio. Qualsiasi espressione numerica o stringa.|  
|`expression2`|Obbligatorio a meno che l' `+` operatore non calcoli un valore negativo. Qualsiasi espressione numerica o stringa.|  
  
## <a name="result"></a>Risultato  
 Se `expression1` e `expression2` sono entrambi numerici, il risultato è la somma aritmetica.  
  
 Se `expression2` è assente, l' `+` operatore è l'operatore di identità *unario* per il valore non modificato di un'espressione. In questo senso, l'operazione consiste nel mantenere il segno di `expression1` , pertanto il risultato è negativo se `expression1` è negativo.  
  
 Se `expression1` e `expression2` sono entrambe stringhe, il risultato è la concatenazione dei relativi valori.  
  
 Se `expression1` e `expression2` sono di tipi misti, l'azione eseguita dipende dai relativi tipi, dal relativo contenuto e dall'impostazione dell' [istruzione Option Strict](../statements/option-strict-statement.md). Per ulteriori informazioni, vedere le tabelle in "osservazioni".  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal` , e `String` .  
  
## <a name="remarks"></a>Commenti  
 In generale, `+` se possibile, esegue l'aggiunta aritmetica e concatena solo quando entrambe le espressioni sono stringhe.  
  
 Se nessuna delle due espressioni è un `Object` , Visual Basic esegue le azioni seguenti.  
  
|Tipi di dati delle espressioni|Azione per compilatore|  
|---|---|  
|Entrambe le espressioni sono tipi di dati numerici ( `SByte` ,, `Byte` `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` o `Double` )|Aggiungi. Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2` . Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).|  
|Entrambe le espressioni sono di tipo`String`|Concatenare.|  
|Un'espressione è un tipo di dati numerico e l'altra è una stringa|Se `Option Strict` è `On` , genera un errore del compilatore.<br /><br /> Se `Option Strict` è `Off` , convertire in modo implicito `String` in `Double` e aggiungere.<br /><br /> Se `String` non può essere convertito in `Double` , viene generata un' <xref:System.InvalidCastException> eccezione.|  
|Un'espressione è un tipo di dati numerico e l'altra [non è nulla](../nothing.md)|Aggiungere, con `Nothing` valore pari a zero.|  
|Un'espressione è una stringa e l'altra è`Nothing`|Concatenate, con `Nothing` valore "".|  
  
 Se un'espressione è un' `Object` espressione, Visual Basic esegue le azioni seguenti.  
  
|Tipi di dati delle espressioni|Azione per compilatore|  
|---|---|  
|`Object`l'espressione include un valore numerico e l'altro è un tipo di dati numerico|Se `Option Strict` è `On` , genera un errore del compilatore.<br /><br /> Se `Option Strict` è `Off` , aggiungere.|  
|`Object`l'espressione include un valore numerico e l'altro è di tipo`String`|Se `Option Strict` è `On` , genera un errore del compilatore.<br /><br /> Se `Option Strict` è `Off` , convertire in modo implicito `String` in `Double` e aggiungere.<br /><br /> Se `String` non può essere convertito in `Double` , viene generata un' <xref:System.InvalidCastException> eccezione.|  
|`Object`l'espressione include una stringa e l'altra è un tipo di dati numerico|Se `Option Strict` è `On` , genera un errore del compilatore.<br /><br /> Se `Option Strict` è `Off` , convertire in modo implicito la stringa `Object` in `Double` e aggiungere.<br /><br /> Se la stringa `Object` non può essere convertita in `Double` , viene generata un' <xref:System.InvalidCastException> eccezione.|  
|`Object`l'espressione include una stringa e l'altra è di tipo`String`|Se `Option Strict` è `On` , genera un errore del compilatore.<br /><br /> Se `Option Strict` è `Off` , convertire in modo implicito `Object` in `String` e concatenare.|  
  
 Se entrambe le espressioni sono `Object` espressioni, Visual Basic esegue le azioni seguenti ( `Option Strict Off` solo).  
  
|Tipi di dati delle espressioni|Azione per compilatore|  
|---|---|  
|Entrambe le `Object` espressioni contengono valori numerici|Aggiungi.|  
|Entrambe `Object` le espressioni sono di tipo`String`|Concatenare.|  
|Un' `Object` espressione include un valore numerico e l'altra include una stringa|Converte in modo implicito la stringa `Object` in `Double` e Aggiungi.<br /><br /> Se la stringa `Object` non può essere convertita in un valore numerico, viene generata un' <xref:System.InvalidCastException> eccezione.|  
  
 Se una `Object` delle due espressioni restituisce [Nothing](../nothing.md) o <xref:System.DBNull> , l' `+` operatore lo considera come `String` con un valore di "".  
  
> [!NOTE]
> Quando si utilizza l' `+` operatore, potrebbe non essere possibile determinare se si verificherà l'aggiunta o la concatenazione di stringhe. Usare l' `&` operatore per la concatenazione per eliminare l'ambiguità e per fornire codice autodocumentato.  
  
## <a name="overloading"></a>Overload  
 L' `+` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `+` operatore per aggiungere numeri. Se gli operandi sono entrambi numerici, Visual Basic calcola il risultato aritmetico. Il risultato aritmetico rappresenta la somma dei due operandi.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 È anche possibile usare l' `+` operatore per concatenare le stringhe. Se gli operandi sono entrambe stringhe, Visual Basic li concatena. Il risultato della concatenazione rappresenta una singola stringa costituita dal contenuto dei due operandi uno dopo l'altro.  
  
 Se gli operandi sono di tipo misto, il risultato dipende dall'impostazione dell' [istruzione Option Strict](../statements/option-strict-statement.md). Nell'esempio seguente viene illustrato il risultato quando `Option Strict` è `On` .  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 Nell'esempio seguente viene illustrato il risultato quando `Option Strict` è `Off` .  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 Per eliminare l'ambiguità, è consigliabile utilizzare l' `&` operatore anziché `+` per la concatenazione.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore&](concatenation-operator.md)
- [Operatori di concatenazione](concatenation-operators.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Operatori aritmetici in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Option Strict Statement](../statements/option-strict-statement.md)
