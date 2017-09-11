---
title: Creazione di attributi personalizzati (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fbfc3f84f6287d233d475f01869dab63b937a521
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="2f78f-102">Creazione di attributi personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f78f-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="2f78f-103">È possibile creare attributi personalizzati definendo una classe attribute, una classe che deriva direttamente o indirettamente da <xref:System.Attribute>, rendendo identificazione delle definizioni degli attributi nei metadati più facili e veloci.</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="2f78f-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="2f78f-104">Si supponga che si desidera contrassegnare i tipi con il nome del programmatore che ha creato il tipo.</span><span class="sxs-lookup"><span data-stu-id="2f78f-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="2f78f-105">È possibile definire un oggetto personalizzato `Author` attributo classe:</span><span class="sxs-lookup"><span data-stu-id="2f78f-105">You might define a custom `Author` attribute class:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="2f78f-106">Il nome della classe è il nome dell'attributo, `Author`.</span><span class="sxs-lookup"><span data-stu-id="2f78f-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="2f78f-107">Deriva da `System.Attribute`, pertanto è una classe di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2f78f-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="2f78f-108">I parametri del costruttore sono parametri posizionali dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2f78f-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="2f78f-109">In questo esempio, `name` è un parametro posizionale.</span><span class="sxs-lookup"><span data-stu-id="2f78f-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="2f78f-110">Qualsiasi proprietà o campi pubblici di lettura / scrittura sono parametri denominate.</span><span class="sxs-lookup"><span data-stu-id="2f78f-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="2f78f-111">In questo caso, `version` è l'unico parametro denominato.</span><span class="sxs-lookup"><span data-stu-id="2f78f-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="2f78f-112">Si noti l'utilizzo di `AttributeUsage` attributo per rendere il `Author` attributo valido solo sulla classe e `Structure` dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="2f78f-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="2f78f-113">È possibile utilizzare il nuovo attributo, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2f78f-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="2f78f-114">`AttributeUsage`ha un parametro denominato `AllowMultiple`, che consente di rendere multiuso un attributo personalizzato a utilizzo singolo o multiuso.</span><span class="sxs-lookup"><span data-stu-id="2f78f-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="2f78f-115">Nell'esempio di codice seguente viene creato un attributo multiuso.</span><span class="sxs-lookup"><span data-stu-id="2f78f-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="2f78f-116">Nell'esempio di codice seguente, a una classe vengono applicati più attributi dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="2f78f-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  <span data-ttu-id="2f78f-117">Se la classe di attributo contiene una proprietà, tale proprietà deve essere in lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="2f78f-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f78f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f78f-118">See Also</span></span>  
 <span data-ttu-id="2f78f-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="2f78f-119"><xref:System.Reflection></span></span>   
<span data-ttu-id="2f78f-120"> [Guida per programmatori Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f78f-120"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="2f78f-121"> [Scrittura di attributi personalizzati](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span><span class="sxs-lookup"><span data-stu-id="2f78f-121"> [Writing Custom Attributes](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span></span>  
<span data-ttu-id="2f78f-122"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="2f78f-122"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="2f78f-123"> [Attributi (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="2f78f-123"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="2f78f-124"> [Accesso agli attributi tramite Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span><span class="sxs-lookup"><span data-stu-id="2f78f-124"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span></span>  
<span data-ttu-id="2f78f-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span><span class="sxs-lookup"><span data-stu-id="2f78f-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span></span>
