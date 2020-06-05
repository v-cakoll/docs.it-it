---
title: Non è possibile chiamare la funzione Friend su un oggetto che non è un'istanza della classe di definizione
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c18c04470c4c49113e8195b92185326c5c4197c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400848"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="16874-102">Non è possibile chiamare la funzione Friend su un oggetto che non è un'istanza della classe di definizione</span><span class="sxs-lookup"><span data-stu-id="16874-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="16874-103">Si è provato a chiamare la routine `Friend` di una classe oppure di accedere a un metodo o a una proprietà `Friend` tra più processi o cross-thread.</span><span class="sxs-lookup"><span data-stu-id="16874-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="16874-104">Una routine `Friend` può essere chiamata da un modulo all'esterno della classe, ma fa parte del progetto in cui è definita la classe.</span><span class="sxs-lookup"><span data-stu-id="16874-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16874-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="16874-105">To correct this error</span></span>  
  
- <span data-ttu-id="16874-106">Assicurarsi di chiamare la routine o di accedervi da un modulo che fa parte del progetto in cui è definita la classe.</span><span class="sxs-lookup"><span data-stu-id="16874-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16874-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16874-107">See also</span></span>

- [<span data-ttu-id="16874-108">Amico</span><span class="sxs-lookup"><span data-stu-id="16874-108">Friend</span></span>](../language-reference/modifiers/friend.md)
