---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592033"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="af262-102">L'eccezione del commento XML deve avere un attributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="af262-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="af262-103">Il tag di > \<exception fornisce un modo per documentare le eccezioni che possono essere generate da un metodo.</span><span class="sxs-lookup"><span data-stu-id="af262-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="af262-104">L'attributo `cref` obbligatorio indica il nome di un membro, che viene controllato dal generatore di documentazione.</span><span class="sxs-lookup"><span data-stu-id="af262-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="af262-105">Se il membro esiste, viene convertito nel nome canonico dell'elemento nel file di documentazione.</span><span class="sxs-lookup"><span data-stu-id="af262-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="af262-106">**ID errore:** BC42319</span><span class="sxs-lookup"><span data-stu-id="af262-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="af262-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="af262-107">To correct this error</span></span>  
  
- <span data-ttu-id="af262-108">Aggiungere l'attributo `cref` all'eccezione come segue:</span><span class="sxs-lookup"><span data-stu-id="af262-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    <span data-ttu-id="af262-109">xml</span><span class="sxs-lookup"><span data-stu-id="af262-109">xml</span></span>  
    <span data-ttu-id="af262-110">'''<exception cref="member">Descrizione</exception></span><span class="sxs-lookup"><span data-stu-id="af262-110">'''<exception cref="member">description</exception></span></span>  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
