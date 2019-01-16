---
title: Operatori C#
ms.date: 04/04/2018
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 6380fa4ec99f598be0d01db1061900520e94d5f1
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333408"
---
# <a name="c-operators"></a>Operatori C#

C# fornisce diversi operatori, ovvero simboli che specificano quali operazioni (matematiche, indicizzazione, chiamate di funzione e così via) eseguire in un'espressione. È possibile eseguire l'[overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) di diversi operatori per cambiarne il significato quando vengono applicati a un tipo definito dall'utente.

Le operazioni sui tipi integrali (come `==`, `!=`, `<`, `>`, `&`, `|`) sono generalmente consentite sui tipi di enumerazione (`enum`).

Le sezioni seguenti elencano gli operatori C# da quelli con la precedenza più alta a quelli con la più bassa. Gli operatori di ogni sezione condividono lo stesso livello di precedenza.

## <a name="primary-operators"></a>Operatori primari

Sono gli operatori con la precedenza più alta.

[x.y](member-access-operator.md): accesso ai membri.

[x?.y](null-conditional-operators.md): accesso ai membri condizionali null. Restituisce `null` se l'operando sul lato sinistro è `null`.

[x?[y]](null-conditional-operators.md): accesso all'indice condizionale null. Restituisce `null` se l'operando sul lato sinistro è `null`.

[f(x)](invocation-operator.md): chiamata di funzione.

[a&#91;x&#93;](index-operator.md): indicizzazione oggetto aggregato.

[x++](increment-operator.md): incremento suffisso. Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).

[x--](decrement-operator.md): decremento suffisso. Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).

[new](../keywords/new-operator.md): creazione di un'istanza del tipo.

[typeof](../keywords/typeof.md): restituisce l'oggetto <xref:System.Type> che rappresenta l'operando.

[checked](../keywords/checked.md): abilita il controllo di overflow per le operazioni con numeri interi.

[unchecked](../keywords/unchecked.md): disabilita il controllo di overflow per le operazioni con numeri interi. Questo è il comportamento predefinito per il compilatore.

[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): genera il valore predefinito del tipo T.

[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md): dichiara e restituisce un'istanza di delegato.

[sizeof](../keywords/sizeof.md): restituisce le dimensioni in byte dell'operando type.

[->](dereference-operator.md): dereferenziazione puntatore combinata con l'accesso ai membri.

## <a name="unary-operators"></a>Operatori unari

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[+x](addition-operator.md): restituisce il valore di x.

[-x](subtraction-operator.md): negazione numerica.

[\!x](logical-negation-operator.md): negazione logica.

[~x](bitwise-complement-operator.md): complemento bit per bit.

[~x](increment-operator.md): incremento prefisso. Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).

[--x](decrement-operator.md): decremento prefisso. Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).

[(T)x](invocation-operator.md): cast di tipo.

[await](../keywords/await.md): attende un oggetto `Task`.

[&x](and-operator.md): indirizzo.

[*x](multiplication-operator.md): dereferenziazione.

## <a name="multiplicative-operators"></a>Operatori moltiplicativi

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x * y](multiplication-operator.md): moltiplicazione.

[x / y](division-operator.md): divisione. Se gli operandi sono numeri interi, il risultato è un numero intero troncato verso zero (ad esempio, `-7 / 2 is -3`).

[x % y](remainder-operator.md): resto. Se gli operandi sono numeri interi, restituisce il resto della divisione di x per y.  Se `q = x / y` e `r = x % y`, allora `x = q * y + r` 

## <a name="additive-operators"></a>Operatori additivi

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x + y](addition-operator.md): addizione.

[x – y](subtraction-operator.md): sottrazione.

## <a name="shift-operators"></a>Operatori shift

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x <\<  y](left-shift-operator.md): spostamento dei bit a sinistra e inserimento di zero a destra.

[x >> y](right-shift-operator.md): spostamento dei bit a destra. Se l'operando di sinistra è `int` o `long`, i bit di sinistra vengono riempiti con il bit più significativo. Se l'operando di sinistra è `uint` o `ulong`, i bit di sinistra vengono riempiti con zero.

## <a name="relational-and-type-testing-operators"></a>Operatori relazionali e operatori di test del tipo

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x \< y](less-than-operator.md): minore di (true se x è minore di y).

[x > y](greater-than-operator.md): maggiore di (true se x è maggiore di y).

[x \<= y](less-than-equal-operator.md): minore o uguale a.

[x >= y](greater-than-equal-operator.md): maggiore o uguale a.

[is](../keywords/is.md): compatibilità del tipo. Restituisce true se è possibile eseguire il cast dell'operando di sinistra valutato al tipo specificato nell'operando di destra (un tipo statico).

[as](../keywords/as.md): conversione di tipi. Restituisce il cast dell'operando di sinistra al tipo specificato dall'operando di destra (un tipo statico), ma `as` restituisce `null` dove `(T)x` genererebbe un'eccezione.

## <a name="equality-operators"></a>Operatori di uguaglianza

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x == y](equality-comparison-operator.md): uguaglianza. Per impostazione predefinita, per i tipi di riferimento diversi da `string`, restituisce l'uguaglianza dei riferimenti (test dell'identità). Tuttavia, i tipi possono eseguire l'overload di `==`, quindi, se si prevede di testare l'identità, è meglio usare il metodo `ReferenceEquals` su `object`.

