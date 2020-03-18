---
title: '#Direttiva del preprocessore if - Riferimenti per C#'
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: d047b88f202341a795834809d0b601706c30fcb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75899848"
---
# <a name="if-c-reference"></a>#if (Riferimenti per C

Quando il compilatore C# trova una direttiva `#if` seguita da una direttiva [#endif](preprocessor-endif.md), compila il codice tra tali direttive solo se il simbolo specificato è definito. Diversamente da C e C++, non è possibile assegnare un valore numerico a un simbolo. L'istruzione `#if` in Cè è booleana e verifica solo se il simbolo è stato definito o meno. Ad esempio:

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

È possibile utilizzare [==](../operators/equality-operators.md#equality-operator-) gli operatori (uguaglianza) e [!](../operators/equality-operators.md#inequality-operator-) , (disuguaglianza) `false`solo per verificare i valori `true` [bool](../builtin-types/bool.md) o . `true`indica che il simbolo è definito. L'istruzione `#if DEBUG` ha lo stesso significato di `#if (DEBUG == true)`. È possibile utilizzare le [&& (and)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (or)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-)e [! (non)](../operators/boolean-logical-operators.md#logical-negation-operator-) per valutare se sono stati definiti più simboli. È anche possibile raggruppare simboli e operatori tra parentesi.

## <a name="remarks"></a>Osservazioni

`#if`, insieme alle direttive [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md)e [#undef](preprocessor-undef.md) , consente di includere o escludere il codice in base all'esistenza di uno o più simboli. Questo può essere utile quando si compila il codice per una build di debug o per una configurazione specifica.

Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`.

`#define` consente di definire un simbolo. Usando poi il simbolo come espressione passata alla direttiva `#if`, l'espressione restituisce `true`.

È anche possibile definire un simbolo con l'opzione del compilatore [-define.](../compiler-options/define-compiler-option.md) Per rimuovere la definizione di un simbolo, è possibile usare [#undef](preprocessor-undef.md).

Un simbolo definito tramite `-define` o `#define` non provoca conflitti con una variabile avente lo stesso nome. Il nome di una variabile, infatti, non può essere passato a una direttiva del preprocessore e un simbolo può essere valutato solo da una direttiva del preprocessore.

L'ambito di un simbolo creato con `#define` è il file in cui è stato definito.

Il sistema di compilazione è inoltre a conoscenza di simboli del preprocessore predefiniti che rappresentano framework di [destinazione](../../../standard/frameworks.md) diversi nei progetti di tipo SDK. Questi simboli sono utili durante la creazione di applicazioni destinata a più di un'implementazione o versione di .NET.

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> Per i progetti .NET Framework tradizionali, è necessario configurare manualmente i simboli di compilazione condizionale per i diversi framework di destinazione in Visual Studio tramite le pagine delle proprietà del progetto.

Altri simboli predefiniti includono le costanti DEBUG e TRACE. È possibile sostituire i valori impostati per il progetto con `#define`. Il simbolo DEBUG, ad esempio, viene impostato automaticamente a seconda delle proprietà di configurazione della build (modalità "Debug" o "Versione").

## <a name="examples"></a>Esempi

L'esempio seguente illustra come definire un simbolo MYTEST su un file e quindi testare i valori dei simboli MYTEST e DEBUG. L'output di questo esempio dipende dal fatto che il progetto sia stato compilato con la modalità di configurazione Debug o Versione.

```csharp
#define MYTEST
using System;
public class MyClass
{
    static void Main()
    {
#if (DEBUG && !MYTEST)
        Console.WriteLine("DEBUG is defined");
#elif (!DEBUG && MYTEST)
        Console.WriteLine("MYTEST is defined");
#elif (DEBUG && MYTEST)
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else
        Console.WriteLine("DEBUG and MYTEST are not defined");
#endif
    }
}
```

L'esempio seguente illustra come eseguire test per framework di destinazione diversi, in modo da poter usare le API più recenti quando possibile:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore di C](index.md)
- [Procedura: compilare in modo condizionale con traccia e debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
