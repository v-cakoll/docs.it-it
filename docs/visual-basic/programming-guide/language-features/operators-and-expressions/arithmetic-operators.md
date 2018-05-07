---
title: Operatori aritmetici in Visual Basic
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
ms.openlocfilehash: cd66d08eba973a796472fcbd40a6a84edbbb62ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="arithmetic-operators-in-visual-basic"></a>Operatori aritmetici in Visual Basic
Operatori aritmetici consentono di eseguire molte delle comuni operazioni aritmetiche che comportano il calcolo di valori numerici rappresentati da valori letterali, variabili, altre espressioni, funzione e chiamate a proprietà e costanti. Anche classificati con operatori aritmetici sono gli operatori di spostamento di bit, che operano a livello dei singoli bit degli operandi e spostare degli schemi di bit a sinistra o a destra.  
  
## <a name="arithmetic-operations"></a>Operazioni aritmetiche  
 È possibile aggiungere due valori in un'espressione con il [+ (operatore)](../../../../visual-basic/language-reference/operators/addition-operator.md), o da un'altra con sottrarre il [-operatore (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Negazione utilizza inoltre il [-operatore (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), ma con un solo operando, come nell'esempio seguente viene illustrato.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Utilizzo di moltiplicazione e divisione di [* operatore](../../../../visual-basic/language-reference/operators/multiplication-operator.md) e [/ (operatore) (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), rispettivamente, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Elevamento a potenza utilizza il [^ operatore](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 La divisione di integer viene eseguita utilizzando il [\ (operatore) (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Divisione di interi restituisce il quoziente, vale a dire un valore integer che rappresenta il numero di volte in cui il divisore possono essere suddivisi in dividendo senza tenere conto di eventuali residui. Sia il divisore e il dividendo devono essere tipi integrali (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, e `ULong`) per l'operatore. Tutti gli altri tipi devono essere convertiti prima a un tipo integrale. L'esempio seguente illustra la divisione di interi.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 Il modulo aritmetico viene eseguito utilizzando il [operatore Mod](../../../../visual-basic/language-reference/operators/mod-operator.md). Questo operatore restituisce il resto dopo aver diviso il divisore per il dividendo per un numero intero di volte. Se il divisore e dividendo sono entrambi tipi integrali, il valore restituito è di tipo integrale. Se il divisore e dividendo sono tipi a virgola mobile, il valore restituito è anche a virgola mobile. Nell'esempio seguente viene illustrato questo comportamento.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>Tentativo di divisione per Zero  
 Divisione per zero produce risultati diversi a seconda dei tipi di dati coinvolti. In integrali suddivisioni (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] genera un <xref:System.DivideByZeroException> eccezione. In operazioni di divisione di `Decimal` o `Single` tipo di dati, il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] genera inoltre un <xref:System.DivideByZeroException> eccezione.  
  
 Divisioni a virgola mobile che implicano il `Double` il tipo di dati, viene generata alcuna eccezione e il risultato è il membro della classe che rappresenta <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, o <xref:System.Double.NegativeInfinity>, a seconda del dividendo. Nella tabella seguente sono riepilogati i vari risultati tentativo di dividere un `Double` valore in base zero.  
  
|Tipo di dati dividendo|Tipo di dati divisore|Valore del dividendo|Risultato|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (non un numero definito matematicamente)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Quando viene rilevata una <xref:System.DivideByZeroException> eccezione, è possibile utilizzare i relativi membri che consentono di gestirlo. Ad esempio, il <xref:System.Exception.Message%2A> proprietà contiene il testo del messaggio dell'eccezione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Operazioni di spostamento di bit  
 Un'operazione di spostamento di bit esegue uno scorrimento aritmetico in uno schema di bit. Il modello di contenuto dell'operando di sinistra, mentre l'operando a destra specifica il numero di posizioni per spostare lo schema. È possibile spostare il modello a destra con la [>> operatore](../../../../visual-basic/language-reference/operators/right-shift-operator.md) o a sinistra con la [<< operatore](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Il tipo di dati dell'operando dello schema deve essere `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`. Deve essere il tipo di dati dell'operando quantità shift `Integer` o deve ampliarsi a `Integer`.  
  
 Aritmetici non sono circolare, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità. Le posizioni dei bit liberate da uno spostamento impostate come indicato di seguito:  
  
-   0 per uno scorrimento aritmetico a sinistra  
  
-   0 per un aritmetico a destra di un numero positivo  
  
-   0 per un aritmetico a destra di un tipo di dati senza segno (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 per un aritmetico a destra di un numero negativo (`SByte`, `Short`, `Integer`, o `Long`)  
  
 Nell'esempio seguente sposta un `Integer` valore a sinistra e a destra.  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Aritmetici non generano mai eccezioni di overflow.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Oltre a essere operatori logici, `Not`, `Or`, `And`, e `Xor` inoltre eseguire operazioni aritmetiche bit per bit se utilizzati con valori numerici. Per ulteriori informazioni, vedere "Operazioni bit per bit" in [operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Indipendenza dai tipi  
 Gli operandi in genere devono essere dello stesso tipo. Ad esempio, se si esegue un'addizione con un `Integer` variabile, è necessario aggiungerlo a un altro `Integer` variabile ed è necessario assegnare il risultato a una variabile di tipo `Integer` anche.  
  
 Un modo per garantire una buona indipendente dai tipi scrittura di codice consiste nell'utilizzare il [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Se si imposta `Option Strict On`, Visual Basic esegue automaticamente *indipendente dai tipi* conversioni. Ad esempio, se si tenta di aggiungere un `Integer` variabile a un `Double` variabile e assegnare il valore a un `Double` variabile, l'operazione viene eseguita in genere, perché un `Integer` valore può essere convertito in `Double` senza perdita di dati. Conversioni di tipo-unsafe, d'altra parte, provocare un errore del compilatore con `Option Strict On`. Ad esempio, se si tenta di aggiungere un `Integer` variabile a un `Double` variabile e assegnare il valore a un `Integer` variabile, un errore del compilatore risultati, perché un `Double` variabile non può essere convertita in modo implicito nel tipo `Integer`.  
  
 Se si imposta `Option Strict Off`, tuttavia, Visual Basic consente conversioni implicite verso un abbiano luogo, anche se possono comportare la perdita di dati o di precisione imprevista. Per questo motivo, è consigliabile utilizzare `Option Strict On` durante la scrittura di codice di produzione. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori aritmetici](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operatori di spostamento bit](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operatori di concatenazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
