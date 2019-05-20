---
title: Operatori C#
ms.date: 04/30/2019
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
ms.openlocfilehash: 07ef96862c04b8245d8365c3d3b419d227e824c4
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876956"
---
# <a name="c-operators"></a>Operatori C#

C# fornisce una serie di operatori predefiniti supportati dai tipi incorporati. Ad esempio, gli [operatori aritmetici](arithmetic-operators.md) eseguono operazioni aritmetiche con gli operandi di tipi numerici incorporati e gli [operatori logici booleani](boolean-logical-operators.md) eseguono operazioni logiche con gli operandi [bool](../keywords/bool.md).

Un tipo definito dall'utente può eseguire l'overload di operatori specifici per definire il comportamento corrispondente per gli operandi di quel tipo. Per altre informazioni, vedere l'articolo sulla parola chiave [operator](../keywords/operator.md).

Le sezioni seguenti elencano gli operatori C# da quelli con la precedenza più alta a quelli con la più bassa. Gli operatori di ogni sezione condividono lo stesso livello di precedenza.

## <a name="primary-operators"></a>Operatori primari

Sono gli operatori con la precedenza più alta.

[x.y](member-access-operators.md#member-access-operator-): accesso ai membri.

[x?.y](member-access-operators.md#null-conditional-operators--and-): accesso ai membri condizionali null. Restituisce `null` se l'operando sul lato sinistro è `null`.

[x?[y]](member-access-operators.md#null-conditional-operators--and-): elemento di matrice condizionale null o accesso al tipo di indicizzatore. Restituisce `null` se l'operando sul lato sinistro è `null`.

[f(x)](member-access-operators.md#invocation-operator-): chiamata di metodo o chiamata a un delegato.

[a&#91;x&#93;](member-access-operators.md#indexer-operator-): elemento di matrice o accesso al tipo di indicizzatore.

[x++](arithmetic-operators.md#increment-operator-): incremento suffisso. Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).

[x--](arithmetic-operators.md#decrement-operator---): decremento suffisso. Restituisce il valore di x e quindi aggiorna la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).

[new](../keywords/new-operator.md): creazione di un'istanza del tipo.

[typeof](../keywords/typeof.md): restituisce l'oggetto <xref:System.Type> che rappresenta l'operando.

[checked](../keywords/checked.md): abilita il controllo di overflow per le operazioni con numeri interi.

[unchecked](../keywords/unchecked.md): disabilita il controllo di overflow per le operazioni con numeri interi. Questo è il comportamento predefinito per il compilatore.

[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): genera il valore predefinito del tipo T.

[nameof](../keywords/nameof.md): ottiene il nome semplice (non qualificato) di una variabile, di un tipo o di un membro come stringa costante.

[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md): dichiara e restituisce un'istanza di delegato.

[sizeof](../keywords/sizeof.md): restituisce le dimensioni in byte dell'operando type.

[stackalloc](../keywords/stackalloc.md): alloca un blocco di memoria nello stack.

[->](pointer-related-operators.md#pointer-member-access-operator--): riferimento indiretto al puntatore combinato con l'accesso ai membri.

## <a name="unary-operators"></a>Operatori unari

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[+x](addition-operator.md): restituisce il valore di x.

[-x](subtraction-operator.md): negazione numerica.

[\!x](boolean-logical-operators.md#logical-negation-operator-): negazione logica.

[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-): complemento bit per bit.

[~x](arithmetic-operators.md#increment-operator-): incremento prefisso. Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta maggiore (in genere aggiunge il numero intero 1).

[--x](arithmetic-operators.md#decrement-operator---): decremento prefisso. Restituisce il valore di x dopo avere aggiornato la posizione di archiviazione con il valore di x che risulta minore (in genere sottrae il numero intero 1).

[(T)x](invocation-operator.md): cast di tipo.

[await](../keywords/await.md): attende un oggetto `Task`.

[&x](pointer-related-operators.md#address-of-operator-): indirizzo di una variabile.

[*x](pointer-related-operators.md#pointer-indirection-operator-): riferimento indiretto al puntatore o dereferenziazione.

[Operatore true](../keywords/true-false-operators.md): restituisce il valore [bool](../keywords/bool.md) `true` per indicare che un operando è senza dubbio true.

[Operatore false](../keywords/true-false-operators.md): restituisce il valore [bool](../keywords/bool.md) `true` per indicare che un operando è senza dubbio false.

## <a name="multiplicative-operators"></a>Operatori moltiplicativi

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x * y](arithmetic-operators.md#multiplication-operator-): moltiplicazione.

[x / y](arithmetic-operators.md#division-operator-): divisione. Se gli operandi sono numeri interi, il risultato è un numero intero troncato verso zero (ad esempio, `-7 / 2 is -3`).

[x % y](arithmetic-operators.md#remainder-operator-): resto. Se gli operandi sono numeri interi, restituisce il resto della divisione di x per y.  Se `q = x / y` e `r = x % y`, allora `x = q * y + r` 

## <a name="additive-operators"></a>Operatori additivi

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x + y](arithmetic-operators.md#addition-operator-): addizione.

[x – y](arithmetic-operators.md#subtraction-operator--): sottrazione.

## <a name="shift-operators"></a>Operatori shift

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-): spostamento dei bit a sinistra e inserimento di zero a destra.

[x >> y](bitwise-and-shift-operators.md#right-shift-operator-): spostamento dei bit a destra. Se l'operando di sinistra è `int` o `long`, i bit di sinistra vengono riempiti con il bit più significativo. Se l'operando di sinistra è `uint` o `ulong`, i bit di sinistra vengono riempiti con zero.

## <a name="relational-and-type-testing-operators"></a>Operatori relazionali e operatori di test del tipo

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x \< y](comparison-operators.md#less-than-operator-): minore di (true se x è minore di y).

[x > y](comparison-operators.md#greater-than-operator-): maggiore di (true se x è maggiore di y).

[x \<= y](comparison-operators.md#less-than-or-equal-operator-): minore o uguale a.

[x >= y](comparison-operators.md#greater-than-or-equal-operator-): maggiore o uguale a.

[is](../keywords/is.md): compatibilità del tipo. Restituisce true se è possibile eseguire il cast dell'operando di sinistra valutato al tipo specificato nell'operando di destra (un tipo statico).

[as](../keywords/as.md): conversione di tipi. Restituisce il cast dell'operando di sinistra al tipo specificato dall'operando di destra (un tipo statico), ma `as` restituisce `null` dove `(T)x` genererebbe un'eccezione.

## <a name="equality-operators"></a>Operatori di uguaglianza

Questi operatori hanno una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x == y](equality-operators.md#equality-operator-): uguaglianza. Per impostazione predefinita, per i tipi di riferimento diversi da `string`, restituisce l'uguaglianza dei riferimenti (test dell'identità). Tuttavia, i tipi possono eseguire l'overload di `==`, quindi, se si prevede di testare l'identità, è meglio usare il metodo `ReferenceEquals` su `object`.

[x != y](equality-operators.md#inequality-operator-): diverso da. Vedere il commento per `==`. Se un tipo esegue l'overload di `==`, deve eseguire l'overload di `!=`.

## <a name="logical-and-operator"></a>AND (operatore logico)

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

`x & y`: [AND logico](boolean-logical-operators.md#logical-and-operator-) per gli operandi `bool` o [AND logico bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) per gli operandi dei tipi di dati integrali.

## <a name="logical-xor-operator"></a>Operatore XOR logico

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

`x ^ y`: [XOR logico](boolean-logical-operators.md#logical-exclusive-or-operator-) per gli operandi `bool` o [XOR logico bit per bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) per gli operandi dei tipi di dati integrali.

## <a name="logical-or-operator"></a>Operatore logico OR

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

`x | y`: [OR logico](boolean-logical-operators.md#logical-or-operator-) per gli operandi `bool` o [OR logico bit per bit](bitwise-and-shift-operators.md#logical-or-operator-) per gli operandi dei tipi di dati integrali.

## <a name="conditional-and-operator"></a>Operatore AND condizionale

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x && y](boolean-logical-operators.md#conditional-logical-and-operator-): AND logico. Se il primo operando è false, C# non valuta il secondo operando.

## <a name="conditional-or-operator"></a>Operatore OR condizionale

Questo operatore ha una precedenza più alta di quelli della sezione successiva e più bassa di quelli della sezione precedente.

[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-): OR logico. Se il primo operando è true, C# non valuta il secondo operando.

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

[x -= y](arithmetic-operators.md#compound-assignment): assegnazione di moltiplicazione. Moltiplica il valore di `y` per il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x -= y](arithmetic-operators.md#compound-assignment): assegnazione di divisione. Divide il valore di `x` per il valore di `y`, archivia il risultato in `x` e restituisce il nuovo valore.

[x %= y](arithmetic-operators.md#compound-assignment): assegnazione di resto. Divide il valore di `x` per il valore di `y`, archivia il resto in `x` e restituisce il nuovo valore.

[x &= y](boolean-logical-operators.md#compound-assignment): assegnazione dell'operatore AND. Applica AND al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x &#124;= y](boolean-logical-operators.md#compound-assignment): assegnazione dell'operatore OR. Applica OR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x ^= y](boolean-logical-operators.md#compound-assignment): assegnazione dell'operatore XOR. Applica XOR al valore di `y` con il valore di `x`, archivia il risultato in `x` e restituisce il nuovo valore.

[x <<= y](bitwise-and-shift-operators.md#compound-assignment): assegnazione di spostamento a sinistra. Sposta il valore di `x` verso sinistra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.

[x >>= y](bitwise-and-shift-operators.md#compound-assignment): assegnazione di spostamento a destra. Sposta il valore di `x` verso destra di `y` posti, archivia il risultato in `x` e restituisce il nuovo valore.

[=>](lambda-operator.md): dichiarazione lambda.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [C#](../../index.md)
- [Operatori che supportano l'overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [Parole chiave di C#](../keywords/index.md)
