---
title: Accesso agli attributi tramite reflection (C#)
description: Usare la reflection per ottenere informazioni definite con attributi personalizzati in C# usando il metodo GetCustomAttributes.
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: 9425141d64fd061d0c1f628228693cce02f7bfa0
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925098"
---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="25cb4-103">Accesso agli attributi tramite reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="25cb4-103">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="25cb4-104">La possibilità di definire attributi personalizzati e inserirli nel codice sorgente sarebbe di scarso valore senza un metodo per recuperare e usare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="25cb4-104">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="25cb4-105">Tramite l'uso di reflection, è possibile recuperare le informazioni definite con gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="25cb4-105">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="25cb4-106">Il metodo chiave è `GetCustomAttributes`, che restituisce una matrice di oggetti che rappresentano gli equivalenti in fase di esecuzione degli attributi di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="25cb4-106">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="25cb4-107">Questo metodo ha versioni diverse sottoposte a overload.</span><span class="sxs-lookup"><span data-stu-id="25cb4-107">This method has several overloaded versions.</span></span> <span data-ttu-id="25cb4-108">Per altre informazioni, vedere <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="25cb4-108">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="25cb4-109">Una specifica di attributo come la seguente:</span><span class="sxs-lookup"><span data-stu-id="25cb4-109">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="25cb4-110">è concettualmente equivalente a questa:</span><span class="sxs-lookup"><span data-stu-id="25cb4-110">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="25cb4-111">Il codice non viene tuttavia eseguito fino a quando non vengono eseguite query su `SampleClass` per gli attributi.</span><span class="sxs-lookup"><span data-stu-id="25cb4-111">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="25cb4-112">La chiamata a `GetCustomAttributes` in `SampleClass` causa la costruzione e l'inizializzazione di un oggetto `Author` come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="25cb4-112">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="25cb4-113">Se la classe ha altri attributi, gli altri oggetti di attributo vengono costruiti in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="25cb4-113">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="25cb4-114">`GetCustomAttributes` restituisce quindi l'oggetto `Author` e tutti gli altri oggetti di attributo in una matrice.</span><span class="sxs-lookup"><span data-stu-id="25cb4-114">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="25cb4-115">È quindi possibile eseguire l'iterazione di questa matrice, determinare gli attributi applicati in base al tipo di ogni elemento della matrice ed estrarre informazioni dagli oggetti di attributo.</span><span class="sxs-lookup"><span data-stu-id="25cb4-115">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25cb4-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="25cb4-116">Example</span></span>  
 <span data-ttu-id="25cb4-117">Questo è un esempio completo.</span><span class="sxs-lookup"><span data-stu-id="25cb4-117">Here is a complete example.</span></span> <span data-ttu-id="25cb4-118">Un attributo personalizzato viene definito, applicato a varie entità e recuperato tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="25cb4-118">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
```csharp  
// Multiuse attribute.  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // Multiuse attribute.  
]  
public class Author : System.Attribute  
{  
    string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
  
        // Default value.  
        version = 1.0;  
    }  
  
    public string GetName()  
    {  
        return name;  
    }  
}  
  
// Class with the Author attribute.  
[Author("P. Ackerman")]  
public class FirstClass  
{  
    // ...  
}  
  
// Class without the Author attribute.  
public class SecondClass  
{  
    // ...  
}  
  
// Class with multiple Author attributes.  
[Author("P. Ackerman"), Author("R. Koch", version = 2.0)]  
public class ThirdClass  
{  
    // ...  
}  
  
class TestAuthorAttribute  
{  
    static void Test()  
    {  
        PrintAuthorInfo(typeof(FirstClass));  
        PrintAuthorInfo(typeof(SecondClass));  
        PrintAuthorInfo(typeof(ThirdClass));  
    }  
  
    private static void PrintAuthorInfo(System.Type t)  
    {  
        System.Console.WriteLine("Author information for {0}", t);  
  
        // Using reflection.  
        System.Attribute[] attrs = System.Attribute.GetCustomAttributes(t);  // Reflection.  
  
        // Displaying output.  
        foreach (System.Attribute attr in attrs)  
        {  
            if (attr is Author)  
            {  
                Author a = (Author)attr;  
                System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version);  
            }  
        }  
    }  
}  
/* Output:  
    Author information for FirstClass  
       P. Ackerman, version 1.00  
    Author information for SecondClass  
    Author information for ThirdClass  
       R. Koch, version 2.00  
       P. Ackerman, version 1.00  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="25cb4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25cb4-119">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="25cb4-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="25cb4-120">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="25cb4-121">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="25cb4-121">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="25cb4-122">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="25cb4-122">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="25cb4-123">Attributi (C#)</span><span class="sxs-lookup"><span data-stu-id="25cb4-123">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="25cb4-124">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="25cb4-124">Creating Custom Attributes (C#)</span></span>](./creating-custom-attributes.md)
