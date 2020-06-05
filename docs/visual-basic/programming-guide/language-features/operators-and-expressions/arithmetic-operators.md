---
title: Operatori aritmetici
ms.date: 07/20/2015
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
ms.openlocfilehash: d5f79f3e45fc887dcb32c959f04703253ade198c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389036"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Operatori aritmetici in Visual Basic
Gli operatori aritmetici vengono utilizzati per eseguire molte delle operazioni aritmetiche note che interessano il calcolo dei valori numerici rappresentati da valori letterali, variabili, altre espressioni, chiamate di funzioni e proprietà e costanti. Gli operatori aritmetici, inoltre, sono gli operatori di spostamento di bit, che agiscono a livello dei singoli bit degli operandi e spostano gli schemi di bit a sinistra o a destra.  
  
## <a name="arithmetic-operations"></a>Operazioni aritmetiche  
 È possibile aggiungere due valori in un'espressione insieme all' [operatore +](../../../language-reference/operators/addition-operator.md)oppure sottrarne uno da un altro con l' [operatore-(Visual Basic)](../../../language-reference/operators/subtraction-operator.md), come illustrato nell'esempio riportato di seguito.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 La negazione usa anche l' [operatore-(Visual Basic)](../../../language-reference/operators/subtraction-operator.md), ma con un solo operando, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 La moltiplicazione e la divisione utilizzano rispettivamente l'operatore [*](../../../language-reference/operators/multiplication-operator.md) e [/(Visual Basic)](../../../language-reference/operators/floating-point-division-operator.md), come illustrato nell'esempio riportato di seguito.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 L'elevamento a potenza usa l' [operatore ^](../../../language-reference/operators/exponentiation-operator.md), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 La divisione di interi viene eseguita utilizzando l' [operatore \ (Visual Basic)](../../../language-reference/operators/integer-division-operator.md). La divisione integer restituisce il quoziente, ovvero il numero intero che rappresenta il numero di volte in cui il divisore può dividere il dividendo senza considerare alcun resto. Il divisore e il dividendo devono essere tipi integrali ( `SByte` ,, `Byte` `Short` , `UShort` , `Integer` , `UInteger` , `Long` e `ULong` ) per questo operatore. Tutti gli altri tipi devono prima essere convertiti in un tipo integrale. Nell'esempio seguente viene illustrata la divisione di interi.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 Il modulo aritmetico viene eseguito usando l' [operatore mod](../../../language-reference/operators/mod-operator.md). Questo operatore restituisce il resto dopo aver diviso il divisore nel dividendo un numero integrale di volte. Se il divisore e il dividendo sono tipi integrali, il valore restituito è integrale. Se divisore e dividendo sono tipi a virgola mobile, anche il valore restituito è a virgola mobile. Nell'esempio seguente viene illustrato questo comportamento.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>Tentativo di divisione per zero  
 La divisione per zero presenta risultati diversi a seconda dei tipi di dati interessati. Nelle divisioni integrali ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` ), il .NET Framework genera un' <xref:System.DivideByZeroException> eccezione. Nelle operazioni di divisione sul `Decimal` `Single` tipo di dati o, il .NET Framework genera anche un' <xref:System.DivideByZeroException> eccezione.  
  
 Nelle divisioni a virgola mobile che coinvolgono il `Double` tipo di dati non viene generata alcuna eccezione e il risultato è il membro della classe che rappresenta <xref:System.Double.NaN> , <xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity> , a seconda del dividendo. Nella tabella seguente vengono riepilogati i vari risultati del tentativo di dividere un `Double` valore per zero.  
  
|Tipo di dati Dividend|Tipo di dati divisore|Valore Dividend|Risultato|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(non è un numero definito matematicamente)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Quando si intercetta un' <xref:System.DivideByZeroException> eccezione, è possibile usare i relativi membri per gestirla. La proprietà, ad esempio, <xref:System.Exception.Message%2A> include il testo del messaggio per l'eccezione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Operazioni di spostamento di bit  
 Un'operazione di spostamento di bit esegue un turno aritmetico in uno schema di bit. Il modello è contenuto nell'operando a sinistra, mentre l'operando a destra specifica il numero di posizioni per lo spostamento del pattern. È possibile spostare il pattern a destra con l' [operatore>> ](../../../language-reference/operators/right-shift-operator.md) o a sinistra con l' [operatore<< ](../../../language-reference/operators/left-shift-operator.md).  
  
 Il tipo di dati dell'operando del criterio deve essere `SByte` ,, `Byte` `Short` , `UShort` , `Integer` , `UInteger` , `Long` o `ULong` . Il tipo di dati dell'operando Shift Amount deve essere `Integer` o deve ampliarsi a `Integer` .  
  
 I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità. Le posizioni dei bit sgomberate da uno spostamento vengono impostate nel modo seguente:  
  
- 0 per uno scorrimento a sinistra aritmetico  
  
- 0 per uno spostamento a destra aritmetico di un numero positivo  
  
- 0 per uno spostamento a destra aritmetico di un tipo di dati senza segno ( `Byte` , `UShort` , `UInteger` , `ULong` )  
  
- 1 per uno spostamento a destra aritmetico di un numero negativo ( `SByte` ,, `Short` `Integer` o `Long` )  
  
 Nell'esempio seguente viene spostato un `Integer` valore sia a sinistra che a destra.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 I turni aritmetici non generano mai eccezioni di overflow.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Oltre a essere operatori logici,,, `Not` `Or` e a `And` `Xor` eseguire operazioni aritmetiche bit per bit quando vengono utilizzati in valori numerici. Per ulteriori informazioni, vedere "operazioni bit per bit" negli [operatori logici e bit per bit in Visual Basic](logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Indipendenza dai tipi  
 Gli operandi devono essere in genere dello stesso tipo. Se ad esempio si sta aggiungendo una `Integer` variabile, è necessario aggiungerla a un'altra `Integer` variabile ed è necessario assegnare il risultato a una variabile di tipo `Integer` .  
  
 Per garantire una corretta procedura di codifica indipendente dai tipi, è possibile usare l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md). Se si imposta `Option Strict On` , Visual Basic esegue automaticamente le conversioni *indipendenti dai tipi* . Se, ad esempio, si tenta di aggiungere una variabile `Integer` a una variabile `Double` e si assegna il valore a una `Double` variabile, l'operazione procede normalmente, perché un `Integer` valore può essere convertito in `Double` senza perdita di dati. Le conversioni non sicure del tipo, d'altra parte, generano un errore del compilatore con `Option Strict On` . Se, ad esempio, si tenta di aggiungere una variabile `Integer` a una variabile `Double` e si assegna il valore a una `Integer` variabile, viene restituito un errore del compilatore, perché una `Double` variabile non può essere convertita in modo implicito nel tipo `Integer` .  
  
 Se si imposta `Option Strict Off` , tuttavia, Visual Basic consente di eseguire conversioni implicite verso un tipo di dati più piccolo, sebbene possano causare una perdita imprevista di dati o di precisione. Per questo motivo, è consigliabile usare quando si `Option Strict On` scrive il codice di produzione. Per altre informazioni, vedere [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Vedere anche

- [Operatori aritmetici](../../../language-reference/operators/arithmetic-operators.md)
- [Operatori di spostamento bit](../../../language-reference/operators/bit-shift-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Operatori di concatenazione in Visual Basic](concatenation-operators.md)
- [Operatori logici e bit per bit in Visual Basic](logical-and-bitwise-operators.md)
- [Combinazione efficace di operatori](efficient-combination-of-operators.md)
