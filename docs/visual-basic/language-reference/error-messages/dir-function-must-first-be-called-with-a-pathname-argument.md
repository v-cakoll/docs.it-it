---
title: '&#39; Dir &#39; funzione deve essere anzitutto chiamata con un &#39; Percorso &#39; argomento'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 843918fe9cb0b9dece076b5dc1373c3571588caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="d8ffb-102">&#39; Dir &#39; funzione deve essere anzitutto chiamata con un &#39; Percorso &#39; argomento</span><span class="sxs-lookup"><span data-stu-id="d8ffb-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="d8ffb-103">Una chiamata iniziale per il `Dir` funzione non include il `PathName` argomento.</span><span class="sxs-lookup"><span data-stu-id="d8ffb-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="d8ffb-104">La prima chiamata a `Dir` deve includere un `PathName`, ma le chiamate successive a `Dir` non è necessario includere parametri per recuperare l'elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="d8ffb-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8ffb-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d8ffb-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="d8ffb-106">Fornire un `PathName` argomento nella chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="d8ffb-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ffb-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8ffb-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