[x != y](not-equal-operator.md): diverso da. Vedere il commento per `==`. Se un tipo esegue l'overload di `==`, deve eseguire l'overload di `!=`.

## <a name="logical-and-operator"></a>AND (operatore logico)

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x & y](and-operator.md): AND logico o bit per bit. Di solito è possibile usarlo con i tipi Integer e con i tipi `enum`.

## <a name="logical-xor-operator"></a>Operatore XOR logico

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x ^ y](xor-operator.md): XOR logico o bit per bit. Di solito è possibile usarlo con i tipi Integer e con i tipi `enum`.

## <a name="logical-or-operator"></a>Operatore logico OR

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x &#124; y](or-operator.md): OR logico o bit per bit. Di solito è possibile usarlo con i tipi Integer e con i tipi `enum`.

## <a name="conditional-and-operator"></a>Operatore AND condizionale

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x && y](conditional-and-operator.md): AND logico. Se il primo operando è false, C# non valuta il secondo operando.

## <a name="conditional-or-operator"></a>Operatore OR condizionale

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x &#124;&#124; y](conditional-or-operator.md): OR logico. Se il primo operando è true, C# non valuta il secondo operando.

## <a name="null-coalescing-operator"></a>Operatore null-coalescing

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x ?? y](null-coalescing-operator.md): restituisce `x` se è non `null`. In caso contrario, restituisce `y`.

## <a name="conditional-operator"></a>Operatore condizionale

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[t ? x : y](conditional-operator.md): se `t` di test è true, valuta e restituisce `x`. In caso contrario, valuta e restituisce `y`.

## <a name="assignment-and-lambda-operators"></a>Operatori di assegnazione e lambda

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x = y](assignment-operator.md): assegnazione.

[x = y](addition-assignment-operator.md): incremento. Aggiunge il valore di `y` al valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore. Se `x` designa un oggetto `event`, `y` deve essere una funzione appropriata che C# aggiunge come gestore eventi.

[x -= y](subtraction-assignment-operator.md): decremento. Sottrae il valore di `y` dal valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore. Se `x` designa un oggetto `event`, `y` deve essere una funzione appropriata che C# rimuove come gestore eventi.

[x -= y](multiplication-assignment-operator.md): assegnazione di moltiplicazione. Moltiplica il valore di `y` per il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x -= y](division-assignment-operator.md): assegnazione di divisione. Divide il valore di `x` per il valore di `y`, archivia il risultato in `x` e restituisce il nuovo valore.

[x %= y](remainder-assignment-operator.md): assegnazione di resto. Divide il valore di `x` per il valore di `y`, archivia il resto in `x` e restituisce il nuovo valore.

[x &= y](and-assignment-operator.md): assegnazione dell'operatore AND. Applica AND al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x &#124;= y](or-assignment-operator.md): assegnazione dell'operatore OR. Applica OR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x ^= y](xor-assignment-operator.md): assegnazione dell'operatore XOR. Applica XOR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x <<= y](left-shift-assignment-operator.md): assegnazione di spostamento a sinistra. Sposta il valore di `x` verso sinistra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.

[x >>= y](right-shift-assignment-operator.md): assegnazione di spostamento a destra. Sposta il valore di `x` verso destra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.

[=>](lambda-operator.md): dichiarazione lambda.

## <a name="arithmetic-overflow"></a>Overflow aritmetico

Gli operatori aritmetici ([+](addition-operator.md), [-](subtraction-operator.md), [*](multiplication-operator.md), [/](division-operator.md)) possono produrre risultati non compresi nell'intervallo dei valori possibili per il tipo numerico coinvolto. È consigliabile fare riferimento alla sezione di un particolare operatore per i dettagli, ma in generale:

- L'overflow aritmetico di interi genera un'eccezione <xref:System.OverflowException> o rimuove i bit più significativi del risultato. La divisione di interi per zero genera sempre un'eccezione <xref:System.DivideByZeroException>.

   Quando si verifica un overflow di interi, ciò che accade dipende dal contesto dell'esecuzione, che può essere [verificato o non verificato](../keywords/checked-and-unchecked.md). In un contesto verificato, viene generata un'eccezione <xref:System.OverflowException>. In un contesto non verificato, i bit più significativi del risultato vengono rimossi e l'esecuzione continua. C# consente dunque di scegliere se gestire o ignorare l'overflow. Per impostazione predefinita, le operazioni aritmetiche vengono eseguite in un contesto *non verificato*.

   Oltre alle operazioni aritmetiche, anche i cast da tipo integrale a tipo integrale possono causare l'overflow, ad esempio il cast di [long](../keywords/long.md) a [int](../keywords/int.md), e sono soggetti a esecuzione verificata o non verificata. Tuttavia, gli operatori bit per bit e gli operatori shift non causano mai l'overflow.

- L'overflow aritmetico a virgola mobile o la divisione per zero non genera mai un'eccezione, perché i tipi a virgola mobile si basano su IEEE 754 e quindi dispongono del provisioning per la rappresentazione dell'infinito e di NaN (Not a Number).

- L'overflow aritmetico [decimale](../keywords/decimal.md) genera sempre un'eccezione <xref:System.OverflowException>. La divisione di decimali per zero genera sempre un'eccezione <xref:System.DivideByZeroException>.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [C#](../../index.md)
- [Operatori che supportano l'overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [Parole chiave di C#](../keywords/index.md)