---
title: Valori restituiti dalla funzione CStr (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819515"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="2f32f-102">Valori restituiti dalla funzione CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f32f-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="2f32f-103">La tabella seguente descrive i valori restituiti per `CStr` per diversi tipi di dati di `expression`.</span><span class="sxs-lookup"><span data-stu-id="2f32f-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="2f32f-104">Se `expression` è di tipo</span><span class="sxs-lookup"><span data-stu-id="2f32f-104">If `expression` type is</span></span>|<span data-ttu-id="2f32f-105">Valori restituiti `CStr`</span><span class="sxs-lookup"><span data-stu-id="2f32f-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="2f32f-106">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="2f32f-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="2f32f-107">Stringa contenente "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="2f32f-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="2f32f-108">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="2f32f-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="2f32f-109">Stringa contenente un `Date` valore (data e ora) nel formato data breve del sistema.</span><span class="sxs-lookup"><span data-stu-id="2f32f-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="2f32f-110">Tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="2f32f-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="2f32f-111">Stringa che rappresenta il numero.</span><span class="sxs-lookup"><span data-stu-id="2f32f-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="2f32f-112">Data e CStr</span><span class="sxs-lookup"><span data-stu-id="2f32f-112">CStr and Date</span></span>  
 <span data-ttu-id="2f32f-113">Il `Date` tipo contiene sempre le informazioni sia data e ora.</span><span class="sxs-lookup"><span data-stu-id="2f32f-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="2f32f-114">Ai fini di conversione del tipo, Visual Basic considera come 1/1/0001 (1 ° gennaio dell'anno 1) da un *valore neutro* per la data e 00:00:00 (mezzanotte) su un valore neutro per il periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2f32f-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="2f32f-115">`CStr` non include valori neutri nella stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="2f32f-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="2f32f-116">Ad esempio, se si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato è "9:30: 12:00:00 AM"; le informazioni sulla data viene eliminate.</span><span class="sxs-lookup"><span data-stu-id="2f32f-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="2f32f-117">Tuttavia, le informazioni sulla data è ancora presente nell'originale `Date` valore e possono essere recuperate con le funzioni, ad esempio <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f32f-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f32f-118">Il `CStr` funzione esegue la conversione in base alle impostazioni cultura correnti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f32f-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="2f32f-119">Per ottenere la rappresentazione di stringa di un numero in una specifica impostazione cultura, usare il numero `ToString(IFormatProvider)` (metodo).</span><span class="sxs-lookup"><span data-stu-id="2f32f-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="2f32f-120">Ad esempio, usare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` a un `String`.</span><span class="sxs-lookup"><span data-stu-id="2f32f-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f32f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f32f-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="2f32f-122">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="2f32f-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2f32f-123">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="2f32f-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="2f32f-124">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="2f32f-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
