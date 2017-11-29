---
title: 'Procedura: utilizzare puntatori per copiare una matrice di byte (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Procedura: utilizzare puntatori per copiare una matrice di byte (Guida per programmatori C#)
Nell'esempio seguente vengono usati i puntatori per copiare i byte da una matrice a un'altra.  
  
 In questo esempio viene usata la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), che consente l'uso di puntatori nel metodo `Copy`. Per dichiarare i puntatori nelle matrici di origine e destinazione, viene usata l'istruzione [fixed](../../../csharp/language-reference/keywords/fixed-statement.md), che *aggiunge* la posizione delle matrici di origine e destinazione nella memoria in modo che non vengano rimosse da Garbage Collection. I blocchi di memoria per le matrici vengono rimossi quando il blocco `fixed` è completato. Il metodo `Copy` in questo esempio usa la parola chiave `unsafe`. Deve pertanto essere compilato con l'opzione del compilatore **/unsafe**. Per impostare l'opzione in Visual Studio, fare clic con il pulsante destro del mouse sul nome del progetto e scegliere **Proprietà**. Nella scheda **Compilazione**, selezionare **Consenti codice di tipo unsafe**.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [/unsafe (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [Garbage Collection](../../../standard/garbage-collection/index.md)
