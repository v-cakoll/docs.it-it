---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3ca08016d3cef0c44e4f3c0bd0d017628eda606d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400047"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="5a49e-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a49e-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="5a49e-102">Formatta una parola come parametro.</span><span class="sxs-lookup"><span data-stu-id="5a49e-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a49e-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a49e-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a49e-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a49e-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5a49e-105">Nome del parametro a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="5a49e-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="5a49e-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="5a49e-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a49e-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="5a49e-107">Remarks</span></span>  
 <span data-ttu-id="5a49e-108">Il `<paramref>` tag consente di indicare che una parola è un parametro.</span><span class="sxs-lookup"><span data-stu-id="5a49e-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="5a49e-109">Il file XML può essere elaborato per formattare questo parametro in modo distinto.</span><span class="sxs-lookup"><span data-stu-id="5a49e-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="5a49e-110">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="5a49e-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a49e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a49e-111">Example</span></span>  
 <span data-ttu-id="5a49e-112">Questo esempio usa il `<paramref>` tag per fare riferimento al `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="5a49e-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5a49e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a49e-113">See also</span></span>

- [<span data-ttu-id="5a49e-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="5a49e-114">XML Comment Tags</span></span>](index.md)
