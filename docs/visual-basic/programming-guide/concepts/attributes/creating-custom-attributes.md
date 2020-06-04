---
title: Creazione di attributi personalizzati
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 84b400c2fa1b2d4019eec32092f954d680e64978
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400694"
---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="9e49e-102">Creazione di attributi personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e49e-102">Creating Custom Attributes (Visual Basic)</span></span>

<span data-ttu-id="9e49e-103">È possibile creare attributi personalizzati definendo una classe Attribute, ovvero una classe che deriva direttamente o indirettamente da <xref:System.Attribute>, la quale semplifica e rende più rapida l'identificazione delle definizioni degli attributi nei metadati.</span><span class="sxs-lookup"><span data-stu-id="9e49e-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="9e49e-104">Si supponga di voler contrassegnare i tipi con il nome del programmatore che ha scritto il tipo.</span><span class="sxs-lookup"><span data-stu-id="9e49e-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="9e49e-105">Si potrebbe definire una classe Attribute `Author` personalizzata:</span><span class="sxs-lookup"><span data-stu-id="9e49e-105">You might define a custom `Author` attribute class:</span></span>

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

<span data-ttu-id="9e49e-106">Il nome della classe è il nome dell'attributo, `Author`.</span><span class="sxs-lookup"><span data-stu-id="9e49e-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="9e49e-107">La classe deriva da `System.Attribute`, quindi è una classe Attribute personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9e49e-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="9e49e-108">I parametri del costruttore sono parametri posizionali dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9e49e-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="9e49e-109">In questo esempio `name` è un parametro posizionale.</span><span class="sxs-lookup"><span data-stu-id="9e49e-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="9e49e-110">Tutte le proprietà o i campi pubblici di lettura/scrittura sono parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="9e49e-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="9e49e-111">In questo caso `version` è l'unico parametro denominato.</span><span class="sxs-lookup"><span data-stu-id="9e49e-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="9e49e-112">Si noti l'uso dell'attributo `AttributeUsage` per rendere l'attributo `Author` valido solo per la classe e le dichiarazioni `Structure`.</span><span class="sxs-lookup"><span data-stu-id="9e49e-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>

<span data-ttu-id="9e49e-113">È possibile usare questo nuovo attributo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9e49e-113">You could use this new attribute as follows:</span></span>

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

<span data-ttu-id="9e49e-114">`AttributeUsage` ha un parametro denominato, `AllowMultiple`, che consente di rendere un attributo personalizzato monouso o multiuso.</span><span class="sxs-lookup"><span data-stu-id="9e49e-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="9e49e-115">Nell'esempio di codice seguente viene creato un attributo multiuso.</span><span class="sxs-lookup"><span data-stu-id="9e49e-115">In the following code example, a multiuse attribute is created.</span></span>

```vb
' multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
```

<span data-ttu-id="9e49e-116">Nell'esempio vengono applicati a una classe più attributi dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="9e49e-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>

```vb
<Author("P. Ackerman", Version:=1.1),
Author("R. Koch", Version:=1.2)>
Class SampleClass
    ' P. Ackerman's code goes here...
    ' R. Koch's code goes here...
End Class
```

> [!NOTE]
> <span data-ttu-id="9e49e-117">Se la classe Attribute contiene una proprietà, tale proprietà deve essere di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="9e49e-117">If your attribute class contains a property, that property must be read-write.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e49e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e49e-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="9e49e-119">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e49e-119">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="9e49e-120">Scrittura di attributi personalizzati</span><span class="sxs-lookup"><span data-stu-id="9e49e-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="9e49e-121">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e49e-121">Reflection (Visual Basic)</span></span>](../reflection.md)
- [<span data-ttu-id="9e49e-122">Attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e49e-122">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- [<span data-ttu-id="9e49e-123">Accesso agli attributi tramite reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e49e-123">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="9e49e-124">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e49e-124">AttributeUsage (Visual Basic)</span></span>](attributeusage.md)
