---
title: 'Procedura: Creare un''unione C-C++ tramite attributi (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4532829080d994cf4cec92d64a12e3bf1890dc6a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="ce822-102">Procedura: Creare un'unione C-C++ tramite attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="ce822-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="ce822-103">L'uso degli attributi consente di personalizzare la disposizione degli struct in memoria.</span><span class="sxs-lookup"><span data-stu-id="ce822-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="ce822-104">Ad esempio, tramite gli attributi `StructLayout(LayoutKind.Explicit)` e `FieldOffset` è possibile creare una struttura che in C/C++ è nota come unione.</span><span class="sxs-lookup"><span data-stu-id="ce822-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce822-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce822-105">Example</span></span>  
 <span data-ttu-id="ce822-106">In questo segmento di codice tutti i campi di `TestUnion` iniziano in corrispondenza della stessa posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="ce822-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a><span data-ttu-id="ce822-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce822-107">Example</span></span>  
 <span data-ttu-id="ce822-108">Nell'esempio seguente i campi iniziano in corrispondenza di posizioni diverse impostate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ce822-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 <span data-ttu-id="ce822-109">I due campi integer, `i1` e `i2`, condividono le stesse posizioni di memoria di `lg`.</span><span class="sxs-lookup"><span data-stu-id="ce822-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="ce822-110">Questo tipo di controllo sul layout degli struct è utile quando si usa la chiamata di piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ce822-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce822-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce822-111">See Also</span></span>  
 <span data-ttu-id="ce822-112"><xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="ce822-112"><xref:System.Reflection></span></span>   
 <span data-ttu-id="ce822-113"><xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="ce822-113"><xref:System.Attribute></span></span>   
 <span data-ttu-id="ce822-114">[Guida per programmatori C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce822-114">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ce822-115">[Attributi](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="ce822-115">[Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
 <span data-ttu-id="ce822-116">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="ce822-116">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 <span data-ttu-id="ce822-117">[Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)  (Attributi (C#))</span><span class="sxs-lookup"><span data-stu-id="ce822-117">[Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md) </span></span>  
 <span data-ttu-id="ce822-118">[Creazione di attributi personalizzati (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ce822-118">[Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
 <span data-ttu-id="ce822-119">[Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Accesso agli attributi tramite reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="ce822-119">[Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>

