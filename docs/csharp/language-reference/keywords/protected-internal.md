---
title: protected internal (Riferimenti per C#)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 5ba2c811a1a4f095bcee65ed6678a7dc50fe94db
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172241"
---
# <a name="protected-internal-c-reference"></a>protected internal (Riferimenti per C#)
La combinazione delle parole chiave `protected internal` è un modificatore di accesso ai membri. Un membro protected internal è accessibile dall'assembly corrente o dai tipi che derivano dalla classe che li contiene. Per un confronto di `protected internal` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
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
        BaseClass baseObject = new BaseClass();
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
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`. Il primo file contiene una classe base pubblica, `BaseClass`, e un'altra classe, `TestAccess`. `BaseClass` è proprietario di un membro protected internal, `myValue`, a cui si accede dal tipo `TestAccess`. Nel secondo file un tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` produrrà un errore, mentre l'accesso a questo membro tramite un'istanza di una classe derivata, `DerivedClass`, avrà esito positivo. 

 I membri struct non possono essere `protected internal` perché struct non può essere ereditato.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [Problemi di sicurezza per le parole chiave virtuali interne](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
