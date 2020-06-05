---
title: Previsto inizializzatore
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 13fa8917f228661fc44f5e0920d91c596e250c38
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402837"
---
# <a name="initializer-expected"></a><span data-ttu-id="e411d-102">Previsto inizializzatore</span><span class="sxs-lookup"><span data-stu-id="e411d-102">Initializer expected</span></span>
<span data-ttu-id="e411d-103">Si è provato a dichiarare un'istanza di una classe usando un inizializzatore di oggetto in cui l'elenco di inizializzazione è vuoto, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e411d-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="e411d-104">È necessario inizializzare almeno un campo o una proprietà nell'elenco di inizializzatori, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e411d-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="e411d-105">**ID errore:** BC30996</span><span class="sxs-lookup"><span data-stu-id="e411d-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e411d-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e411d-106">To correct this error</span></span>  
  
1. <span data-ttu-id="e411d-107">Inizializzare almeno un campo o una proprietà nell'inizializzatore oppure non usare un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="e411d-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e411d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e411d-108">See also</span></span>

- [<span data-ttu-id="e411d-109">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="e411d-109">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="e411d-110">Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto</span><span class="sxs-lookup"><span data-stu-id="e411d-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
