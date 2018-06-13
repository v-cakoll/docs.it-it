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
ms.openlocfilehash: b0ab186945b456d7fb4dde3f52724b08a99e2827
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652500"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Parametri e argomenti delle routine (Visual Basic)
Nella maggior parte dei casi, una stored procedure richiede alcune informazioni sulle circostanze in cui è stato chiamato. Una routine che esegue attività ripetute o condivise utilizza informazioni diverse per ogni chiamata. Queste informazioni è costituito da variabili, costanti ed espressioni che viene passato alla routine quando viene chiamato.  
  
 Oggetto *parametro* rappresenta un valore che la procedura prevede di specificare quando viene chiamato. La dichiarazione della routine definisce i parametri.  
  
 È possibile definire una routine con senza parametri, un parametro di uno o più. La parte della definizione della routine che specifica i parametri viene chiamata il *elenco parametri*.  
  
 Un *argomento* rappresenta il valore fornito per un parametro di routine quando si chiama la routine. Il codice chiamante fornisce gli argomenti quando viene chiamata la procedura. La parte della chiamata di routine che specifica gli argomenti viene chiamata il *elenco di argomenti*.  
  
 La figura seguente illustra la procedura di chiamata del codice `safeSquareRoot` da due posizioni diverse. La prima chiamata passa il valore della variabile `x` (4.0) per il parametro `number`e il valore restituito in `root` (2.0) viene assegnato alla variabile `y`. La seconda chiamata passa il valore letterale 9.0 per `number`e assegna il valore restituito (3.0) variabile `z`.  
  
 ![Diagramma grafico del passaggio argomento al parametro](./media/parametersargue.gif "ParametersArgue")  
Passa un argomento a un parametro  
  
 Per ulteriori informazioni, vedere [le differenze tra parametri e argomenti](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Tipo di dati di parametro  
 Si definisce un tipo di dati per un parametro utilizzando il `As` clausola nella relativa dichiarazione. Ad esempio, la funzione seguente accetta una stringa e un numero intero.  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 Se il controllo dei tipi passa ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `Off,` il `As` clausola è facoltativa, ad eccezione del fatto che un qualsiasi parametro utilizzata da tutti i parametri devono essere utilizzata. Il controllo di tipo `On`, `As` clausola è obbligatoria per tutti i parametri di stored procedure.  
  
 Se il codice chiamante prevede di fornire un argomento con un tipo di dati diverso da quello del parametro corrispondente, come `Byte` per un `String` parametro, è necessario eseguire una delle operazioni seguenti:  
  
-   Specificare solo gli argomenti con i tipi di dati che vengono ampliati al tipo di dati del parametro.  
  
-   Impostare `Option Strict Off` per consentire conversioni implicite verso un; o  
  
-   Utilizzare una parola chiave di conversione per convertire esplicitamente il tipo di dati.  
  
### <a name="type-parameters"></a>Parametri di tipo  
 Oggetto *routine generica* definisce anche una o più *parametri di tipo* oltre ai normali parametri. Una routine generica consente al codice chiamante passare i tipi di dati diversi ogni volta che viene chiamata la routine, in modo che la possibilità di personalizzare i tipi di dati per i requisiti di ogni singola chiamata. Vedere [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Function](./function-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Procedura: Definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)  
 [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
