---
title: private protected (informazioni di riferimento su C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: a73d61712075cf24d2b94c505104df1fade629e9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713209"
---
# <a name="private-protected-c-reference"></a>private protected (informazioni di riferimento su C#)

La combinazione delle parole chiave `private protected` è un modificatore di accesso ai membri. Un membro protetto privato è accessibile per i tipi derivati dalla classe che lo contiene, ma solo all'interno dell'assembly che lo contiene. Per un confronto di `private protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](accessibility-levels.md).

> [!NOTE]
> Il modificatore di accesso `private protected` è valido in C# versione 7.2 e versioni successive.

## <a name="example"></a>Esempio

Un membro protetto privato di una classe base è accessibile dai tipi derivati nell'assembly che lo contiene solo se il tipo statico della variabile è il tipo della classe derivata. Si consideri il segmento di codice di esempio seguente:  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;  

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`.
Il primo file contiene una classe base pubblica, `BaseClass`, e un tipo derivato, `DerivedClass1`. `BaseClass` è proprietaria di un membro protetto privato, `myValue`, a cui `DerivedClass1` prova ad accedere in due modi. Il primo tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` genererà un errore. Il tentativo di usarlo come membro ereditato in `DerivedClass1` avrà, tuttavia, esito positivo.
Nel secondo file un tentativo di accedere a `myValue` come membro ereditato di `DerivedClass2` genererà un errore, perché è accessibile solo per i tipi derivati in Assembly1.

I membri struct non possono essere `private protected` perché struct non può essere ereditato.  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori di accesso](access-modifiers.md)
- [Livelli di accessibilità](accessibility-levels.md)
- [Modificatori](index.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Problemi di sicurezza per le parole chiave virtuali interne](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
