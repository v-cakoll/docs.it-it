---
title: Accesso agli attributi tramite reflection (C#)
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
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
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
ms.openlocfilehash: 36724c7b6a2a786aff837db5bcf2ad2ccfa39205
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="7b088-102">Accesso agli attributi tramite reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="7b088-102">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="7b088-103">La possibilità di definire attributi personalizzati e inserirli nel codice sorgente sarebbe di scarso valore senza un metodo per recuperare e usare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="7b088-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="7b088-104">Tramite l'uso di reflection, è possibile recuperare le informazioni definite con gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7b088-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="7b088-105">Il metodo chiave è `GetCustomAttributes`, che restituisce una matrice di oggetti che rappresentano gli equivalenti in fase di esecuzione degli attributi di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7b088-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="7b088-106">Questo metodo ha versioni diverse sottoposte a overload.</span><span class="sxs-lookup"><span data-stu-id="7b088-106">This method has several overloaded versions.</span></span> <span data-ttu-id="7b088-107">Per altre informazioni, vedere <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="7b088-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="7b088-108">Una specifica di attributo come la seguente:</span><span class="sxs-lookup"><span data-stu-id="7b088-108">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="7b088-109">è concettualmente equivalente a questa:</span><span class="sxs-lookup"><span data-stu-id="7b088-109">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="7b088-110">Il codice non viene tuttavia eseguito fino a quando non vengono eseguite query su `SampleClass` per gli attributi.</span><span class="sxs-lookup"><span data-stu-id="7b088-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="7b088-111">La chiamata a `GetCustomAttributes` in `SampleClass` causa la costruzione e l'inizializzazione di un oggetto `Author` come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7b088-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="7b088-112">Se la classe ha altri attributi, gli altri oggetti di attributo vengono costruiti in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="7b088-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="7b088-113">`GetCustomAttributes` restituisce quindi l'oggetto `Author` e tutti gli altri oggetti di attributo in una matrice.</span><span class="sxs-lookup"><span data-stu-id="7b088-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="7b088-114">È quindi possibile eseguire l'iterazione di questa matrice, determinare gli attributi applicati in base al tipo di ogni elemento della matrice ed estrarre informazioni dagli oggetti di attributo.</span><span class="sxs-lookup"><span data-stu-id="7b088-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b088-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b088-115">Example</span></span>  
 <span data-ttu-id="7b088-116">Questo è un esempio completo.</span><span class="sxs-lookup"><span data-stu-id="7b088-116">Here is a complete example.</span></span> <span data-ttu-id="7b088-117">Un attributo personalizzato viene definito, applicato a varie entità e recuperato tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="7b088-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7b088-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b088-118">See Also</span></span>  
 <span data-ttu-id="7b088-119"><xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="7b088-119"><xref:System.Reflection></span></span>   
 <span data-ttu-id="7b088-120"><xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="7b088-120"><xref:System.Attribute></span></span>   
 <span data-ttu-id="7b088-121">[Guida per programmatori C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b088-121">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7b088-122">[Recupero di informazioni memorizzate negli attributi](../../../../standard/attributes/retrieving-information-stored-in-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="7b088-122">[Retrieving Information Stored in Attributes](../../../../standard/attributes/retrieving-information-stored-in-attributes.md) </span></span>  
 <span data-ttu-id="7b088-123">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="7b088-123">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 <span data-ttu-id="7b088-124">[Attributi (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b088-124">[Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md) </span></span>  
 [<span data-ttu-id="7b088-125">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="7b088-125">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)

