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
ms.openlocfilehash: 2bd88b2df91c38d658e46157a9a83ce44ab9f25c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981270"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Operatori aritmetici in Visual Basic
Operatori aritmetici consentono di eseguire molte delle comuni operazioni aritmetiche che coinvolgono il calcolo dei valori numerici rappresentati da valori letterali, variabili, altre espressioni, (funzione) e le chiamate di proprietà e costanti. Anche classificati con operatori aritmetici sono elencati gli operatori di spostamento di bit, che operano a livello dei singoli bit di operandi- and -shift degli schemi di bit verso sinistra o destra.  
  
## <a name="arithmetic-operations"></a>Operazioni aritmetiche  
 È possibile aggiungere due valori in un'espressione con il [+ (operatore)](../../../../visual-basic/language-reference/operators/addition-operator.md), o sottrarre da un'altra con il [-operatore (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 Negazione Usa anche il [-operatore (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), ma con un solo operando, come illustrato nell'esempio seguente viene illustrato.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 Uso di moltiplicazione e divisione il [* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md) e [/ operatore (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), rispettivamente, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 Elevamento a potenza Usa la [^ operatore](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 La divisione di integer viene eseguita usando il [\ (operatore) (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Divisione di interi restituisce il quoziente, ovvero integer che rappresenta il numero di volte in cui il divisore può dividere il dividendo senza tenere conto di qualsiasi parte rimanente. Sia il divisore e dividendo devono essere tipi integrali (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, e `ULong`) per questo operatore. Tutti gli altri tipi devono essere convertiti prima di tutto a un tipo integrale. L'esempio seguente illustra la divisione di interi.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 Modulo aritmetico viene eseguito usando il [operatore Mod](../../../../visual-basic/language-reference/operators/mod-operator.md). Questo operatore restituisce il resto dopo aver diviso il divisore per il dividendo per un numero integrale di ore. Se il divisore e dividendo sono entrambi tipi integrali, il valore restituito è parte integrante. Se il divisore e dividendo sono tipi a virgola mobile, il valore restituito è anche a virgola mobile. Nell'esempio seguente viene illustrato questo comportamento.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>Tentativo di divisione per Zero  
 Divisione per zero potrà avere risultati diversi a seconda dei tipi di dati coinvolti. In integrali divisioni (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] genera un <xref:System.DivideByZeroException> eccezione. Nelle operazioni di divisione il `Decimal` o `Single` tipo di dati, il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] genera inoltre un <xref:System.DivideByZeroException> eccezione.  
  
 In suddivisioni a virgola mobile che implicano la `Double` tipo di dati, viene generata alcuna eccezione e il risultato è il membro della classe che rappresenta <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, o <xref:System.Double.NegativeInfinity>, a seconda del dividendo. Nella tabella seguente riepiloga i diversi risultati del tentativo di dividere un `Double` valore in base zero.  
  
|Tipo di dati dividendo|Tipo di dati divisore|Valore dividendo|Risultato|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (non un numero definito matematicamente)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Quando si intercetta un <xref:System.DivideByZeroException> eccezione, è possibile usare i relativi membri che consentono di gestirlo. Ad esempio, il <xref:System.Exception.Message%2A> proprietà contiene il testo del messaggio dell'eccezione. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Operazioni di spostamento di bit  
 Un'operazione di spostamento di bit esegue uno spostamento aritmetico in uno schema di bit. Il modello di contenuto dell'operando a sinistra, mentre l'operando a destra specifica il numero di posizioni da spostare lo schema. È possibile spostare il modello a destra con il [>> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md) o a sinistra con la [<< operatore](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 Il tipo di dati dell'operando dello schema deve essere `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`. Deve essere il tipo di dati dell'operando quantità shift `Integer` o devono potersi ampliare al `Integer`.  
  
 Aritmetici non sono circolari, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità. Le posizioni dei bit lasciati liberi tramite un turno sono impostate come indicato di seguito:  
  
-   0 per uno spostamento a sinistra aritmetico  
  
-   0 per uno scorrimento aritmetico a destra di un numero positivo  
  
-   0 per uno scorrimento aritmetico a destra di un tipo di dati non firmati (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 per uno scorrimento aritmetico a destra di un numero negativo (`SByte`, `Short`, `Integer`, o `Long`)  
  
 Nell'esempio seguente sposta un' `Integer` valore sia a sinistra e destra.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Aritmetici non generano mai le eccezioni di overflow.  
  
## <a name="bitwise-operations"></a>Operazioni bit per bit  
 Oltre a essere gli operatori logici `Not`, `Or`, `And`, e `Xor` anche eseguire operazioni aritmetiche bit per bit se utilizzata con valori numerici. Per altre informazioni, vedere "Operazioni bit per bit" nella [operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Indipendenza dai tipi  
 Gli operandi in genere devono essere dello stesso tipo. Ad esempio, se si esegue un'addizione con un `Integer` variabile, è necessario aggiungerla a un altro `Integer` variabile ed è consigliabile assegnare il risultato a una variabile di tipo `Integer` anche.  
  
 Un modo per garantire indipendente dai tipi buona procedura di codifica consiste nell'usare la [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Se si imposta `Option Strict On`, Visual Basic esegue automaticamente *indipendente dai tipi* conversioni. Ad esempio, se si prova ad aggiungere un `Integer` variabile a un `Double` variabile e assegnare il valore a un `Double` variabile, l'operazione procede normalmente, in quanto un `Integer` valore può essere convertito in `Double` senza perdita di dati. Le conversioni di tipo unsafe, d'altra parte, provocare un errore del compilatore con `Option Strict On`. Ad esempio, se si prova ad aggiungere un `Integer` variabile a un `Double` variabile e assegnare il valore a un `Integer` variabile, un errore del compilatore generato, perché una `Double` variabile non può essere convertita in modo implicito nel tipo `Integer`.  
  
 Se si imposta `Option Strict Off`, tuttavia, Visual Basic consente le conversioni di narrowing implicite si verifica anche se possono comportare la perdita imprevista di dati o di precisione. Per questo motivo, è consigliabile usare `Option Strict On` durante la scrittura di codice di produzione. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Vedere anche
- [Operatori aritmetici](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operatori di spostamento bit](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori di concatenazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
