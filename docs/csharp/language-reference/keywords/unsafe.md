---
title: unsafe (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: c476bdcea4993b27c0e8f8148a985f18a43ba09b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="unsafe-c-reference"></a>unsafe (Riferimenti per C#)
La parola chiave `unsafe` denota un contesto unsafe, necessario per qualsiasi operazione che interessa i puntatori. Per altre informazioni, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 È possibile usare il modificatore `unsafe` nella dichiarazione di un tipo o di un membro. L'intera estensione testuale del tipo o membro viene pertanto considerato come contesto unsafe. Ad esempio, il seguente è un metodo dichiarato con il modificatore `unsafe`:  
  
```csharp  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 L'ambito del contesto unsafe si estende dall'elenco di parametri alla fine del metodo, in modo tale che i puntatori possano essere usati anche nell'elenco dei parametri:  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 È anche possibile usare un blocco unsafe per consentire l'uso di un codice unsafe all'interno del blocco. Ad esempio:  
  
```csharp  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Per compilare codice unsafe, è necessario specificare l'opzione del compilatore [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md). Il codice unsafe non è verificabile da Common Language Runtime.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Buffer a dimensione fissa](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
