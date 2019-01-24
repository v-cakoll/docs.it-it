---
title: L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: b4cae7802019cba569cf15517b1e948266a576f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631438"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="ee284-102">L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita</span><span class="sxs-lookup"><span data-stu-id="ee284-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="ee284-103">Nel costruttore della classe è stata usata un'istanza predefinita di una classe.</span><span class="sxs-lookup"><span data-stu-id="ee284-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="ee284-104">Questo può causare una chiamata ricorsiva infinita, detta anche ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="ee284-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee284-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ee284-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ee284-106">Rimuovere l'istanza predefinita dal costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="ee284-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee284-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee284-107">See also</span></span>
- [<span data-ttu-id="ee284-108">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ee284-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
