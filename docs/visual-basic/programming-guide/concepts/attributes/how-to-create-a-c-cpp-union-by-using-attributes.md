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
ms.openlocfilehash: bcb5291737a9f4763f680daaf625c58d308423f8
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="83c66-102">Procedura: creare un'unione C/C++ tramite attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83c66-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="83c66-103">L'uso degli attributi consente di personalizzare la disposizione degli struct in memoria.</span><span class="sxs-lookup"><span data-stu-id="83c66-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="83c66-104">Ad esempio, tramite gli attributi `StructLayout(LayoutKind.Explicit)` e `FieldOffset` è possibile creare una struttura che in C/C++ è nota come unione.</span><span class="sxs-lookup"><span data-stu-id="83c66-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c66-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="83c66-105">Example</span></span>  
 <span data-ttu-id="83c66-106">In questo segmento di codice tutti i campi di `TestUnion` iniziano in corrispondenza della stessa posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="83c66-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="83c66-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="83c66-107">Example</span></span>  
 <span data-ttu-id="83c66-108">Nell'esempio seguente i campi iniziano in corrispondenza di posizioni diverse impostate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="83c66-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
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
  
 <span data-ttu-id="83c66-109">I due campi integer, `i1` e `i2`, condividono le stesse posizioni di memoria di `lg`.</span><span class="sxs-lookup"><span data-stu-id="83c66-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="83c66-110">Questo tipo di controllo sul layout degli struct è utile quando si usa la chiamata di piattaforma.</span><span class="sxs-lookup"><span data-stu-id="83c66-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c66-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83c66-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="83c66-112">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83c66-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="83c66-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="83c66-113">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="83c66-114">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83c66-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="83c66-115">Attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83c66-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="83c66-116">Creazione di attributi personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83c66-116">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="83c66-117">Accesso agli attributi tramite reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83c66-117">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
