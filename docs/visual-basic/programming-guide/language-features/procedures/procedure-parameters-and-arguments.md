---
title: Parametri e argomenti delle routine (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: 80065cabcacdcf44b04fef7bacb978ca9c8077ae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825456"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Parametri e argomenti delle routine (Visual Basic)
Nella maggior parte dei casi, una procedura richiede alcune informazioni sulle circostanze in cui è stato chiamato. Una routine che esegue attività ripetute o condivise Usa informazioni diverse per ogni chiamata. Queste informazioni è costituito da variabili, costanti ed espressioni che viene passato alla procedura quando si chiama.  
  
 Oggetto *parametro* rappresenta un valore che la procedura prevede di specificare quando viene chiamata. La dichiarazione della routine definisce i relativi parametri.  
  
 È possibile definire una routine con senza parametri, un parametro di uno o più. La parte della definizione della routine che specifica i parametri si chiama il *elenco di parametri*.  
  
 Un' *argomento* rappresenta il valore fornito a un parametro di procedura quando si chiama la routine. Il codice chiamante fornisce gli argomenti quando viene chiamata la routine. La parte della chiamata di routine che specifica gli argomenti si chiama il *elenco di argomenti*.  
  
 La figura seguente illustra codice che chiama la routine `safeSquareRoot` da due posizioni diverse. La prima chiamata passa il valore della variabile `x` (4.0) per il parametro `number`e il valore restituito nella `root` (2.0) viene assegnato alla variabile `y`. La seconda chiamata passa il valore letterale 9.0 `number`e assegna il valore restituito (3.0) alla variabile `z`.  
  
 ![Diagramma che mostra il passaggio di un argomento a un parametro](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 Per altre informazioni, vedere [differenze tra parametri e argomenti](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Tipo di dati di parametro  
 Si definisce un tipo di dati per un parametro utilizzando il `As` clausola nella relativa dichiarazione. Ad esempio, la funzione seguente accetta una stringa e un numero intero.  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 Se il controllo del tipo passa ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) viene `Off,` il `As` clausola è facoltativa, ad eccezione del fatto che lo usa un parametro, tutti i parametri devono essere. Se il controllo di tipo `On`, il `As` clausola è obbligatoria per tutti i parametri di procedura.  
  
 Se il codice chiamante si aspetta di fornire un argomento con un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` a un `String` parametro, è necessario eseguire una delle operazioni seguenti:  
  
-   Specificare solo argomenti con i tipi di dati che vengono ampliati al tipo di dati di parametro.  
  
-   Impostare `Option Strict Off` per consentire le conversioni di narrowing implicite; o  
  
-   Usare una parola chiave di conversione per convertire in modo esplicito il tipo di dati.  
  
### <a name="type-parameters"></a>Parametri di tipo  
 Oggetto *routine generica* definisce anche uno o più *parametri di tipo* oltre i relativi parametri normali. Una routine generica consente di passare diversi tipi di dati ogni volta che viene chiamata la routine, in modo che è possibile personalizzare i tipi di dati per i requisiti di ogni singola chiamata al codice chiamante. Vedere [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Overload della routine](./procedure-overloading.md)
- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
