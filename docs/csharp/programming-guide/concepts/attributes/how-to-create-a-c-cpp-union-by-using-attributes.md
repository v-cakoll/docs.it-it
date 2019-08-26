---
title: "Procedura: Creare un'unione C-C++ tramite attributi (C#)"
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: fdadc9505b93f40c66001ac36345efada2edd270
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595368"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="08818-102">Procedura: Creare un'unione C/C++ tramite attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="08818-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="08818-103">L'uso degli attributi consente di personalizzare la disposizione degli struct in memoria.</span><span class="sxs-lookup"><span data-stu-id="08818-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="08818-104">Ad esempio, tramite gli attributi `StructLayout(LayoutKind.Explicit)` e `FieldOffset` è possibile creare una struttura che in C/C++ è nota come unione.</span><span class="sxs-lookup"><span data-stu-id="08818-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08818-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="08818-105">Example</span></span>  
 <span data-ttu-id="08818-106">In questo segmento di codice tutti i campi di `TestUnion` iniziano in corrispondenza della stessa posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="08818-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="08818-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="08818-107">Example</span></span>  
 <span data-ttu-id="08818-108">Nell'esempio seguente i campi iniziano in corrispondenza di posizioni diverse impostate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="08818-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
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
  
 <span data-ttu-id="08818-109">I due campi integer, `i1` e `i2`, condividono le stesse posizioni di memoria di `lg`.</span><span class="sxs-lookup"><span data-stu-id="08818-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="08818-110">Questo tipo di controllo sul layout degli struct è utile quando si usa la chiamata di piattaforma.</span><span class="sxs-lookup"><span data-stu-id="08818-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08818-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08818-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="08818-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="08818-112">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="08818-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="08818-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="08818-114">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="08818-114">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="08818-115">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="08818-115">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="08818-116">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="08818-116">Creating Custom Attributes (C#)</span></span>](./creating-custom-attributes.md)
- <span data-ttu-id="08818-117">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md) (Accesso agli attributi tramite reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="08818-117">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md)</span></span>
