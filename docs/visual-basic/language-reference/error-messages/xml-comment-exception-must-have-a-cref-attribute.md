---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a974df5d2305b88946981d0d258a8088b23d3fc3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813288"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="9d670-102">L'eccezione del commento XML deve avere un attributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="9d670-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="9d670-103">Il \<eccezione > tag consente di documentare le eccezioni che possono essere generate da un metodo.</span><span class="sxs-lookup"><span data-stu-id="9d670-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="9d670-104">Obbligatorio `cref` l'attributo specifica il nome di un membro, che viene controllato dal generatore di documentazione.</span><span class="sxs-lookup"><span data-stu-id="9d670-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="9d670-105">Se il membro esiste, viene convertito al nome canonico dell'elemento nel file di documentazione.</span><span class="sxs-lookup"><span data-stu-id="9d670-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="9d670-106">**ID errore:** BC42319</span><span class="sxs-lookup"><span data-stu-id="9d670-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d670-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9d670-107">To correct this error</span></span>  
  
-   <span data-ttu-id="9d670-108">Aggiungere il `cref` attributo per l'eccezione come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9d670-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9d670-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d670-109">See also</span></span>

- [<span data-ttu-id="9d670-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="9d670-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="9d670-111">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="9d670-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="9d670-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="9d670-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
