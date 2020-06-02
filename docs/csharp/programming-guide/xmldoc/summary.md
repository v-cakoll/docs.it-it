---
title: <summary> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: e1a8c9d61e61eae7ba6bf7f0c1b9d2a8dc8a4171
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287207"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="ee78d-102">\<summary>(Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ee78d-102">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ee78d-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee78d-103">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="ee78d-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee78d-104">Parameters</span></span>

- `description`

  <span data-ttu-id="ee78d-105">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ee78d-105">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee78d-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ee78d-106">Remarks</span></span>

<span data-ttu-id="ee78d-107">Il `<summary>` tag deve essere usato per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="ee78d-107">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="ee78d-108">Utilizzare [\<remarks>](./remarks.md) per aggiungere informazioni aggiuntive a una descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="ee78d-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="ee78d-109">Usare l'[attributo cref](./cref-attribute.md) per abilitare strumenti della documentazione come [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.</span><span class="sxs-lookup"><span data-stu-id="ee78d-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="ee78d-110">Il testo per il `<summary>` tag è l'unica fonte di informazioni sul tipo in IntelliSense e viene visualizzato anche nella finestra di Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="ee78d-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="ee78d-111">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="ee78d-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="ee78d-112">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="ee78d-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="ee78d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee78d-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="ee78d-114">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="ee78d-114">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            <seealso cref="M:TestClass.Main"/>
            </summary>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a><span data-ttu-id="ee78d-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee78d-115">Example</span></span>

<span data-ttu-id="ee78d-116">Nell'esempio riportato di seguito viene illustrato come effettuare un riferimento `cref` a un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ee78d-116">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="ee78d-117">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="ee78d-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="ee78d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee78d-118">See also</span></span>

- [<span data-ttu-id="ee78d-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ee78d-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ee78d-120">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="ee78d-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
