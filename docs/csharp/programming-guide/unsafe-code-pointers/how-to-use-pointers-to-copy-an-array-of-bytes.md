---
title: 'Procedura: utilizzare puntatori per copiare una matrice di byte (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 808a74f75e4dcbcec47735d98063138e2c7456e5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="f45fc-102">Procedura: utilizzare puntatori per copiare una matrice di byte (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f45fc-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="f45fc-103">Nell'esempio seguente vengono usati i puntatori per copiare i byte da una matrice a un'altra.</span><span class="sxs-lookup"><span data-stu-id="f45fc-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="f45fc-104">In questo esempio viene usata la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), che consente l'uso di puntatori nel metodo `Copy`.</span><span class="sxs-lookup"><span data-stu-id="f45fc-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="f45fc-105">Per dichiarare i puntatori nelle matrici di origine e destinazione, viene usata l'istruzione [fixed](../../../csharp/language-reference/keywords/fixed-statement.md),</span><span class="sxs-lookup"><span data-stu-id="f45fc-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="f45fc-106">che *aggiunge* la posizione delle matrici di origine e destinazione nella memoria in modo che non vengano rimosse da Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f45fc-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="f45fc-107">I blocchi di memoria per le matrici vengono rimossi quando il blocco `fixed` è completato.</span><span class="sxs-lookup"><span data-stu-id="f45fc-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="f45fc-108">Il metodo `Copy` in questo esempio usa la parola chiave `unsafe`. Deve pertanto essere compilato con l'opzione del compilatore **/unsafe**.</span><span class="sxs-lookup"><span data-stu-id="f45fc-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="f45fc-109">Per impostare l'opzione in Visual Studio, fare clic con il pulsante destro del mouse sul nome del progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f45fc-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="f45fc-110">Nella scheda **Compilazione**, selezionare **Consenti codice di tipo unsafe**.</span><span class="sxs-lookup"><span data-stu-id="f45fc-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f45fc-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f45fc-111">Example</span></span>  
 <span data-ttu-id="f45fc-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f45fc-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span></span>  
  
 <span data-ttu-id="f45fc-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f45fc-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f45fc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f45fc-114">See Also</span></span>  
 <span data-ttu-id="f45fc-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f45fc-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f45fc-116">[Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="f45fc-116">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="f45fc-117">[-unsafe (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="f45fc-117">[/unsafe (C# Compiler Options)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span></span>  
 [<span data-ttu-id="f45fc-118">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="f45fc-118">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

