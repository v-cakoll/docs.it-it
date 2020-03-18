---
title: protected internal - Riferimenti per C#
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 877df74b51fb859043171619f5687ecddb8409d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713196"
---
# <a name="protected-internal-c-reference"></a>protected internal (Riferimenti per C#)

La combinazione delle parole chiave `protected internal` è un modificatore di accesso ai membri. Un membro protected internal è accessibile dall'assembly corrente o dai tipi che derivano dalla classe che li contiene. Per un confronto di `protected internal` con altri modificatori di accesso, vedere [Livelli di accessibilità](accessibility-levels.md).

## <a name="example"></a>Esempio

Un membro protected internal di una classe base è accessibile da qualsiasi tipo all'interno dell'assembly che lo contiene. È inoltre accessibile in una classe derivata che si trova in un altro assembly solo se l'accesso viene eseguito tramite una variabile del tipo di classe derivata. Si consideri il segmento di codice di esempio seguente:

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`.
Il primo file contiene una classe base pubblica, `BaseClass`, e un'altra classe, `TestAccess`. `BaseClass` è proprietario di un membro protected internal, `myValue`, a cui si accede dal tipo `TestAccess`.
Nel secondo file un tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` produrrà un errore, mentre l'accesso a questo membro tramite un'istanza di una classe derivata, `DerivedClass`, avrà esito positivo.

I membri struct non possono essere `protected internal` perché struct non può essere ereditato.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori di accesso](access-modifiers.md)
- [Livelli di accessibilità](accessibility-levels.md)
- [Modificatori](index.md)
- [pubblico](public.md)
- [Privato](private.md)
- [Interno](internal.md)
- [Problemi di sicurezza per le parole chiave virtuali interne](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
