---
title: Parametri e argomenti delle routine
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
ms.openlocfilehash: 178206ca2ee103bbdb5a4ac03bca0df903c8c5d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406716"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Parametri e argomenti delle routine (Visual Basic)
Nella maggior parte dei casi, una procedura richiede alcune informazioni sulle circostanze in cui è stata chiamata. Una procedura che esegue attività ripetute o condivise USA informazioni diverse per ogni chiamata. Queste informazioni sono costituite da variabili, costanti ed espressioni passate alla procedura quando viene chiamata.  
  
 Un *parametro* rappresenta un valore che la routine prevede di fornire quando viene chiamato. La dichiarazione della stored procedure definisce i relativi parametri.  
  
 È possibile definire una routine senza parametri, un parametro o più di uno. La parte della definizione della routine che specifica i parametri è denominata *elenco di parametri*.  
  
 Un *argomento* rappresenta il valore fornito a un parametro di routine quando si chiama la stored procedure. Il codice chiamante fornisce gli argomenti quando chiama la routine. La parte della chiamata di procedura che specifica gli argomenti è denominata *elenco di argomenti*.  
  
 Nella figura seguente viene illustrato il codice che chiama la procedura `safeSquareRoot` da due posizioni diverse. La prima chiamata passa il valore della variabile `x` (4,0) al parametro `number` e il valore restituito in `root` (2,0) viene assegnato alla variabile `y` . La seconda chiamata passa il valore letterale 9,0 a `number` e assegna il valore restituito (3,0) alla variabile `z` .  
  
 ![Diagramma che mostra il passaggio di un argomento a un parametro](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 Per ulteriori informazioni, vedere [differenze tra parametri e argomenti](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Tipo di dati del parametro  
 Per definire un tipo di dati per un parametro, usare la `As` clausola nella relativa dichiarazione. La funzione seguente, ad esempio, accetta una stringa e un numero intero.  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 Se l'opzione di controllo del tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) è `Off,` la `As` clausola è facoltativa, ad eccezione del fatto che se un parametro lo usa, tutti i parametri devono utilizzarlo. Se il controllo del tipo è `On` , la `As` clausola è obbligatoria per tutti i parametri di routine.  
  
 Se il codice chiamante prevede di fornire un argomento con un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` un `String` parametro, deve eseguire una delle operazioni seguenti:  
  
- Fornire solo argomenti con tipi di dati che si ampliano al tipo di dati del parametro;  
  
- Impostare `Option Strict Off` per consentire le conversioni implicite verso un tipo di caratteri più piccolo oppure  
  
- Usare una parola chiave di conversione per convertire in modo esplicito il tipo di dati.  
  
### <a name="type-parameters"></a>Parametri di tipo  
 Una *routine generica* definisce anche uno o più *parametri di tipo* oltre ai parametri normali. Una routine generica consente al codice chiamante di passare tipi di dati diversi ogni volta che viene chiamata la procedura, in modo da poter adattare i tipi di dati ai requisiti di ogni singola chiamata. Vedere [Generic Procedures in Visual Basic](../data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Procedura: definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Overload della routine](./procedure-overloading.md)
- [Conversioni di tipi in Visual Basic](../data-types/type-conversions.md)
