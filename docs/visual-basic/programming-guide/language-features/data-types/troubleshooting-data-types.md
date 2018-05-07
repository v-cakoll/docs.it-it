---
title: Risoluzione dei problemi relativi ai tipi di dati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: c5ff9d097c0660956a9751a23511d8273766227c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-data-types-visual-basic"></a>Risoluzione dei problemi relativi ai tipi di dati (Visual Basic)
Questa pagina elenca alcuni problemi comuni che possono verificarsi quando si eseguono operazioni su tipi di dati intrinseci.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Le espressioni a virgola mobile non vengono considerati uguali  
 Quando si lavora con numeri a virgola mobile ([singolo tipo di dati](../../../../visual-basic/language-reference/data-types/single-data-type.md) e [tipo di dati Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), tenere presente che sono archiviati come frazioni binarie. Ciò significa che non possono contenere una rappresentazione esatta di qualsiasi quantità che non è una frazione binaria (nel formato k / (2 ^ n) dove k e n sono numeri interi). Ad esempio 0,5 (= 1/2) e 0,3125 (= 5/16) possono essere mantenuti come valori precisi, mentre 0,2 (= 1/5) e 0,3 (= 3/10) possono essere solo approssimazioni.  
  
 Per questo motivo imprecisione, è possibile basarsi sui risultati esatti quando si opera su valori a virgola mobile. In particolare, due valori che sono uguali in teoria potrebbero essere leggermente diverse rappresentazioni.  
  
| Per confrontare le quantità a virgola mobile | 
|---| 
|1.  Calcolare il valore assoluto della loro differenza utilizzando il <xref:System.Math.Abs%2A> metodo il <xref:System.Math> classe il <xref:System> dello spazio dei nomi.<br />2.  Determinare una differenza massima accettabile, in modo che è possibile prendere in considerazione due quantità siano uguali ai fini pratici se la relativa differenza non sia superiore.<br />3.  Confrontare il valore assoluto della differenza con la differenza accettabile.|  
  
 Nell'esempio seguente viene corretto sia corretto il confronto di due `Double` valori.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 L'esempio precedente Usa il <xref:System.Double.ToString%2A> metodo il <xref:System.Double> struttura in modo che è possibile specificare la migliore precisione rispetto di `CStr` Usa (parola chiave). Il valore predefinito è 15 cifre, ma il formato "G17" si estende a 17 cifre.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Operatore Mod non restituisce risultati accurati  
 A causa dell'imprecisione dell'archiviazione a virgola mobile, il [operatore Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) può restituire un risultato imprevisto quando almeno uno degli operandi è a virgola mobile.  
  
 Il [tipo di dati Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) non utilizza la rappresentazione a virgola mobile. Molti numeri inesatti in `Single` e `Double` sono esatti in `Decimal` (ad esempio 0,2 e 0,3). Sebbene il calcolo aritmetico è più lenta `Decimal` rispetto in virgola mobile, è possibile perdita di prestazioni per ottenere una maggiore precisione.  
  
|Per trovare il resto intero di quantità a virgola mobile|  
|---|  
|1.  Dichiarare le variabili come `Decimal`.<br />2.  Utilizzare il carattere di tipo letterale `D` per valori letterali per forzare `Decimal`, nel caso in cui i relativi valori sono troppo grande per il `Long` tipo di dati.|  
  
 L'esempio seguente illustra la potenziale imprecisione degli operandi a virgola mobile.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 L'esempio precedente Usa il <xref:System.Double.ToString%2A> metodo il <xref:System.Double> struttura in modo che è possibile specificare la migliore precisione rispetto di `CStr` Usa (parola chiave). Il valore predefinito è 15 cifre, ma il formato "G17" si estende a 17 cifre.  
  
 Poiché `zeroPointTwo` è `Double`, il valore per 0,2 è una frazione binaria ripetuta all'infinito con un valore archiviato di 0,20000000000000001. Dividendo 2.0 per questa quantità il risultato è 9,9999999999999995 con il resto di 0,19999999999999991.  
  
 Nell'espressione per `decimalRemainder`, il tipo di valore letterale di carattere `D` impone entrambi gli operandi siano `Decimal`, e 0,2 la rappresentazione è precisa. Pertanto il `Mod` operatore produce il resto previsto pari a 0,0.  
  
 Si noti che non è sufficiente dichiarare `decimalRemainder` come `Decimal`. È necessario anche imporre ai valori letterali di `Decimal`, o usano `Double` per impostazione predefinita e `decimalRemainder` riceve lo stesso valore corretta `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Tipo Boolean non converte in modo accurato in tipo numerico  
 [Tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) valori non vengono archiviati come numeri e i valori archiviati non sono considerati equivalenti ai numeri. Per la compatibilità con le versioni precedenti, Visual Basic consente di parole chiave di conversione ([funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`e così via) per la conversione tra `Boolean` e tipi numerici. Tuttavia, altri linguaggi talvolta eseguono queste conversioni in modo diverso, come il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metodi.  
  
 Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False`. Quando possibile, è consigliabile limitare l'utilizzo di `Boolean` variabili per i valori logici per cui vengono progettate. Se è necessario combinare `Boolean` e valori numerici, assicurarsi di aver compreso il metodo di conversione selezionati.  
  
### <a name="conversion-in-visual-basic"></a>Conversione in Visual Basic  
 Quando si utilizza il `CType` o `CBool` parole chiave di conversione per convertire i tipi di dati numerici per `Boolean`, diventa 0 `False` e tutti gli altri valori diventano `True`. Quando esegue la conversione `Boolean` valori in tipi numerici utilizzando le parole chiave di conversione, `False` diventa 0 e `True` diventa -1.  
  
### <a name="conversion-in-the-framework"></a>Conversione in Framework  
 Il <xref:System.Convert.ToInt32%2A> metodo il <xref:System.Convert> classe il <xref:System> converte dello spazio dei nomi `True` e + 1.  
  
 Se è necessario convertire un `Boolean` valore a un tipo di dati numerici, assicurarsi che il metodo di conversione da utilizzare.  
  
## <a name="character-literal-generates-compiler-error"></a>Valore letterale carattere genera l'errore del compilatore  
 In assenza di caratteri di qualsiasi tipo, Visual Basic assume predefinito i tipi di dati per i valori letterali. Il tipo predefinito per un valore letterale carattere, racchiuso tra virgolette (`" "`), ovvero è `String`.  
  
 Il `String` tipo di dati si amplia nel [tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Ciò significa che se si desidera assegnare un valore letterale in un `Char` variabile, è necessario eseguire una conversione di narrowing o forzare il valore letterale di `Char` tipo.  

|Per creare un carattere letterale per assegnare a una variabile o costante|
|---|  
|1.  Dichiarare la variabile o costante come `Char`.<br />2.  Racchiudere il valore del carattere tra virgolette (`" "`).<br />3.  Seguire il segno di virgolette doppie di chiusura con il carattere di tipo letterale `C` per forzare il valore letterale `Char`. Questa operazione è necessaria se il controllo dei tipi passa ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `On`, ed è utile in tutti i casi.|  
  
 L'esempio seguente illustra le assegnazioni di esito negativa e non riuscite di un valore letterale in un `Char` variabile.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 È sempre un rischio con le conversioni di restrizione, perché si può avere esito negativo in fase di esecuzione. Ad esempio, una conversione da `String` a `Char` può non riuscire se il `String` valore contiene più di un carattere. Pertanto, è preferibile programmare per utilizzare il `C` carattere tipo.  
  
## <a name="string-conversion-fails-at-run-time"></a>Conversione di stringhe ha esito negativo in fase di esecuzione  
 Il [tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md) partecipa poche le conversioni di ampliamento. `String` Allarga solo a se stessa e `Object`e solo `Char` e `Char()` (un `Char` matrice) ampliarsi `String`. In questo modo `String` variabili e costanti possono contenere valori che non possono contenere altri tipi di dati.  
  
 Quando il controllo del tipo di opzione ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `On`, il compilatore non consente conversioni di narrowing implicite. Sono inclusi quelli che coinvolgono `String`. Il codice può comunque utilizzare parole chiave di conversione, ad esempio `CStr` e [CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md), quali direct il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] a tentare la conversione.  
  
> [!NOTE]
>  L'errore di conversione di restrizione viene eliminato per le conversioni dagli elementi in un `For Each…Next` insieme alla variabile di controllo del ciclo. Per ulteriori informazioni ed esempi, vedere la sezione "Conversioni di restrizione" [For Each... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Protezione della conversione di Narrowing  
 Lo svantaggio di conversioni di restrizione è che potrebbe non riuscire in fase di esecuzione. Ad esempio, se un `String` variabile contiene esclusivamente "True" o "False", non può essere convertito in `Boolean`. Se contiene caratteri di punteggiatura, errore di conversione in qualsiasi tipo numerico. A meno che non si è certi che il `String` la variabile mantiene sempre i valori che può accettare il tipo di destinazione, non è consigliabile provare una conversione.  
  
 Se è necessario convertire da `String` a un altro tipo di dati, la procedura più sicura consiste nel racchiudere la conversione tentata nel [provare... Catch... Istruzione finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Ciò consente di gestire un errore in fase di esecuzione.  
  
### <a name="character-arrays"></a>Matrici di caratteri  
 Un singolo `Char` e una matrice di `Char` elementi entrambi ampliarsi `String`. Tuttavia, `String` si amplia in `Char()`. Per convertire un `String` valore un `Char` matrice, è possibile utilizzare il <xref:System.String.ToCharArray%2A> metodo la <xref:System.String?displayProperty=nameWithType> classe.  
  
### <a name="meaningless-values"></a>Valori non significativi  
 In generale, `String` valori non sono significativi in altri tipi di dati e la conversione è altamente artificiale e pericolosa. Quando possibile, è consigliabile limitare l'utilizzo di `String` variabili per le sequenze di caratteri per cui vengono progettate. Non scrivere mai codice che si basa su valori equivalenti in altri tipi.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Uso efficiente dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
