---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 91bde92e2184c90b14838a09a89a6d261447f139
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662615"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="33609-102">L'eccezione del commento XML deve avere un attributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="33609-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="33609-103">Il \<eccezione > tag consente di documentare le eccezioni che possono essere generate da un metodo.</span><span class="sxs-lookup"><span data-stu-id="33609-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="33609-104">Obbligatorio `cref` l'attributo specifica il nome di un membro, che viene controllato dal generatore di documentazione.</span><span class="sxs-lookup"><span data-stu-id="33609-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="33609-105">Se il membro esiste, viene convertito al nome canonico dell'elemento nel file di documentazione.</span><span class="sxs-lookup"><span data-stu-id="33609-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="33609-106">**ID errore:** BC42319</span><span class="sxs-lookup"><span data-stu-id="33609-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33609-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="33609-107">To correct this error</span></span>  
  
- <span data-ttu-id="33609-108">Aggiungere il `cref` attributo per l'eccezione come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="33609-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33609-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33609-109">See also</span></span>

- [<span data-ttu-id="33609-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="33609-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="33609-111">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="33609-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="33609-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="33609-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
