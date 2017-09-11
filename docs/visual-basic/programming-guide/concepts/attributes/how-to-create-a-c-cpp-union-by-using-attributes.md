---
title: 'Procedura: creare un&quot;unione C C++ tramite attributi (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 195dc0c64cb01e38ede0b7c34c30ca7912aea685
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="63f75-102">Procedura: creare un'unione C/C++ tramite attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63f75-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="63f75-103">Utilizzando gli attributi è possibile personalizzare come struct sono disposti nella memoria.</span><span class="sxs-lookup"><span data-stu-id="63f75-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="63f75-104">Ad esempio, è possibile creare ciò che viene definito un operatore union in C/C++ tramite il `StructLayout(LayoutKind.Explicit)` e `FieldOffset` gli attributi.</span><span class="sxs-lookup"><span data-stu-id="63f75-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63f75-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="63f75-105">Example</span></span>  
 <span data-ttu-id="63f75-106">In questo segmento di codice, tutti i campi di `TestUnion` start nella stessa posizione in memoria.</span><span class="sxs-lookup"><span data-stu-id="63f75-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="63f75-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="63f75-107">Example</span></span>  
 <span data-ttu-id="63f75-108">Di seguito è un altro esempio in cui campi iniziano in diversi imposta in modo esplicito i percorsi.</span><span class="sxs-lookup"><span data-stu-id="63f75-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
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
  
 <span data-ttu-id="63f75-109">I due campi integer, `i1` e `i2`, condividono le stesse posizioni di memoria di `lg`.</span><span class="sxs-lookup"><span data-stu-id="63f75-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="63f75-110">Questo tipo di controllo sul layout struttura è utile quando si utilizza la chiamata di piattaforma.</span><span class="sxs-lookup"><span data-stu-id="63f75-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f75-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63f75-111">See Also</span></span>  
 <span data-ttu-id="63f75-112"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="63f75-112"><xref:System.Reflection></span></span>   
 <span data-ttu-id="63f75-113"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="63f75-113"><xref:System.Attribute></span></span>   
<span data-ttu-id="63f75-114"> [Guida per programmatori Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="63f75-114"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="63f75-115"> [Attributi](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="63f75-115"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="63f75-116"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="63f75-116"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="63f75-117"> [Attributi (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="63f75-117"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="63f75-118"> [Creazione di attributi personalizzati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="63f75-118"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="63f75-119"> [Accesso agli attributi tramite Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="63f75-119"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
