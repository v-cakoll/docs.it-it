---
title: Il tipo <typename> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 243f51b3e6c798c82fdbe7b28557c4f96c728bf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764374"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="a6198-102">Tipo \<typename > non è conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="a6198-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="a6198-103">Una variabile, proprietà o restituito dalla funzione è dichiarato con un tipo di dati che non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="a6198-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="a6198-104">Per un'applicazione è compatibile con il [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), è necessario utilizzare solo tipi conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="a6198-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="a6198-105">I seguenti tipi di dati di Visual Basic non sono conformi a CLS:</span><span class="sxs-lookup"><span data-stu-id="a6198-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="a6198-106">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="a6198-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="a6198-107">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="a6198-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="a6198-108">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="a6198-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="a6198-109">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="a6198-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="a6198-110">**ID errore:** BC40041</span><span class="sxs-lookup"><span data-stu-id="a6198-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6198-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a6198-111">To correct this error</span></span>  
  
- <span data-ttu-id="a6198-112">Se l'applicazione deve essere conforme a CLS, modificare il tipo di dati di questo elemento di tipo conforme a CLS più vicina.</span><span class="sxs-lookup"><span data-stu-id="a6198-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="a6198-113">Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="a6198-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a6198-114">Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.</span><span class="sxs-lookup"><span data-stu-id="a6198-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="a6198-115">Se l'applicazione non deve essere conforme a CLS, non occorre apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="a6198-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="a6198-116">È consigliabile tenere la non conformità, tuttavia.</span><span class="sxs-lookup"><span data-stu-id="a6198-116">You should be aware of its noncompliance, however.</span></span>