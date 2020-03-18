---
title: <include> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 22d87559766c04e53141e843ee8768c8aab89a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156974"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="376c2-102">\<includere> (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="376c2-102">\<include> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="376c2-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="376c2-103">Syntax</span></span>

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a><span data-ttu-id="376c2-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="376c2-104">Parameters</span></span>

- `filename`

  <span data-ttu-id="376c2-105">Nome del file XML che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="376c2-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="376c2-106">Il nome file può essere qualificato con un percorso relativo al file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="376c2-106">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="376c2-107">Racchiudere `filename` tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="376c2-107">Enclose `filename` in single quotation marks (' ').</span></span>

- `tagpath`

  <span data-ttu-id="376c2-108">Percorso dei tag di `filename` che porta al `name` del tag.</span><span class="sxs-lookup"><span data-stu-id="376c2-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="376c2-109">Racchiudere il percorso tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="376c2-109">Enclose the path in single quotation marks (' ').</span></span>

- `name`

  <span data-ttu-id="376c2-110">Identificatore del nome contenuto nel tag che precede i commenti. `name` ha sempre un `id`.</span><span class="sxs-lookup"><span data-stu-id="376c2-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>

- `id`

<span data-ttu-id="376c2-111">ID del tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="376c2-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="376c2-112">Racchiudere l'ID tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="376c2-112">Enclose the ID in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="376c2-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="376c2-113">Remarks</span></span>

<span data-ttu-id="376c2-114">Il tag \<include> consente di fare riferimento ai commenti di un altro file per la descrizione dei tipi e dei membri del codice sorgente,</span><span class="sxs-lookup"><span data-stu-id="376c2-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="376c2-115">eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="376c2-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="376c2-116">Inserendo la documentazione in un file separato, è possibile applicare alla documentazione il controllo del codice sorgente separatamente dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="376c2-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="376c2-117">Una persona, ad esempio, può avere il file di codice sorgente estratto e un'altra il file della documentazione estratto.</span><span class="sxs-lookup"><span data-stu-id="376c2-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>

<span data-ttu-id="376c2-118">Il tag \<include> usa la sintassi XML XPath.</span><span class="sxs-lookup"><span data-stu-id="376c2-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="376c2-119">Per informazioni sulla personalizzazione dell'utilizzo di \<include>, consultare la documentazione relativa a XPath.</span><span class="sxs-lookup"><span data-stu-id="376c2-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>

## <a name="example"></a><span data-ttu-id="376c2-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="376c2-120">Example</span></span>

<span data-ttu-id="376c2-121">In questo esempio vengono presi in considerazione più file.</span><span class="sxs-lookup"><span data-stu-id="376c2-121">This is a multifile example.</span></span> <span data-ttu-id="376c2-122">Di seguito è riportato \<il primo file, che utilizza>.</span><span class="sxs-lookup"><span data-stu-id="376c2-122">The following is the first file, which uses \<include>.</span></span>

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

<span data-ttu-id="376c2-123">Il secondo file, *xml_include_tag.doc*, contiene i seguenti commenti relativi alla documentazione.</span><span class="sxs-lookup"><span data-stu-id="376c2-123">The second file, *xml_include_tag.doc*, contains the following documentation comments.</span></span>

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a><span data-ttu-id="376c2-124">Output del programma</span><span class="sxs-lookup"><span data-stu-id="376c2-124">Program output</span></span>

<span data-ttu-id="376c2-125">L'output seguente viene generato quando si compilano le classi Test e Test2 con la riga di comando seguente: `-doc:DocFileName.xml.`. In Visual Studio, è possibile specificare l'opzione dei commenti XML alla documentazione nel riquadro Compilazione di Creazione progetti.</span><span class="sxs-lookup"><span data-stu-id="376c2-125">The following output is generated when you compile the Test and Test2 classes with the following command line: `-doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="376c2-126">Se il compilatore C# rileva il tag \<include>, la ricerca dei commenti alla documentazione verrà eseguita nel file xml_include_tag.doc anziché nel file di origine corrente.</span><span class="sxs-lookup"><span data-stu-id="376c2-126">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="376c2-127">Il compilatore genera quindi il file DocFileName.xml, che verrà usato dagli strumenti della documentazione come [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per produrre la documentazione finale.</span><span class="sxs-lookup"><span data-stu-id="376c2-127">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a><span data-ttu-id="376c2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="376c2-128">See also</span></span>

- [<span data-ttu-id="376c2-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="376c2-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="376c2-130">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="376c2-130">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
