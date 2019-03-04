---
title: <summary> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 12898d5cd10d9ecca4ec0fd1f7d06be0761b57b8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978553"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="35ab7-102">\<summary> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="35ab7-102">\<summary> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="35ab7-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35ab7-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35ab7-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="35ab7-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="35ab7-105">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="35ab7-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35ab7-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="35ab7-106">Remarks</span></span>  
 <span data-ttu-id="35ab7-107">Il tag \<summary> deve essere usato per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="35ab7-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="35ab7-108">Utilizzare [ \<osservazioni >](../../../csharp/programming-guide/xmldoc/remarks.md) per aggiungere informazioni supplementari alla descrizione di un tipo.</span><span class="sxs-lookup"><span data-stu-id="35ab7-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="35ab7-109">Usare l'[attributo cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) per abilitare strumenti della documentazione come [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.</span><span class="sxs-lookup"><span data-stu-id="35ab7-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="35ab7-110">Il testo del tag \<summary> rappresenta l'unica fonte di informazioni sul tipo in IntelliSense e viene visualizzato anche nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="35ab7-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="35ab7-111">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="35ab7-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="35ab7-112">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="35ab7-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35ab7-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="35ab7-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
 <span data-ttu-id="35ab7-114">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="35ab7-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="35ab7-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="35ab7-115">Example</span></span>  
 <span data-ttu-id="35ab7-116">Nell'esempio riportato di seguito viene illustrato come effettuare un riferimento `cref` a un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="35ab7-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]  
  
 <span data-ttu-id="35ab7-117">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="35ab7-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="35ab7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35ab7-118">See also</span></span>

- [<span data-ttu-id="35ab7-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="35ab7-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="35ab7-120">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="35ab7-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
