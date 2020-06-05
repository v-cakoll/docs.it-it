---
title: L'eccezione del commento XML deve avere un attributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406508"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="6bafd-102">L'eccezione del commento XML deve avere un attributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="6bafd-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="6bafd-103">Il \<exception> tag fornisce un modo per documentare le eccezioni che possono essere generate da un metodo.</span><span class="sxs-lookup"><span data-stu-id="6bafd-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="6bafd-104">L' `cref` attributo required designa il nome di un membro, che viene controllato dal generatore di documentazione.</span><span class="sxs-lookup"><span data-stu-id="6bafd-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="6bafd-105">Se il membro esiste, viene convertito nel nome canonico dell'elemento nel file di documentazione.</span><span class="sxs-lookup"><span data-stu-id="6bafd-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="6bafd-106">**ID errore:** BC42319</span><span class="sxs-lookup"><span data-stu-id="6bafd-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6bafd-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="6bafd-107">To correct this error</span></span>

<span data-ttu-id="6bafd-108">Aggiungere l' `cref` attributo all'eccezione come segue:</span><span class="sxs-lookup"><span data-stu-id="6bafd-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="6bafd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bafd-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="6bafd-110">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="6bafd-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="6bafd-111">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="6bafd-111">XML Comment Tags</span></span>](../xmldoc/index.md)
