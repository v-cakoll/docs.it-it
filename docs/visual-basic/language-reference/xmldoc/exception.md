---
title: '&lt;eccezione&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d718a7c2213a61f7f60ed80a04f9bd03f6c770a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="2f6ed-102">&lt;eccezione&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f6ed-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="2f6ed-103">Specifica le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f6ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f6ed-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f6ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f6ed-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="2f6ed-106">Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="2f6ed-107">Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2f6ed-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="2f6ed-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2f6ed-109">Una descrizione.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f6ed-110">Note</span><span class="sxs-lookup"><span data-stu-id="2f6ed-110">Remarks</span></span>  
 <span data-ttu-id="2f6ed-111">Utilizzare il `<exception>` tag per specificare quali eccezioni possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="2f6ed-112">Questo tag viene applicato a una definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="2f6ed-113">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f6ed-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f6ed-114">Example</span></span>  
 <span data-ttu-id="2f6ed-115">Questo esempio viene utilizzato il `<exception>` tag per descrivere un'eccezione che il `IntDivide` funzione può generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2f6ed-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2f6ed-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f6ed-116">See Also</span></span>  
 [<span data-ttu-id="2f6ed-117">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="2f6ed-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
