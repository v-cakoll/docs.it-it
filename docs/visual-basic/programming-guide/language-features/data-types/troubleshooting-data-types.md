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
ms.openlocfilehash: 9bbc7f51de9899354184d051d8f1a584651dd030
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45696133"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Risoluzione dei problemi relativi ai tipi di dati (Visual Basic)
Questa pagina elenca alcuni problemi comuni che possono verificarsi quando si eseguono operazioni sui tipi di dati intrinseco.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Le espressioni a virgola mobile vengono considerati non uguali  
 Quando si lavora con numeri a virgola mobile ([singolo tipo di dati](../../../../visual-basic/language-reference/data-types/single-data-type.md) e [tipo di dati Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), tenere presente che sono archiviati come binarie frazioni. Ciò significa che non possono contenere una rappresentazione esatta di qualsiasi quantità che non è una frazione binaria (nel formato k o (2 ^ n) dove k e n sono numeri interi). Ad esempio, 0,5 (= 1 o 2) e 0,3125 (= 5/16) possono essere mantenuti come valori precisi, mentre (= 1, 5) 0.2 e 0.3 (= 3/10) può essere solo approssimazioni.  
  
 Per questo motivo dell'imprecisione, è possibile basarsi sui risultati esatti quando si opera su valori a virgola mobile. In particolare, due valori uguali in teoria potrebbero essere leggermente diverse rappresentazioni.  
  
| Per confrontare le quantità a virgola mobile | 
|---| 
|1.  Calcolare il valore assoluto della loro differenza tramite le <xref:System.Math.Abs%2A> metodo del <xref:System.Math> classe il <xref:System> dello spazio dei nomi.<br />2.  Determinare una differenza massima accettabile, in modo che è possibile prendere in considerazione le due quantità a essere uguali ai fini pratici se la loro differenza non superiore.<br />3.  Confrontare il valore assoluto della differenza con la differenza accettabile.|  
  
 L'esempio seguente illustra un confronto fra due sia errato e quello corretto `Double` valori.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 L'esempio precedente Usa la <xref:System.Double.ToString%2A> metodo del <xref:System.Double> strutturare in modo che consente di specificare la precisione migliore rispetto il `CStr` (parola chiave) viene utilizzato. Il valore predefinito è 15 cifre, ma il formato "G17" lo estende a 17 cifre.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Operatore Mod non restituisce risultati accurati  
 A causa dell'imprecisione dell'archiviazione a virgola mobile, il [operatore Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) può restituire un risultato imprevisto quando almeno uno degli operandi è a virgola mobile.  
  
 Il [tipo di dati Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) non usa la rappresentazione a virgola mobile. Molti numeri che inesatti in `Single` e `Double` sono esatti in `Decimal` (ad esempio 0.2 e 0.3). Sebbene il calcolo aritmetico risulta più lento in `Decimal` rispetto in virgola mobile, potrebbe essere utile la riduzione delle prestazioni per ottenere una maggiore precisione.  
  
|Per trovare il resto intero di quantità a virgola mobile|  
|---|  
|1.  Dichiarare le variabili come `Decimal`.<br />2.  Usare il carattere di tipo di valore letterale `D` valori letterali per forzare `Decimal`, nel caso in cui i relativi valori sono troppo grandi per il `Long` tipo di dati.|  
  
 L'esempio seguente illustra le potenzialità dell'imprecisione di operandi a virgola mobile.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 L'esempio precedente Usa la <xref:System.Double.ToString%2A> metodo del <xref:System.Double> strutturare in modo che consente di specificare la precisione migliore rispetto il `CStr` (parola chiave) viene utilizzato. Il valore predefinito è 15 cifre, ma il formato "G17" lo estende a 17 cifre.  
  
 In quanto `zeroPointTwo` è `Double`, il relativo valore per 0.2 è una frazione binaria ripetuta all'infinito con un valore memorizzato di 0.20000000000000001. Dividendo 2.0 questa quantità il risultato è 9,9999999999999995 con il resto di 0,19999999999999991.  
  
 Nell'espressione per `decimalRemainder`, il carattere di tipo letterale `D` forza di entrambi gli operandi in `Decimal`, e 0.2 la rappresentazione è precisa. Di conseguenza il `Mod` operatore restituisce il resto previsto pari a 0,0.  
  
 Si noti che non è sufficiente dichiarare `decimalRemainder` come `Decimal`. È anche necessario forzare i valori letterali `Decimal`, oppure utilizzare `Double` per impostazione predefinita e `decimalRemainder` riceve lo stesso valore non accurato `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Tipo booleano non viene convertito in tipo numerico con precisione  
 [Tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) valori non vengono archiviati come numeri e i valori archiviati non sono considerati equivalenti ai numeri. Per garantire la compatibilità con le versioni precedenti, Visual Basic include parole chiave di conversione ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`e così via) per la conversione tra `Boolean` e tipi numerici. Tuttavia, altri linguaggi a volte eseguono queste conversioni in modo diverso, come avviene il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metodi.  
  
 Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False`. Quando possibile, è consigliabile limitare l'utilizzo di `Boolean` variabili per i valori logici per il quale sono progettate. Se occorre combinare insieme `Boolean` e valori numerici, assicurarsi di aver compreso il metodo di conversione selezionati.  
  
### <a name="conversion-in-visual-basic"></a>Conversione in Visual Basic  
 Quando si usa la `CType` oppure `CBool` parole chiave di conversione per convertire i tipi di dati numerico `Boolean`, diventa 0 `False` e tutti gli altri valori diventano `True`. Quando si convertono `Boolean` i valori per i tipi numerici con parole chiave di conversione `False` diventa 0 e `True` diventano -1.  
  
### <a name="conversion-in-the-framework"></a>Conversione in Framework  
 Il <xref:System.Convert.ToInt32%2A> metodo del <xref:System.Convert> classe la <xref:System> converte lo spazio dei nomi `True` in + 1.  
  
 Se è necessario convertire un `Boolean` valore a un tipo di dati numerici, prestare attenzione a quale metodo di conversione è utilizzare.  
  
## <a name="character-literal-generates-compiler-error"></a>Valore letterale carattere genera l'errore del compilatore  
 In assenza di qualsiasi tipo di carattere, Visual Basic predefiniti si presuppone che i tipi di dati per i valori letterali. Il tipo predefinito per un valore letterale carattere, racchiuso tra virgolette (`" "`), ovvero è `String`.  
  
 Il `String` tipo di dati non si amplia per il [tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Ciò significa che se si desidera assegnare un valore letterale in una `Char` variabile, è necessario eseguire una conversione di narrowing o forzare il valore letterale per il `Char` tipo.  

|Per creare un carattere letterale da assegnare a una variabile o costante|
|---|  
|1.  Dichiarare la variabile o costante come `Char`.<br />2.  Racchiudere il valore del carattere virgolette (`" "`).<br />3.  Seguire il segno di virgolette doppie di chiusura con il carattere di tipo di valore letterale `C` per forzare il valore letterale `Char`. Questa operazione è necessaria se passa il controllo del tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `On`, ed è quindi preferibile in ogni caso.|  
  
 L'esempio seguente illustra le assegnazioni di sia riuscite e ha esito positivo di un valore letterale a una `Char` variabile.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 In è sempre presente un rischio Usa le conversioni di narrowing, poiché è possibile non riesca in fase di esecuzione. Ad esempio, una conversione da `String` al `Char` può non riuscire se il `String` valore contiene più di un carattere. Pertanto, è preferibile programmare per utilizzare il `C` Digita carattere.  
  
## <a name="string-conversion-fails-at-run-time"></a>Si verifica un errore di conversione di stringhe in fase di esecuzione  
 Il [tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md) fa parte di un numero molto ridotto le conversioni di ampliamento. `String` amplia solo a se stesso e `Object`e solo `Char` e `Char()` (un `Char` array) ampliarsi `String`. Infatti, `String` variabili e costanti possono contenere valori che non possono contenere altri tipi di dati.  
  
 Quando il controllo del tipo di opzione ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `On`, il compilatore non consente conversioni di narrowing implicite. Sono inclusi quelli che coinvolgono `String`. Il codice può comunque usare parole chiave di conversione, ad esempio `CStr` e [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), che spingono i [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] tentare la conversione.  
  
> [!NOTE]
>  L'errore di conversione narrowing viene eliminata per le conversioni dagli elementi in un `For Each…Next` insieme alla variabile di controllo del ciclo. Per altre informazioni ed esempi, vedere la sezione "Conversioni di Narrowing" [For Each... Istruzione Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Protezione di conversione Narrowing  
 Lo svantaggio di conversione di narrowing è che può non riuscire in fase di esecuzione. Ad esempio, se un `String` variabile contiene un valore diverso da "True" o "False", non può essere convertito in `Boolean`. Se sono presenti caratteri di punteggiatura, la conversione a qualsiasi tipo numerico ha esito negativo. A meno che non si è certi che il `String` variabile contiene sempre i valori che può accettare il tipo di destinazione, non è consigliabile provare una conversione.  
  
 Se è necessario convertire dal `String` a un altro tipo di dati, la procedura più sicura consiste nel racchiudere la conversione tentata nel [Try... Catch... Istruzione finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Ciò consente di gestire un errore in fase di esecuzione.  
  
### <a name="character-arrays"></a>Matrici di caratteri  
 Un unico `Char` e una matrice di `Char` entrambi si amplia in elementi `String`. Tuttavia `String` si amplia in `Char()`. Per convertire un `String` valore per un `Char` matrice, è possibile utilizzare il <xref:System.String.ToCharArray%2A> metodo del <xref:System.String?displayProperty=nameWithType> classe.  
  
### <a name="meaningless-values"></a>Valori non significativi  
 In generale, `String` valori non sono significativi in altri tipi di dati e la conversione è estremamente artificiali e pericoloso. Quando possibile, è consigliabile limitare l'utilizzo di `String` variabili alle sequenze di caratteri per il quale sono progettate. Non scrivere mai codice che si basa su valori equivalenti in altri tipi.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Uso efficiente dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
