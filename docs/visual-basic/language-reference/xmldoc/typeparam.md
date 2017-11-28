---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b654fe6fc93642693730256b523fee999aa55937
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="c5050-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5050-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="c5050-103">Definisce un parametro di tipo nome e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="c5050-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5050-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5050-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5050-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5050-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c5050-106">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="c5050-106">The name of the type parameter.</span></span> <span data-ttu-id="c5050-107">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="c5050-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c5050-108">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="c5050-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5050-109">Note</span><span class="sxs-lookup"><span data-stu-id="c5050-109">Remarks</span></span>  
 <span data-ttu-id="c5050-110">Utilizzare il `<typeparam>` tag nel commento per un tipo generico o una dichiarazione di membro generico descrivere uno dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="c5050-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="c5050-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="c5050-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5050-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5050-112">Example</span></span>  
 <span data-ttu-id="c5050-113">Questo esempio viene utilizzato il `<typeparam>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="c5050-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c5050-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5050-114">See Also</span></span>  
 [<span data-ttu-id="c5050-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="c5050-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
