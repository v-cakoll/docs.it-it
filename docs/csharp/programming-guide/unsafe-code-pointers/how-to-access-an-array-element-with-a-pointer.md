---
title: 'Procedura: accedere a un elemento di matrice mediante un puntatore (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 737c1d7fc0bc0a739de5c0a6cbc5dc09f813133e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a>Procedura: accedere a un elemento di matrice mediante un puntatore (Guida per programmatori C#)
In un contesto non sicuro è possibile accedere a un elemento in memoria usando l'accesso all'elemento mediante puntatore, come illustrato nell'esempio seguente:  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 L'espressione racchiusa tra parentesi quadre deve essere convertibile in modo implicito in `int`, `uint`, `long` o `ulong`. L'operazione p[e] è equivalente a *(p+e). Analogamente a C e C++, l'accesso all'elemento mediante puntatore non implica la verifica di errori relativi a valori non compresi nell'intervallo.  
  
## <a name="example"></a>Esempio  
 In questo esempio 123 posizioni di memoria vengono allocate a una matrice di caratteri, `charPointer`. La matrice viene usata per visualizzare le lettere in minuscolo e maiuscolo in due cicli [for](../../../csharp/language-reference/keywords/for.md).  
  
 Si noti che l'espressione `charPointer[i]` è equivalente all'espressione `*(charPointer + i)` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.  
  
 [!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
 **Lettere maiuscole:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Lettere minuscole:**  
**abcdefghijklmnopqrstuvwxyz**   
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipi](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
