---
title: '&lt;summary&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <summary>
- summary
dev_langs:
- CSharp
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd96e58494196fcfdeb46e9e59481666ec9466f3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltsummarygt-c-programming-guide"></a><span data-ttu-id="c6ef6-102">&lt;summary&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c6ef6-102">&lt;summary&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c6ef6-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6ef6-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6ef6-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6ef6-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c6ef6-105">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6ef6-106">Note</span><span class="sxs-lookup"><span data-stu-id="c6ef6-106">Remarks</span></span>  
 <span data-ttu-id="c6ef6-107">Il tag \<summary> deve essere usato per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="c6ef6-108">Utilizzare [ \<osservazioni >](../../../csharp/programming-guide/xmldoc/remarks.md) per aggiungere informazioni supplementari alla descrizione di un tipo.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="c6ef6-109">Utilizzare l'[attributo cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) per abilitare strumenti della documentazione come [Sandcastle](https://github.com/EWSoftware/SHFB) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="c6ef6-110">Il testo del tag \<summary> rappresenta l'unica fonte di informazioni sul tipo in IntelliSense e viene visualizzato anche nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="c6ef6-111">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="c6ef6-112">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="c6ef6-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ef6-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6ef6-113">Example</span></span>  
 <span data-ttu-id="c6ef6-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c6ef6-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]</span></span>  
  
 <span data-ttu-id="c6ef6-115">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-115">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="c6ef6-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6ef6-116">Example</span></span>  
 <span data-ttu-id="c6ef6-117">Nell'esempio riportato di seguito viene illustrato come effettuare un riferimento `cref` a un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-117">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 <span data-ttu-id="c6ef6-118">[!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c6ef6-118">[!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]</span></span>  
  
 <span data-ttu-id="c6ef6-119">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="c6ef6-119">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c6ef6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6ef6-120">See Also</span></span>  
 <span data-ttu-id="c6ef6-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6ef6-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c6ef6-122">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="c6ef6-122">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

