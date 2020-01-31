---
title: <summary> - C# Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 1ae3c17bef69a52b4d5852e09284929dc328bf8a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789666"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="0bd18-102">> Riepilogo \<(C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="0bd18-102">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="0bd18-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0bd18-103">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="0bd18-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="0bd18-104">Parameters</span></span>

- `description`

  <span data-ttu-id="0bd18-105">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0bd18-105">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0bd18-106">Note</span><span class="sxs-lookup"><span data-stu-id="0bd18-106">Remarks</span></span>

<span data-ttu-id="0bd18-107">Il tag \<summary> deve essere usato per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="0bd18-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="0bd18-108">Utilizzare [\<osservazioni >](./remarks.md) per aggiungere informazioni supplementari alla descrizione di un tipo.</span><span class="sxs-lookup"><span data-stu-id="0bd18-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="0bd18-109">Usare l'[attributo cref](./cref-attribute.md) per abilitare strumenti della documentazione come [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.</span><span class="sxs-lookup"><span data-stu-id="0bd18-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="0bd18-110">Il testo del tag \<summary> rappresenta l'unica fonte di informazioni sul tipo in IntelliSense e viene visualizzato anche nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="0bd18-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="0bd18-111">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="0bd18-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="0bd18-112">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="0bd18-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="0bd18-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bd18-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="0bd18-114">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="0bd18-114">The previous example produces the following XML file.</span></span>

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

## <a name="example"></a><span data-ttu-id="0bd18-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bd18-115">Example</span></span>

<span data-ttu-id="0bd18-116">Nell'esempio riportato di seguito viene illustrato come effettuare un riferimento `cref` a un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="0bd18-116">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="0bd18-117">L'esempio precedente produce il seguente XML.</span><span class="sxs-lookup"><span data-stu-id="0bd18-117">The previous example produces the following XML file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0bd18-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bd18-118">See also</span></span>

- [<span data-ttu-id="0bd18-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0bd18-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="0bd18-120">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="0bd18-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
