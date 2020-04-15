---
title: Creazione di attributi personalizzati (C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: ec959723c339a13a40fd62388421ceacb736dfca
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389551"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="945fb-102">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="945fb-102">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="945fb-103">È possibile creare attributi personalizzati definendo una classe Attribute, ovvero una classe che deriva direttamente o indirettamente da <xref:System.Attribute>, la quale semplifica e rende più rapida l'identificazione delle definizioni degli attributi nei metadati.</span><span class="sxs-lookup"><span data-stu-id="945fb-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="945fb-104">Si supponga di voler contrassegnare i tipi con il nome del programmatore che ha scritto il tipo.</span><span class="sxs-lookup"><span data-stu-id="945fb-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="945fb-105">Si potrebbe definire una classe Attribute `Author` personalizzata:</span><span class="sxs-lookup"><span data-stu-id="945fb-105">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="945fb-106">Il nome della classe è il nome dell'attributo, `Author`.</span><span class="sxs-lookup"><span data-stu-id="945fb-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="945fb-107">La classe deriva da `System.Attribute`, quindi è una classe Attribute personalizzata.</span><span class="sxs-lookup"><span data-stu-id="945fb-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="945fb-108">I parametri del costruttore sono parametri posizionali dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="945fb-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="945fb-109">In questo esempio `name` è un parametro posizionale.</span><span class="sxs-lookup"><span data-stu-id="945fb-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="945fb-110">Tutte le proprietà o i campi pubblici di lettura/scrittura sono parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="945fb-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="945fb-111">In questo caso `version` è l'unico parametro denominato.</span><span class="sxs-lookup"><span data-stu-id="945fb-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="945fb-112">Si noti l'uso dell'attributo `AttributeUsage` per rendere l'attributo `Author` valido solo per la classe e le dichiarazioni `struct`.</span><span class="sxs-lookup"><span data-stu-id="945fb-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="945fb-113">È possibile usare questo nuovo attributo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="945fb-113">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="945fb-114">`AttributeUsage` ha un parametro denominato, `AllowMultiple`, che consente di rendere un attributo personalizzato monouso o multiuso.</span><span class="sxs-lookup"><span data-stu-id="945fb-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="945fb-115">Nell'esempio di codice seguente viene creato un attributo multiuso.</span><span class="sxs-lookup"><span data-stu-id="945fb-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 <span data-ttu-id="945fb-116">Nell'esempio vengono applicati a una classe più attributi dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="945fb-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="945fb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="945fb-117">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="945fb-118">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="945fb-118">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="945fb-119">Scrittura di attributi personalizzati</span><span class="sxs-lookup"><span data-stu-id="945fb-119">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="945fb-120">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="945fb-120">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="945fb-121">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="945fb-121">Attributes (C#)</span></span>](./index.md)
- <span data-ttu-id="945fb-122">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="945fb-122">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md)</span></span>
- [<span data-ttu-id="945fb-123">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="945fb-123">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
