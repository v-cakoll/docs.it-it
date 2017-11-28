---
title: '&lt;include&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f4df6a23b2fe33b2390aef86891aedc6b04e464d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltincludegt-c-programming-guide"></a><span data-ttu-id="5833b-102">&lt;include&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5833b-102">&lt;include&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5833b-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5833b-103">Syntax</span></span>  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5833b-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="5833b-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="5833b-105">Nome del file XML che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="5833b-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="5833b-106">È possibile qualificare il nome del file con un percorso.</span><span class="sxs-lookup"><span data-stu-id="5833b-106">The file name can be qualified with a path.</span></span> <span data-ttu-id="5833b-107">Racchiudere `filename` tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="5833b-107">Enclose `filename` in single quotation marks (' ').</span></span>  
  
 `tagpath`  
 <span data-ttu-id="5833b-108">Percorso dei tag di `filename` che porta al `name` del tag.</span><span class="sxs-lookup"><span data-stu-id="5833b-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="5833b-109">Racchiudere il percorso tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="5833b-109">Enclose the path in single quotation marks (' ').</span></span>  
  
 `name`  
 <span data-ttu-id="5833b-110">Identificatore del nome contenuto nel tag che precede i commenti. `name` ha sempre un `id`.</span><span class="sxs-lookup"><span data-stu-id="5833b-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="5833b-111">ID del tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="5833b-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="5833b-112">Racchiudere l'ID tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="5833b-112">Enclose the ID in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5833b-113">Note</span><span class="sxs-lookup"><span data-stu-id="5833b-113">Remarks</span></span>  
 <span data-ttu-id="5833b-114">Il tag \<include> consente di fare riferimento ai commenti di un altro file per la descrizione dei tipi e dei membri del codice sorgente,</span><span class="sxs-lookup"><span data-stu-id="5833b-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="5833b-115">eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5833b-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="5833b-116">Inserendo la documentazione in un file separato, è possibile applicare alla documentazione il controllo del codice sorgente separatamente dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5833b-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="5833b-117">Una persona, ad esempio, può avere il file di codice sorgente estratto e un'altra il file della documentazione estratto.</span><span class="sxs-lookup"><span data-stu-id="5833b-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>  
  
 <span data-ttu-id="5833b-118">Il tag \<include> usa la sintassi XML XPath.</span><span class="sxs-lookup"><span data-stu-id="5833b-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="5833b-119">Per informazioni sulla personalizzazione dell'utilizzo di \<include>, consultare la documentazione relativa a XPath.</span><span class="sxs-lookup"><span data-stu-id="5833b-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5833b-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="5833b-120">Example</span></span>  
 <span data-ttu-id="5833b-121">In questo esempio vengono presi in considerazione più file.</span><span class="sxs-lookup"><span data-stu-id="5833b-121">This is a multifile example.</span></span> <span data-ttu-id="5833b-122">Di seguito è riportato il primo file, che usa \<include>:</span><span class="sxs-lookup"><span data-stu-id="5833b-122">The first file, which uses \<include>, is listed below:</span></span>  
  
 [!code-csharp[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 <span data-ttu-id="5833b-123">Il secondo file, xml_include_tag.doc, contiene i commenti alla documentazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="5833b-123">The second file, xml_include_tag.doc, contains the following documentation comments:</span></span>  
  
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
  
## <a name="program-output"></a><span data-ttu-id="5833b-124">Output di programma</span><span class="sxs-lookup"><span data-stu-id="5833b-124">Program Output</span></span>  
 <span data-ttu-id="5833b-125">L'output seguente viene generato quando si compilano le classi Test e Test2 con la riga di comando seguente: `/doc:DocFileName.xml.`. In Visual Studio, è possibile specificare l'opzione dei commenti XML alla documentazione nel riquadro Compilazione di Creazione progetti.</span><span class="sxs-lookup"><span data-stu-id="5833b-125">The following output is generated when you compile the Test and Test2 classes with the following command line: `/doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="5833b-126">Se il compilatore C# rileva il tag \<include>, la ricerca dei commenti alla documentazione verrà eseguita nel file xml_include_tag.doc anziché nel file di origine corrente.</span><span class="sxs-lookup"><span data-stu-id="5833b-126">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="5833b-127">Il compilatore genera quindi il file DocFileName.xml, che verrà usato dagli strumenti della documentazione come [Sandcastle](https://github.com/EWSoftware/SHFB) per realizzare la documentazione finale.</span><span class="sxs-lookup"><span data-stu-id="5833b-127">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5833b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5833b-128">See Also</span></span>  
 [<span data-ttu-id="5833b-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5833b-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5833b-130">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="5833b-130">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
