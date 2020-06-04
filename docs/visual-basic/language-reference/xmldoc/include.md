---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 78a10624107cea349b01f484c641190a945dbd7e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400111"
---
# <a name="include-visual-basic"></a><span data-ttu-id="a4f6c-101">\<include> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4f6c-101">\<include> (Visual Basic)</span></span>
<span data-ttu-id="a4f6c-102">Fa riferimento a un altro file che descrive i tipi e i membri nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-102">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f6c-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4f6c-103">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4f6c-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4f6c-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="a4f6c-105">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-105">Required.</span></span> <span data-ttu-id="a4f6c-106">Nome del file che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-106">The name of the file containing the documentation.</span></span> <span data-ttu-id="a4f6c-107">È possibile qualificare il nome del file con un percorso.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-107">The file name can be qualified with a path.</span></span> <span data-ttu-id="a4f6c-108">Racchiude `filename` tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="a4f6c-108">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="a4f6c-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-109">Required.</span></span> <span data-ttu-id="a4f6c-110">Percorso dei tag di `filename` che porta al `name` del tag.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-110">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="a4f6c-111">Racchiudere il percorso tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="a4f6c-111">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="a4f6c-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-112">Required.</span></span> <span data-ttu-id="a4f6c-113">Identificatore del nome nel tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-113">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="a4f6c-114">`Name`avrà un `id` .</span><span class="sxs-lookup"><span data-stu-id="a4f6c-114">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="a4f6c-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-115">Required.</span></span> <span data-ttu-id="a4f6c-116">ID del tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-116">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="a4f6c-117">Racchiudere l'ID racchiuso tra virgolette singole ('').</span><span class="sxs-lookup"><span data-stu-id="a4f6c-117">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4f6c-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="a4f6c-118">Remarks</span></span>  
 <span data-ttu-id="a4f6c-119">Usare il `<include>` tag per fare riferimento ai commenti in un altro file che descrive i tipi e i membri nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="a4f6c-120">eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-120">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="a4f6c-121">Il `<include>` tag usa la raccomandazione W3C XML Path Language (XPath) versione 1,0.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="a4f6c-122">Per ulteriori informazioni sulle modalità di personalizzazione dell' `<include>` utilizzo, vedere <https://www.w3.org/TR/xpath> .</span><span class="sxs-lookup"><span data-stu-id="a4f6c-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4f6c-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4f6c-123">Example</span></span>  
 <span data-ttu-id="a4f6c-124">Questo esempio usa il `<include>` tag per importare i commenti relativi alla documentazione membri da un file denominato `commentFile.xml` .</span><span class="sxs-lookup"><span data-stu-id="a4f6c-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="a4f6c-125">Il formato di `commentFile.xml` è il seguente.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-125">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a4f6c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4f6c-126">See also</span></span>

- [<span data-ttu-id="a4f6c-127">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="a4f6c-127">XML Comment Tags</span></span>](index.md)
