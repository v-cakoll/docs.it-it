---
title: Tipi di puntatori - Guida per programmatori C#
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: ad6e6f17f9a8c30339a74b8ab41af3a99e716d3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745352"
---
# <a name="pointer-types-c-programming-guide"></a>Tipi di puntatori (Guida per programmatori C#)

In un contesto unsafe, un tipo può essere un tipo di puntatore, un tipo di valore o un tipo di riferimento. La dichiarazione di un tipo di puntatore può assumere uno dei seguenti formati:

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

Il tipo specificato prima di `*` in un tipo di puntatore viene chiamato **tipo referente**. Solo un [tipo non gestito](../../language-reference/builtin-types/unmanaged-types.md) può essere un tipo referente.

I tipi di puntatore non ereditano da [object](../../language-reference/builtin-types/reference-types.md). Non sono inoltre previste conversioni tra i tipi di puntatore e `object`. Con i puntatori non sono inoltre supportate le operazioni di boxing e unboxing. È tuttavia possibile eseguire conversioni tra tipi di puntatore diversi e tra tipi di puntatore e tipi integrali.

Quando si dichiarano più puntatori nella stessa dichiarazione, l'asterisco (*) viene scritto solo con il tipo sottostante. Non viene utilizzato come prefisso di ogni nome di puntatore. Ad esempio,

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

Un puntatore non può puntare a un riferimento o a uno [struct](../../language-reference/keywords/struct.md) che contiene riferimenti, perché un riferimento a un oggetto può essere sottoposto a processi di Garbage Collection anche se un puntatore punta a esso. Il Garbage Collector non tiene traccia degli altri tipi di puntatore che puntano all'oggetto.

Il valore della variabile del puntatore di tipo `myType*` è l'indirizzo di una variabile di tipo `myType`. Di seguito sono riportati alcuni esempi di dichiarazioni di tipi di puntatore:

|Esempio|Descrizione|
|-------------|-----------------|
|`int* p`|`p` è un puntatore a un Integer.|
|`int** p`|`p` è un puntatore a un puntatore a un Integer.|
|`int*[] p`|`p` è una matrice unidimensionale di puntatori a Integer.|
|`char* p`|`p` è un puntatore a un carattere.|
|`void* p`|`p` è un puntatore a un tipo sconosciuto.|

Per accedere al contenuto nella posizione a cui punta la variabile del puntatore, è possibile utilizzare *, ovvero l'operatore di riferimento indiretto a puntatore. Si consideri ad esempio la seguente dichiarazione:

```csharp
int* myVariable;
```

L'espressione `*myVariable` indica la variabile `int` individuata all'indirizzo contenuto in `myVariable`.

Gli argomenti [Istruzione fixed](../../language-reference/keywords/fixed-statement.md) e [Conversioni di puntatori](./pointer-conversions.md) includono diversi esempi di puntatori. L'esempio seguente usa la parola chiave `unsafe` e l'istruzione `fixed` e mostra come incrementare un puntatore interno.  È possibile incollare il codice nella funzione Main di un'applicazione console per eseguirlo. Questi esempi devono essere compilati con il set di opzioni del compilatore [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

Non è possibile applicare l'operatore di riferimento indiretto a un puntatore di tipo `void*`. È tuttavia possibile eseguire un cast per convertire un puntatore void in qualsiasi altro tipo e viceversa.

Un puntatore può essere `null`. Se l'operatore di riferimento indiretto viene applicato a un puntatore Null, si otterrà un comportamento definito dall'implementazione.

Tenere presente che il passaggio di puntatori tra metodi può generare un comportamento non definito. Prendere in considerazione un metodo che restituisce un puntatore a una variabile locale tramite un parametro `in`, `out` o `ref` oppure come risultato della funzione. Se il puntatore è stato impostato in un blocco fisso, la variabile a cui punta potrebbe non essere più fissa.

Nella tabella riportata di seguito sono elencati gli operatori e le istruzioni che è possibile utilizzare con i puntatori in un contesto unsafe:

|Operatore/istruzione|Utilizzo|
|-------------------------|---------|
|`*`|Esegue il riferimento indiretto al puntatore.|
|`->`|Accede a un membro di struct tramite un puntatore.|
|`[]`|Indicizza un puntatore.|
|`&`|Ottiene l'indirizzo di una variabile.|
|`++` e `--`|Incrementa e decrementa puntatori.|
|`+` e `-`|Utilizza l'aritmetica dei puntatori.|
|`==`, `!=`, `<`, `>`, `<=` e `>=`|Confronta puntatori.|
|[Operatore `stackalloc`](../../language-reference/operators/stackalloc.md)|Alloca memoria nello stack.|
|[Istruzione `fixed`](../../language-reference/keywords/fixed-statement.md)|Corregge temporaneamente una variabile per consentire di trovarne l'indirizzo.|

Per altre informazioni sugli operatori correlati ai puntatori, vedere [Operatori correlati ai puntatori](../../language-reference/operators/pointer-related-operators.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Tipi puntatore](~/_csharplang/spec/unsafe-code.md#pointer-types) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Codice unsafe e puntatori](index.md)
- [Conversioni puntatore](pointer-conversions.md)
- [Tipi riferimento](../../language-reference/keywords/reference-types.md)
- [Tipi di valore](../../language-reference/builtin-types/value-types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
