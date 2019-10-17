---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321169"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="60407-102">L'eccezione del commento XML deve avere un attributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="60407-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="60407-103">Il tag \<exception > fornisce un modo per documentare le eccezioni che possono essere generate da un metodo.</span><span class="sxs-lookup"><span data-stu-id="60407-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="60407-104">L'attributo `cref` obbligatorio indica il nome di un membro, che viene controllato dal generatore di documentazione.</span><span class="sxs-lookup"><span data-stu-id="60407-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="60407-105">Se il membro esiste, viene convertito nel nome canonico dell'elemento nel file di documentazione.</span><span class="sxs-lookup"><span data-stu-id="60407-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="60407-106">**ID errore:** BC42319</span><span class="sxs-lookup"><span data-stu-id="60407-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="60407-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="60407-107">To correct this error</span></span>

<span data-ttu-id="60407-108">Aggiungere l'attributo `cref` all'eccezione come segue:</span><span class="sxs-lookup"><span data-stu-id="60407-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="60407-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60407-109">See also</span></span>

- [<span data-ttu-id="60407-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="60407-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="60407-111">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="60407-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="60407-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="60407-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
