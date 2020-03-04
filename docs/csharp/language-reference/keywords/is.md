---
title: is - Riferimenti per C#
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: a72f3b87e7558c594ef8a94bd0eadcc4664206b9
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239651"
---
# <a name="is-c-reference"></a>is (Riferimenti per C#)

L'operatore `is` controlla se il risultato di un'espressione è compatibile con un determinato tipo oppure (a partire da C# 7.0) controlla un'espressione rispetto a un criterio. Per informazioni sull'operatore di test del tipo `is`, vedere la sezione [Operatore is](../operators/type-testing-and-cast.md#is-operator) dell'articolo [Operatori di cast e di test del tipo](../operators/type-testing-and-cast.md).

## <a name="pattern-matching-with-is"></a>Criteri di ricerca con `is`

A partire da C# 7.0, le istruzioni `is` e [switch](switch.md) supportano i criteri di ricerca. La parola chiave `is` supporta i criteri seguenti:

- [Criterio del tipo](#type-pattern), che verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.

- [Criterio costante](#constant-pattern), che verifica se un'espressione restituisce un valore costante specificato.

- [Criterio var](#var-pattern), una corrispondenza che ha sempre esito positivo e associa il valore di un'espressione a una nuova variabile locale.

### <a name="type-pattern"></a>Criterio del tipo

Quando si usa il criterio del tipo per eseguire i criteri di ricerca, `is` verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo. È una semplice estensione dell'istruzione `is` che consente la valutazione e la conversione concisa del tipo. Il formato generale del criterio del tipo è `is`:

```csharp
   expr is type varname
```

Dove *expr* è un'espressione che restituisce un'istanza di un tipo, *Type* è il nome del tipo in cui il risultato di *expr* deve essere convertito e *VarName* è l'oggetto in cui il risultato di *expr* viene convertito se il `is` test è `true`. 

L'espressione `is` è `true` se *expr* non è `null` e una delle condizioni seguenti è true:

- *expr* è un'istanza dello stesso tipo di *type*.

- *expr* è un'istanza di un tipo che deriva da *type*. In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.

- *expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*. Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione. Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.

- *expr* è un'istanza di un tipo che implementa l'interfaccia *type*.

A partire da C# 7.1, *expr* può avere un tipo in fase di compilazione definito da un parametro di tipo generico e dai relativi vincoli.

Se *expr* è `true` e `is` viene usato con un'istruzione `if`, *varname* viene assegnato solo all'interno dell'istruzione `if`. L'ambito di *varname* va dall'espressione `is` alla fine del blocco che racchiude l'istruzione `if`. Se si usa *varname* in qualsiasi altra posizione, viene generato un errore in fase di compilazione perché è stata usata una variabile che non è stata assegnata.

Nell'esempio seguente viene usato il criterio del tipo `is` per specificare l'implementazione di un metodo <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> del tipo.

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

Senza criteri di ricerca, questo codice potrebbe essere scritto come segue. L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null`.  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

Anche il criterio del tipo `is` produce codice più compatto quando determina il tipo di un tipo di valore. Nell'esempio seguente viene usato il criterio del tipo `is` per determinare se un oggetto è un'istanza `Person` o `Dog` prima di visualizzare il valore di una proprietà appropriata.

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

Il codice equivalente senza criteri di ricerca richiede un'assegnazione separata che include un cast esplicito.

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a>Criterio costante

Quando si eseguono criteri di ricerca con il criterio costante, `is` verifica se un'espressione è uguale a una costante specificata. In C# 6 e versioni precedenti, il criterio costante è supportato per l'istruzione [switch](switch.md). A partire da C# 7.0 è supportato anche dall'istruzione `is`. La relativa sintassi è la seguente:

```csharp
   expr is constant
```

dove *expr* è l'espressione da valutare e *constant* è il valore da testare. *constant* può essere una delle espressioni costanti seguenti:

- Valore letterale.

- Il nome di una variabile `const` dichiarata.

- Una costante di enumerazione.

L'espressione costante viene valutata nel modo seguente:

- Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).

- In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.  

Nell'esempio seguente vengono combinati i criteri di tipo e costante per verificare se un oggetto è un'istanza `Dice` e, in tal caso, per determinare se il valore di un tiro di dadi è 6.

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

Verifica che `null` possa essere eseguito usando il criterio costante. La parola chiave `null` è supportata dall'istruzione `is`. La relativa sintassi è la seguente:

```csharp
   expr is null
```

L'esempio seguente illustra un confronto di controlli `null`:

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a>Criterio var

Una corrispondenza con il modello di `var` ha sempre esito positivo. La relativa sintassi è la seguente:

```csharp
   expr is var varname
```

Dove il valore di *expr* viene sempre assegnato a una variabile locale denominata *VarName*. *VarName* è una variabile dello stesso tipo del tipo in fase di compilazione di *expr*. 

Se *expr* restituisce `null`, l'espressione `is` produce `true` e assegna `null` a *VarName*. Il modello var è uno dei pochi usi di `is` che produce `true` per un valore di `null`.

È possibile usare il modello di `var` per creare una variabile temporanea in un'espressione booleana, come illustrato nell'esempio seguente:

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

Nell'esempio precedente, la variabile temporanea viene utilizzata per archiviare il risultato di un'operazione costosa. La variabile può quindi essere usata più volte.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#
  
Per altre informazioni, vedere la sezione [Operatore is](~/_csharplang/spec/expressions.md#the-is-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md) e le proposte di linguaggio C# seguenti:

- [Criteri di ricerca](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [Criteri di ricerca con generics](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Parole chiave C#](index.md)
- [Operatori di cast e di test del tipo](../operators/type-testing-and-cast.md)
