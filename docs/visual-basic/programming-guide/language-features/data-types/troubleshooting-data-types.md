---
title: Risoluzione dei problemi relativi ai tipi di dati
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
ms.openlocfilehash: 239e1c2f908a9023aeca6e92aff4633b60f27b69
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393403"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Risoluzione dei problemi relativi ai tipi di dati (Visual Basic)

In questa pagina sono elencati alcuni problemi comuni che possono verificarsi quando si eseguono operazioni sui tipi di dati intrinseci.

## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Le espressioni a virgola mobile non vengono confrontate come uguali

Quando si utilizzano numeri a virgola mobile (tipo di[dati singolo](../../../language-reference/data-types/single-data-type.md) e [tipo di dati Double](../../../language-reference/data-types/double-data-type.md)), tenere presente che vengono archiviati come frazioni binarie. Ciò significa che non è possibile mantenere una rappresentazione esatta di qualsiasi quantità che non sia una frazione binaria (nel formato k/(2 ^ n), dove k e n sono numeri interi. 0,5 (= 1/2) e 0,3125 (= 5/16), ad esempio, possono essere mantenuti come valori precisi, mentre 0,2 (= 1/5) e 0,3 (= 3/10) possono essere solo approssimazioni.

A causa di questa imprecisione, non è possibile basarsi sui risultati esatti quando si opera sui valori a virgola mobile. In particolare, due valori teoricamente uguali potrebbero presentare rappresentazioni leggermente diverse.

| Per confrontare le quantità a virgola mobile |
|---|
|1. calcolare il valore assoluto della differenza usando il <xref:System.Math.Abs%2A> metodo della <xref:System.Math> classe nello <xref:System> spazio dei nomi.<br />2. determinare una differenza massima accettabile, in modo che sia possibile considerare le due quantità come uguali per scopi pratici se la differenza non è maggiore.<br />3. confrontare il valore assoluto della differenza con la differenza accettabile.|

Nell'esempio seguente viene illustrato il confronto errato e corretto di due `Double` valori.

[!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]

Nell'esempio precedente viene utilizzato il <xref:System.Double.ToString%2A> metodo della <xref:System.Double> struttura in modo che sia possibile specificare una precisione maggiore rispetto a quella `CStr` utilizzata dalla parola chiave. Il valore predefinito è 15 cifre, ma il formato "G17" lo estende a 17 cifre.

## <a name="mod-operator-does-not-return-accurate-result"></a>L'operatore mod non restituisce risultati accurati

A causa dell'imprecisione dell'archiviazione a virgola mobile, l' [operatore mod](../../../language-reference/operators/mod-operator.md) può restituire un risultato imprevisto quando almeno uno degli operandi è a virgola mobile.

Il [tipo di dati Decimal](../../../language-reference/data-types/decimal-data-type.md) non utilizza la rappresentazione a virgola mobile. Molti numeri non esatti in `Single` e `Double` sono esatti in `Decimal` (ad esempio, 0,2 e 0,3). Sebbene l'aritmetica risulti più lenta in `Decimal` rispetto a virgola mobile, potrebbe valere la riduzione delle prestazioni per ottenere una maggiore precisione.

|Per trovare il resto integer delle quantità a virgola mobile|
|---|
|1. dichiarare le variabili come `Decimal` .<br />2. utilizzare il carattere di tipo letterale `D` per forzare i valori letterali in `Decimal` , nel caso in cui i valori siano troppo grandi per il `Long` tipo di dati.|

Nell'esempio seguente viene illustrata la potenziale imprecisione degli operandi a virgola mobile.

[!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]

Nell'esempio precedente viene utilizzato il <xref:System.Double.ToString%2A> metodo della <xref:System.Double> struttura in modo che sia possibile specificare una precisione maggiore rispetto a quella `CStr` utilizzata dalla parola chiave. Il valore predefinito è 15 cifre, ma il formato "G17" lo estende a 17 cifre.

Poiché `zeroPointTwo` è `Double` , il relativo valore per 0,2 è una frazione binaria ripetuta in modo infinito con un valore archiviato di 0.20000000000000001. La divisione di 2,0 per questa quantità restituisce 9.9999999999999995 con un resto di 0.19999999999999991.

Nell'espressione per `decimalRemainder` , il carattere di tipo letterale `D` impone entrambi gli operandi a `Decimal` e 0,2 presenta una rappresentazione precisa. Pertanto `Mod` , l'operatore restituisce il resto previsto di 0,0.

Si noti che non è sufficiente dichiarare `decimalRemainder` come `Decimal` . È inoltre necessario forzare i valori letterali a `Decimal` oppure utilizzarli per `Double` impostazione predefinita e `decimalRemainder` ricevere lo stesso valore non accurato di `doubleRemainder` .

## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Il tipo booleano non converte in modo accurato il tipo numerico

I valori [dei tipi di dati booleani](../../../language-reference/data-types/boolean-data-type.md) non vengono archiviati come numeri e i valori archiviati non sono destinati a essere equivalenti ai numeri. Per la compatibilità con le versioni precedenti, Visual Basic fornisce parole chiave di conversione ([funzione CType](../../../language-reference/functions/ctype-function.md),, `CBool` `CInt` e così via) per la conversione tra i `Boolean` tipi numerici e. Tuttavia, altri linguaggi a volte eseguono queste conversioni in modo diverso, come i metodi .NET Framework.

Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False` . Laddove possibile, è consigliabile limitare l'utilizzo delle `Boolean` variabili ai valori logici per i quali sono stati progettati. Se è necessario combinare `Boolean` e valori numerici, assicurarsi di conoscere il metodo di conversione selezionato.

### <a name="conversion-in-visual-basic"></a>Conversione in Visual Basic

Quando si usano le `CType` `CBool` parole chiave di conversione o per convertire i tipi di dati numerici in `Boolean` , 0 diventa `False` e tutti gli altri valori diventano `True` . Quando si convertono `Boolean` i valori in tipi numerici usando le parole chiave di conversione, `False` diventa 0 e `True` diventa-1.

### <a name="conversion-in-the-framework"></a>Conversione nel Framework

Il <xref:System.Convert.ToInt32%2A> metodo della <xref:System.Convert> classe nello <xref:System> spazio dei nomi converte `True` in + 1.

Se è necessario convertire un `Boolean` valore in un tipo di dati numerico, prestare attenzione al metodo di conversione utilizzato.

## <a name="character-literal-generates-compiler-error"></a>Il valore letterale carattere genera un errore del compilatore

In assenza di caratteri di tipo, Visual Basic presuppone i tipi di dati predefiniti per i valori letterali. Il tipo predefinito per un valore letterale carattere, racchiuso tra virgolette ( `" "` ), è `String` .

Il `String` tipo di dati non viene ampliato al [tipo di dati char](../../../language-reference/data-types/char-data-type.md). Ciò significa che se si desidera assegnare un valore letterale a una `Char` variabile, è necessario eseguire una conversione verso un tipo di testo più piccolo o forzare il valore letterale nel `Char` tipo.

|Per creare un valore letterale Char da assegnare a una variabile o a una costante|
|---|
|1. dichiarare la variabile o la costante come `Char` .<br />2. racchiudere il valore del carattere tra virgolette ( `" "` ).<br />3. seguire le virgolette doppie di chiusura con il carattere di tipo letterale `C` per forzare il valore letterale in `Char` . Questa operazione è necessaria se l'opzione di controllo del tipo ([istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md)) è `On` ed è auspicabile in ogni caso.|

Nell'esempio seguente vengono illustrate le assegnazioni non riuscite e corrette di un valore letterale a una `Char` variabile.

[!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]

Esiste sempre un rischio nell'utilizzo di conversioni verso un tipo di caratteri più piccolo, perché possono avere esito negativo in fase di esecuzione. Ad esempio, una conversione da `String` a `Char` può avere esito negativo se il `String` valore contiene più di un carattere. Pertanto, è preferibile programmare di utilizzare il `C` carattere tipo.

## <a name="string-conversion-fails-at-run-time"></a>Conversione di stringa non riuscita in fase di esecuzione

Il [tipo di dati String](../../../language-reference/data-types/string-data-type.md) partecipa a pochissime conversioni verso un tipo di dati più grande. `String`viene ampliato solo a se stesso e e `Object` solo `Char` e `Char()` ( `Char` matrice) si ampliano a `String` . Questo perché `String` variabili e costanti possono contenere valori che altri tipi di dati non possono contenere.

Quando l'opzione di controllo del tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) è `On` , il compilatore non consente tutte le conversioni implicite verso un tipo di caratteri più piccolo. Sono inclusi quelli che coinvolgono `String` . Il codice può comunque usare parole chiave di conversione `CStr` , ad esempio e la [funzione CType](../../../language-reference/functions/ctype-function.md), che indirizzano l'.NET Framework per tentare la conversione.

> [!NOTE]
> L'errore di conversione verso un tipo di ristringimento viene eliminato per le conversioni dagli elementi di una `For Each…Next` raccolta alla variabile di controllo del ciclo. Per ulteriori informazioni ed esempi, vedere la sezione relativa alle conversioni verso un tipo di dati più piccolo in [per ciascuna... Istruzione successiva](../../../language-reference/statements/for-each-next-statement.md).

### <a name="narrowing-conversion-protection"></a>Riduzione della protezione della conversione

Lo svantaggio delle conversioni verso un tipo di restringimento è che possono avere esito negativo in fase di esecuzione. Ad esempio, se una `String` variabile contiene un valore diverso da "true" o "false", non può essere convertito in `Boolean` . Se contiene caratteri di punteggiatura, la conversione in qualsiasi tipo numerico ha esito negativo. Se non si è certi che la `String` variabile contenga sempre valori che possono essere accettati dal tipo di destinazione, non provare a eseguire una conversione.

Se è necessario eseguire la conversione da `String` a un altro tipo di dati, la procedura più sicura consiste nel racchiudere la tentata conversione nell'oggetto [try... Rileva... Istruzione finally](../../../language-reference/statements/try-catch-finally-statement.md). In questo modo è possibile gestire un errore in fase di esecuzione.

### <a name="character-arrays"></a>Matrici di caratteri

Una singola `Char` e una matrice di `Char` elementi si ampliano a `String` . Tuttavia, non `String` si amplia a `Char()` . Per convertire un `String` valore in una `Char` matrice, è possibile usare il <xref:System.String.ToCharArray%2A> metodo della <xref:System.String?displayProperty=nameWithType> classe.

### <a name="meaningless-values"></a>Valori non significativi

In generale, `String` i valori non sono significativi in altri tipi di dati e la conversione è altamente artificiale e pericolosa. Laddove possibile, è consigliabile limitare l'utilizzo delle `String` variabili alle sequenze di caratteri per le quali sono progettate. Non scrivere mai codice che si basa su valori equivalenti di altri tipi.

## <a name="see-also"></a>Vedere anche

- [Tipi di dati](index.md)
- [Caratteri tipo](type-characters.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Conversioni di tipi in Visual Basic](type-conversions.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
- [CString](../../../language-reference/functions/type-conversion-functions.md)
- [Uso efficiente dei tipi di dati](efficient-use-of-data-types.md)
