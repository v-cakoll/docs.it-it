---
title: '&lt;includere&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 0f143f8c023102f44b41e3898f29d18be0083128
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49349108"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="eb9f9-102">&lt;includere&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb9f9-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="eb9f9-103">Fa riferimento a un altro file che descrive i tipi e membri nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb9f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb9f9-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb9f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb9f9-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="eb9f9-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-106">Required.</span></span> <span data-ttu-id="eb9f9-107">Nome del file che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="eb9f9-108">È possibile qualificare il nome del file con un percorso.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="eb9f9-109">Racchiudere `filename` tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="eb9f9-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="eb9f9-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-110">Required.</span></span> <span data-ttu-id="eb9f9-111">Percorso dei tag di `filename` che porta al `name` del tag.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="eb9f9-112">Racchiudere il percorso tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="eb9f9-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="eb9f9-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-113">Required.</span></span> <span data-ttu-id="eb9f9-114">L'identificatore di nome nel tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="eb9f9-115">`Name` sarà necessario un `id`.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="eb9f9-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-116">Required.</span></span> <span data-ttu-id="eb9f9-117">ID del tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="eb9f9-118">Racchiudere l'ID tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="eb9f9-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb9f9-119">Note</span><span class="sxs-lookup"><span data-stu-id="eb9f9-119">Remarks</span></span>  
 <span data-ttu-id="eb9f9-120">Usare il `<include>` tag per fare riferimento ai commenti in un altro file che descrivono i tipi e membri nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="eb9f9-121">eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="eb9f9-122">Il `<include>` tag Usa la raccomandazione di W3C XML Path Language (XPath) Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="eb9f9-123">Per altre informazioni sui modi per personalizzare il `<include>` usare, vedere <https://www.w3.org/TR/xpath>.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-123">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb9f9-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb9f9-124">Example</span></span>  
 <span data-ttu-id="eb9f9-125">Questo esempio Usa la `<include>` tag per importare i commenti della documentazione membro da un file denominato `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="eb9f9-126">Il formato del `commentFile.xml` è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="eb9f9-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb9f9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb9f9-127">See Also</span></span>  
 [<span data-ttu-id="eb9f9-128">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="eb9f9-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
