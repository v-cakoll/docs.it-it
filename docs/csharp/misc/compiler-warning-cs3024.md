---
title: Avviso del compilatore CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: 7515fdd7bc8f57890e3f1aac6303ed4607cc2249
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61688254"
---
# <a name="compiler-warning-cs3024"></a><span data-ttu-id="b8f17-102">Avviso del compilatore CS3024</span><span class="sxs-lookup"><span data-stu-id="b8f17-102">Compiler Warning CS3024</span></span>
<span data-ttu-id="b8f17-103">Il tipo di vincolo 'type' non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="b8f17-103">Constraint type 'type' is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="b8f17-104">Il compilatore genera questo avviso perché l'uso di un tipo non conforme a CLS come vincolo di tipo generico potrebbe impedire al codice scritto in alcuni linguaggi di usare la classe generica.</span><span class="sxs-lookup"><span data-stu-id="b8f17-104">The compiler issues this warning because the use of a non-CLS-compliant type as a generic type constraint could make it impossible for code written in some languages to consume your generic class.</span></span>  
  
### <a name="to-eliminate-this-warning"></a><span data-ttu-id="b8f17-105">Per eliminare l'avviso</span><span class="sxs-lookup"><span data-stu-id="b8f17-105">To eliminate this warning</span></span>  
  
1. <span data-ttu-id="b8f17-106">Usare un tipo conforme a CLS per il vincolo di tipo.</span><span class="sxs-lookup"><span data-stu-id="b8f17-106">Use a CLS-compliant type for the type constraint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8f17-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8f17-107">Example</span></span>  
 <span data-ttu-id="b8f17-108">L'esempio seguente genera l'errore CS3024 in diverse posizioni:</span><span class="sxs-lookup"><span data-stu-id="b8f17-108">The following example generates CS3024 in several locations:</span></span>  
  
```csharp  
// cs3024.cs  
// Compile with: /target:library  
 [assembly: System.CLSCompliant(true)]  
  
[type: System.CLSCompliant(false)]  
public class TestClass // CS3024  
{  
    public ushort us;  
}  
[type: System.CLSCompliant(false)]  
public interface ITest // CS3024  
{}  
public interface I<T> where T : TestClass  
{}  
public class TestClass_2<T> where T : ITest  
{}  
public class TestClass_3<T> : I<T> where T : TestClass  
{}  
public class TestClass_4<T> : TestClass_2<T> where T : ITest  
{}  
public class Test  
{  
    public static int Main()  
    {  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8f17-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8f17-109">See also</span></span>

- [<span data-ttu-id="b8f17-110">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="b8f17-110">Constraints on Type Parameters</span></span>](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
