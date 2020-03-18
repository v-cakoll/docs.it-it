---
title: Creazione di attributi personalizzati (C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: c0f25adf0d562b659edaa8f36e72332fd0c1ee7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595414"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="c6962-102">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="c6962-102">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="c6962-103">È possibile creare attributi personalizzati definendo una classe Attribute, ovvero una classe che deriva direttamente o indirettamente da <xref:System.Attribute>, la quale semplifica e rende più rapida l'identificazione delle definizioni degli attributi nei metadati.</span><span class="sxs-lookup"><span data-stu-id="c6962-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="c6962-104">Si supponga di voler contrassegnare i tipi con il nome del programmatore che ha scritto il tipo.</span><span class="sxs-lookup"><span data-stu-id="c6962-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="c6962-105">Si potrebbe definire una classe Attribute `Author` personalizzata:</span><span class="sxs-lookup"><span data-stu-id="c6962-105">You might define a custom `Author` attribute class:</span></span>  
  
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
  
 <span data-ttu-id="c6962-106">Il nome della classe è il nome dell'attributo, `Author`.</span><span class="sxs-lookup"><span data-stu-id="c6962-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="c6962-107">La classe deriva da `System.Attribute`, quindi è una classe Attribute personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c6962-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="c6962-108">I parametri del costruttore sono parametri posizionali dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c6962-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="c6962-109">In questo esempio `name` è un parametro posizionale.</span><span class="sxs-lookup"><span data-stu-id="c6962-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="c6962-110">Tutte le proprietà o i campi pubblici di lettura/scrittura sono parametri denominati.</span><span class="sxs-lookup"><span data-stu-id="c6962-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="c6962-111">In questo caso `version` è l'unico parametro denominato.</span><span class="sxs-lookup"><span data-stu-id="c6962-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="c6962-112">Si noti l'uso dell'attributo `AttributeUsage` per rendere l'attributo `Author` valido solo per la classe e le dichiarazioni `struct`.</span><span class="sxs-lookup"><span data-stu-id="c6962-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="c6962-113">È possibile usare questo nuovo attributo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c6962-113">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="c6962-114">`AttributeUsage` ha un parametro denominato, `AllowMultiple`, che consente di rendere un attributo personalizzato monouso o multiuso.</span><span class="sxs-lookup"><span data-stu-id="c6962-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="c6962-115">Nell'esempio di codice seguente viene creato un attributo multiuso.</span><span class="sxs-lookup"><span data-stu-id="c6962-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 <span data-ttu-id="c6962-116">Nell'esempio vengono applicati a una classe più attributi dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="c6962-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6962-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6962-117">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="c6962-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c6962-118">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="c6962-119">Scrittura di attributi personalizzati</span><span class="sxs-lookup"><span data-stu-id="c6962-119">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="c6962-120">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="c6962-120">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="c6962-121">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="c6962-121">Attributes (C#)</span></span>](./index.md)
- <span data-ttu-id="c6962-122">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="c6962-122">[Accessing Attributes by Using Reflection (C#)](./accessing-attributes-by-using-reflection.md)</span></span>
- [<span data-ttu-id="c6962-123">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="c6962-123">AttributeUsage (C#)</span></span>](./attributeusage.md)
