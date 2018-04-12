---
title: Eccezione del commento XML deve avere un &#39; cref &#39; attributo
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c22c9cd9415faf17d027c3751d166662a92b50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="5d11c-102">Eccezione del commento XML deve avere un &#39; cref &#39; attributo</span><span class="sxs-lookup"><span data-stu-id="5d11c-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="5d11c-103">Il \<eccezione > tag fornisce un modo per documentare le eccezioni che possono essere generate da un metodo.</span><span class="sxs-lookup"><span data-stu-id="5d11c-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="5d11c-104">Obbligatorio `cref` l'attributo specifica il nome di un membro, è selezionata per il generatore di documentazione.</span><span class="sxs-lookup"><span data-stu-id="5d11c-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="5d11c-105">Se il membro esiste, viene convertito il nome canonico dell'elemento nel file di documentazione.</span><span class="sxs-lookup"><span data-stu-id="5d11c-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="5d11c-106">**ID errore:** BC42319</span><span class="sxs-lookup"><span data-stu-id="5d11c-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d11c-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5d11c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="5d11c-108">Aggiungere il `cref` attributo all'eccezione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5d11c-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5d11c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d11c-109">See Also</span></span>  
 [<span data-ttu-id="5d11c-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="5d11c-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="5d11c-111">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="5d11c-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="5d11c-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="5d11c-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
