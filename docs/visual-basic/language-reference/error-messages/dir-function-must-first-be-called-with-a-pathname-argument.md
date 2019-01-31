---
title: La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 828c715d9aaceef17d030113e7eda302f025ca9d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282590"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="91737-102">La funzione 'Dir' deve essere anzitutto chiamata con un argomento 'PathName'</span><span class="sxs-lookup"><span data-stu-id="91737-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="91737-103">Una chiamata iniziale per il `Dir` funzione non include il `PathName` argomento.</span><span class="sxs-lookup"><span data-stu-id="91737-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="91737-104">La prima chiamata a `Dir` deve includere una `PathName`, ma le chiamate successive a `Dir` non è necessario includere i parametri per recuperare l'elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="91737-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91737-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="91737-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="91737-106">Fornire un `PathName` argomento nella chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="91737-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91737-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91737-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
