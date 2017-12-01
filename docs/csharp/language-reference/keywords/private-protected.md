---
title: privato protetto (riferimenti per c#)
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a>privato protetto (riferimenti per c#)
Il `private protected` combinazione di parole chiave è un modificatore di accesso di membro. Un membro protetto privato è accessibile da tipi derivati dalla classe di appartenenza, ma solo all'interno del relativo assembly che lo contiene. Per un confronto di `private protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Esempio  
 Un membro privato protetto di una classe base è accessibile da tipi derivati nel relativo assembly contenitore solo se il tipo statico della variabile è il tipo di classe derivata. Si consideri il segmento di codice di esempio seguente:  
  
 ```
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
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
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
 Questo esempio contiene due file, `Assembly1.cs` e `Assembly2.cs`. Il primo file contiene una classe base pubblica, `BaseClass`e un tipo derivato da esso, `DerivedClass1`. `BaseClass`proprietario di un membro privato protetto, `myValue`, che `DerivedClass1` tenta di accedere in due modi. Il primo tentativo di accedere a `myValue` tramite un'istanza di `BaseClass` genererà un errore. Tuttavia, il tentativo di utilizzo di un membro ereditato in `DerivedClass1` avrà esito positivo.
Nel secondo file, un tentativo di accedere a `myValue` di un membro ereditato di `DerivedClass2` genererà un errore, in quanto sono solo accessibili dai tipi derivati in Assembly1. 

 I membri struct non possono essere `private protected` perché lo struct non può essere ereditato.  
  
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
 [Problemi di sicurezza per parole chiave virtuali interne](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
