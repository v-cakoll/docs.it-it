---
title: Non è possibile chiamare la funzione Friend su un oggetto che non è un'istanza della classe di definizione
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: a655207110d512805490b693e413b1d22b0367ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33634929"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="f4f83-102">Non è possibile chiamare la funzione Friend su un oggetto che non è un'istanza della classe di definizione</span><span class="sxs-lookup"><span data-stu-id="f4f83-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="f4f83-103">Si è provato a chiamare la routine `Friend` di una classe oppure di accedere a un metodo o a una proprietà `Friend` tra più processi o cross-thread.</span><span class="sxs-lookup"><span data-stu-id="f4f83-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="f4f83-104">Una routine `Friend` può essere chiamata da un modulo all'esterno della classe, ma fa parte del progetto in cui è definita la classe.</span><span class="sxs-lookup"><span data-stu-id="f4f83-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4f83-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f4f83-105">To correct this error</span></span>  
  
-   <span data-ttu-id="f4f83-106">Assicurarsi di chiamare la routine o di accedervi da un modulo che fa parte del progetto in cui è definita la classe.</span><span class="sxs-lookup"><span data-stu-id="f4f83-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f83-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4f83-107">See Also</span></span>  
 [<span data-ttu-id="f4f83-108">Friend</span><span class="sxs-lookup"><span data-stu-id="f4f83-108">Friend</span></span>](../../visual-basic/language-reference/modifiers/friend.md)
