---
title: Restrizioni relative all'uso dei livelli di accessibilità - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 8082dbd7398b6634b68f1dd2887cd55d6798a5d9
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795157"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a>Restrizioni relative all'uso dei livelli di accessibilità (Riferimenti per C#)

Quando si specifica un tipo in una dichiarazione, verificare se il livello di accessibilità del tipo dipende dal livello di accessibilità di un membro o di un altro tipo. Ad esempio, la classe di base diretta deve essere accessibile almeno quanto la classe derivata. Le dichiarazioni seguenti causano un errore del compilatore perché la classe di base `BaseClass` è meno accessibile di `MyClass`:

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

Nella tabella seguente sono riepilogate le restrizioni relative ai livelli di accessibilità dichiarata.

|Contesto|Osservazioni|
|-------------|-------------|
|[Classi](../../programming-guide/classes-and-structs/classes.md)|La classe di base diretta di un tipo di classe deve essere accessibile almeno quanto il tipo di classe.|
|[Interfacce](../../programming-guide/interfaces/index.md)|Le interfacce di base esplicite di un tipo di interfaccia devono essere accessibili almeno quanto il tipo di interfaccia.|
|[Delegati](../../programming-guide/delegates/index.md)|Il tipo restituito e i tipi di parametro di un tipo delegato devono essere accessibili almeno quanto il tipo delegato.|
|[Costanti](../../programming-guide/classes-and-structs/constants.md)|Il tipo di una costante deve essere accessibile almeno quanto la costante.|
|[Fields](../../programming-guide/classes-and-structs/fields.md)|Il tipo di un campo deve essere accessibile almeno quanto il campo.|
|[Metodi](../../programming-guide/classes-and-structs/methods.md)|Il tipo restituito e i tipi di parametro di un metodo devono essere accessibili almeno quanto il metodo.|
|[Proprietà](../../programming-guide/classes-and-structs/properties.md)|Il tipo di una proprietà deve essere accessibile almeno quanto la proprietà.|
|[Events](../../programming-guide/events/index.md)|Il tipo di un evento deve essere accessibile almeno quanto l'evento.|
|[Indicizzatori](../../programming-guide/indexers/index.md)|Il tipo e i tipi di parametro di un indicizzatore devono essere accessibili almeno quanto l'indicizzatore.|
|[Operatori](../operators/index.md)|Il tipo restituito e i tipi di parametro di un operatore devono essere accessibili almeno quanto l'operatore.|
|[Costruttori](../../programming-guide/classes-and-structs/constructors.md)|I tipi di parametro di un costruttore devono essere accessibili almeno quanto il costruttore.|

## <a name="example"></a>Esempio

L'esempio seguente contiene dichiarazioni errate di tipi diversi. Il commento che segue ogni dichiarazione indica l'errore del compilatore previsto.

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori di accesso](access-modifiers.md)
- [Dominio di accessibilità](accessibility-domain.md)
- [Livelli di accessibilità](accessibility-levels.md)
- [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [pubblico](public.md)
- [privata](private.md)
- [protetto](protected.md)
- [internal](internal.md)
