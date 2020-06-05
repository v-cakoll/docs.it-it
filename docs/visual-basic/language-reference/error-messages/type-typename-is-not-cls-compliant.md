---
title: Il tipo <typename> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: eacf5036ebc6fc31dfa0e8de39c4fb574c9072b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386958"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="229ae-102">Il tipo \<typename> non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="229ae-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="229ae-103">Una variabile, una proprietà o una funzione restituita è dichiarata con un tipo di dati che non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="229ae-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="229ae-104">Affinché un'applicazione sia compatibile con l'indipendenza del [linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve utilizzare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="229ae-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="229ae-105">I tipi di dati Visual Basic seguenti non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="229ae-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="229ae-106">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="229ae-106">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="229ae-107">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="229ae-107">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="229ae-108">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="229ae-108">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="229ae-109">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="229ae-109">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="229ae-110">**ID errore:** BC40041</span><span class="sxs-lookup"><span data-stu-id="229ae-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="229ae-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="229ae-111">To correct this error</span></span>  
  
- <span data-ttu-id="229ae-112">Se l'applicazione deve essere conforme a CLS, modificare il tipo di dati di questo elemento sul tipo conforme a CLS più vicino.</span><span class="sxs-lookup"><span data-stu-id="229ae-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="229ae-113">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="229ae-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="229ae-114">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="229ae-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="229ae-115">Se non è necessario che l'applicazione sia conforme a CLS, non è necessario apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="229ae-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="229ae-116">È tuttavia necessario tenere presente la relativa non conformità.</span><span class="sxs-lookup"><span data-stu-id="229ae-116">You should be aware of its noncompliance, however.</span></span>
