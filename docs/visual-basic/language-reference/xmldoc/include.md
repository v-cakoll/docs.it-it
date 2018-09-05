---
title: '&lt;includere&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: da7a6c15c558fc56dbc6a874d4a28c4434f67668
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671954"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="bd767-102">&lt;includere&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd767-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="bd767-103">Fa riferimento a un altro file che descrive i tipi e membri nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bd767-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd767-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd767-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd767-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd767-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="bd767-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bd767-106">Required.</span></span> <span data-ttu-id="bd767-107">Nome del file che contiene la documentazione.</span><span class="sxs-lookup"><span data-stu-id="bd767-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="bd767-108">È possibile qualificare il nome del file con un percorso.</span><span class="sxs-lookup"><span data-stu-id="bd767-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="bd767-109">Racchiudere `filename` tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="bd767-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="bd767-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bd767-110">Required.</span></span> <span data-ttu-id="bd767-111">Percorso dei tag di `filename` che porta al `name` del tag.</span><span class="sxs-lookup"><span data-stu-id="bd767-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="bd767-112">Racchiudere il percorso tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="bd767-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="bd767-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bd767-113">Required.</span></span> <span data-ttu-id="bd767-114">L'identificatore di nome nel tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="bd767-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="bd767-115">`Name` sarà necessario un `id`.</span><span class="sxs-lookup"><span data-stu-id="bd767-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="bd767-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bd767-116">Required.</span></span> <span data-ttu-id="bd767-117">ID del tag che precede i commenti.</span><span class="sxs-lookup"><span data-stu-id="bd767-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="bd767-118">Racchiudere l'ID tra virgolette singole (' ').</span><span class="sxs-lookup"><span data-stu-id="bd767-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd767-119">Note</span><span class="sxs-lookup"><span data-stu-id="bd767-119">Remarks</span></span>  
 <span data-ttu-id="bd767-120">Usare il `<include>` tag per fare riferimento ai commenti in un altro file che descrivono i tipi e membri nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bd767-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="bd767-121">eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bd767-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="bd767-122">Il `<include>` tag Usa la raccomandazione di W3C XML Path Language (XPath) Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="bd767-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="bd767-123">Altre informazioni per la modalità di personalizzazione del `<include>` utilizzo è disponibile all'indirizzo http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="bd767-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd767-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd767-124">Example</span></span>  
 <span data-ttu-id="bd767-125">Questo esempio Usa la `<include>` tag per importare i commenti della documentazione membro da un file denominato `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="bd767-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="bd767-126">Il formato del `commentFile.xml` è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bd767-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd767-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd767-127">See Also</span></span>  
 [<span data-ttu-id="bd767-128">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="bd767-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
