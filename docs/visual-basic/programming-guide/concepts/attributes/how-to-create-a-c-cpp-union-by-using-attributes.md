---
title: 'Procedura: creare un''unione C C++ tramite attributi (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51d04c573e91a351c48edefebdb3d32fce1d306f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="62434-102">Procedura: creare un'unione C/C++ tramite attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62434-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="62434-103">L'uso degli attributi consente di personalizzare la disposizione degli struct in memoria.</span><span class="sxs-lookup"><span data-stu-id="62434-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="62434-104">Ad esempio, tramite gli attributi `StructLayout(LayoutKind.Explicit)` e `FieldOffset` è possibile creare una struttura che in C/C++ è nota come unione.</span><span class="sxs-lookup"><span data-stu-id="62434-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62434-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="62434-105">Example</span></span>  
 <span data-ttu-id="62434-106">In questo segmento di codice tutti i campi di `TestUnion` iniziano in corrispondenza della stessa posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="62434-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a><span data-ttu-id="62434-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="62434-107">Example</span></span>  
 <span data-ttu-id="62434-108">Nell'esempio seguente i campi iniziano in corrispondenza di posizioni diverse impostate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="62434-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(  
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 <span data-ttu-id="62434-109">I due campi integer, `i1` e `i2`, condividono le stesse posizioni di memoria di `lg`.</span><span class="sxs-lookup"><span data-stu-id="62434-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="62434-110">Questo tipo di controllo sul layout degli struct è utile quando si usa la chiamata di piattaforma.</span><span class="sxs-lookup"><span data-stu-id="62434-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62434-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62434-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="62434-112">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62434-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="62434-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="62434-113">Attributes</span></span>](../../../../standard/attributes/index.md)  
 [<span data-ttu-id="62434-114">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62434-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="62434-115">Attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62434-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="62434-116">Creazione di attributi personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62434-116">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="62434-117">Accesso agli attributi tramite reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62434-117">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
