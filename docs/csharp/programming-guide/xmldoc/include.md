---
title: '&lt;include&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs:
- CSharp
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0cabcc25c4e35027c600e4af2bccfad7f9db1514
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="ltincludegt-c-programming-guide"></a><span data-ttu-id="fcfbe-102">&lt;include&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="fcfbe-102">&lt;include&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="fcfbe-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcfbe-103">Syntax</span></span>  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcfbe-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="fcfbe-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="fcfbe-105">Nome del file XML che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="fcfbe-106">È possibile qualificare il nome del file con un percorso.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-106">The file name can be qualified with a path.</span></span> <span data-ttu-id="fcfbe-107">Racchiudere `filename` tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="fcfbe-107">Enclose `filename` in single quotation marks (' ').</span></span>  
  
 `tagpath`  
 <span data-ttu-id="fcfbe-108">Percorso dei tag di `filename` che porta al `name` del tag.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="fcfbe-109">Racchiudere il percorso tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="fcfbe-109">Enclose the path in single quotation marks (' ').</span></span>  
  
 `name`  
 <span data-ttu-id="fcfbe-110">Identificatore del nome contenuto nel tag che precede i commenti. `name` ha sempre un `id`.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="fcfbe-111">ID del tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="fcfbe-112">Racchiudere l'ID tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="fcfbe-112">Enclose the ID in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcfbe-113">Note</span><span class="sxs-lookup"><span data-stu-id="fcfbe-113">Remarks</span></span>  
 <span data-ttu-id="fcfbe-114">Il tag \<include> consente di fare riferimento ai commenti di un altro file per la descrizione dei tipi e dei membri del codice sorgente,</span><span class="sxs-lookup"><span data-stu-id="fcfbe-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="fcfbe-115">eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="fcfbe-116">Inserendo la documentazione in un file separato, è possibile applicare alla documentazione il controllo del codice sorgente separatamente dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="fcfbe-117">Una persona, ad esempio, può avere il file di codice sorgente estratto e un'altra il file della documentazione estratto.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>  
  
 <span data-ttu-id="fcfbe-118">Il tag \<include> usa la sintassi XML XPath.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="fcfbe-119">Per informazioni sulla personalizzazione dell'utilizzo di \<include>, consultare la documentazione relativa a XPath.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcfbe-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcfbe-120">Example</span></span>  
 <span data-ttu-id="fcfbe-121">In questo esempio vengono presi in considerazione più file.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-121">This is a multifile example.</span></span> <span data-ttu-id="fcfbe-122">Di seguito è riportato il primo file, che usa \<include>:</span><span class="sxs-lookup"><span data-stu-id="fcfbe-122">The first file, which uses \<include>, is listed below:</span></span>  
  
 <span data-ttu-id="fcfbe-123">[!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fcfbe-123">[!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]</span></span>  
  
 <span data-ttu-id="fcfbe-124">Il secondo file, xml_include_tag.doc, contiene i commenti alla documentazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="fcfbe-124">The second file, xml_include_tag.doc, contains the following documentation comments:</span></span>  
  
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
  
## <a name="program-output"></a><span data-ttu-id="fcfbe-125">Output di programma</span><span class="sxs-lookup"><span data-stu-id="fcfbe-125">Program Output</span></span>  
 <span data-ttu-id="fcfbe-126">L'output seguente viene generato quando si compilano le classi Test e Test2 con la riga di comando seguente: `/doc:DocFileName.xml.`. In Visual Studio, è possibile specificare l'opzione dei commenti XML alla documentazione nel riquadro Compilazione di Creazione progetti.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-126">The following output is generated when you compile the Test and Test2 classes with the following command line: `/doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="fcfbe-127">Se il compilatore C# rileva il tag \<include>, la ricerca dei commenti alla documentazione verrà eseguita nel file xml_include_tag.doc anziché nel file di origine corrente.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-127">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="fcfbe-128">Il compilatore genera quindi il file DocFileName.xml, che verrà usato dagli strumenti della documentazione come [Sandcastle](https://github.com/EWSoftware/SHFB) per realizzare la documentazione finale.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-128">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fcfbe-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcfbe-129">See Also</span></span>  
 <span data-ttu-id="fcfbe-130">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fcfbe-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="fcfbe-131">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="fcfbe-131">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

