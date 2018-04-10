---
title: class (Riferimenti per C#)
ms.date: 07/18/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ae4b019ee88b6f331a76c750ab94fc76a3343adb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="class-c-reference"></a>class (Riferimenti per C#)

Le classi vengono dichiarate usando la parola chiave `class`, come illustrato nell'esempio seguente:

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates 
    // and nested classes go here.
}
```

## <a name="remarks"></a>Note
In C# è consentita solo l'eredità singola. In altre parole, una classe può ereditare l'implementazione solo da una classe di base singola. Una classe può tuttavia implementare più di un'interfaccia. La tabella seguente illustra esempi di ereditarietà di classi e di implementazione di interfacce:

|Ereditarietà|Esempio|
|-----------------|-------------|
|Nessuno|`class ClassA { }`|
|Single|`class DerivedClass: BaseClass { }`|
|Nessuna, implementa due interfacce|`class ImplClass: IFace1, IFace2 { }`|
|Singola, implementa una sola interfaccia|`class ImplDerivedClass: BaseClass, IFace1 { }`|

Una classe dichiarata direttamente all'interno di uno spazio dei nomi, non annidata all'interno di altre classi, può essere [public](../../../csharp/language-reference/keywords/public.md) o [internal](../../../csharp/language-reference/keywords/internal.md). Le classi sono `internal` per impostazione predefinita.

I membri di classe, incluse le classi annidate, possono essere [pubblica](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protetti](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), [privata](../../../csharp/language-reference/keywords/private.md), o `private protected`. I membri sono [private](../../../csharp/language-reference/keywords/private.md) per impostazione predefinita.

Per altre informazioni, vedere [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) (Modificatori di accesso).

È possibile dichiarare classi generiche che hanno parametri di tipo. Per altre informazioni, vedere [Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md) (Classi generiche).

Una classe può contenere dichiarazioni dei membri seguenti:

- [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [Costanti](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [Campi](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [Indicizzatori](../../../csharp/programming-guide/indexers/index.md)

- [Operatori](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [Eventi](../../../csharp/programming-guide/events/index.md)

- [Delegati](../../../csharp/programming-guide/delegates/index.md)

- [Classi](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [Interfacce](../../../csharp/programming-guide/interfaces/index.md)

- [Struct](../../../csharp/programming-guide/classes-and-structs/structs.md)

## <a name="example"></a>Esempio
L'esempio seguente illustra la dichiarazione di campi di classe, costruttori e metodi. Illustra anche la creazione di istanze di oggetti e la stampa dei dati di istanza. In questo esempio vengono dichiarate due classi. La prima classe `Child`, contiene due campi privati (`name` e `age`), due costruttori pubblici e un metodo pubblico. La seconda classe, `StringTest`, viene usata per contenere `Main`.

[!code-csharp[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]

## <a name="comments"></a>Commenti
Si noti che, nell'esempio precedente, i campi privati (`name` e `age`) sono accessibili solo tramite i metodi pubblici della classe `Child`. Ad esempio, non è possibile stampare il nome del figlio, dal metodo `Main`, usando un'istruzione simile alla seguente:

```csharp
Console.Write(child1.name);   // Error
```

L'accesso ai membri private di `Child` da `Main` sarebbe possibile solo se `Main` fosse un membro della classe.

I tipi dichiarati all'interno di una classe senza un modificatore di accesso vengono impostati automaticamente a `private`; in tal modo i membri dei dati in questo esempio sarebbero sempre `private`, anche se la parola chiave venisse rimossa.

Infine, si noti che per l'oggetto creato usando il costruttore predefinito (`child3`), il campo age (età) è stato inizializzato su zero per impostazione predefinita.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Tipi riferimento](../../../csharp/language-reference/keywords/reference-types.md)
