---
title: Valori restituiti per la funzione CStr
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
ms.openlocfilehash: 6039ba3f6bd1c364db818807604ee0851bc23d50
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406386"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="f5e9f-102">Valori restituiti dalla funzione CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5e9f-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="f5e9f-103">Nella tabella seguente vengono descritti i valori restituiti per `CStr` per diversi tipi di dati di `expression` .</span><span class="sxs-lookup"><span data-stu-id="f5e9f-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="f5e9f-104">Se il `expression` tipo è</span><span class="sxs-lookup"><span data-stu-id="f5e9f-104">If `expression` type is</span></span>|<span data-ttu-id="f5e9f-105">Valori restituiti `CStr`</span><span class="sxs-lookup"><span data-stu-id="f5e9f-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="f5e9f-106">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="f5e9f-106">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="f5e9f-107">Stringa contenente "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="f5e9f-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="f5e9f-108">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="f5e9f-108">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="f5e9f-109">Stringa contenente un `Date` valore (data e ora) nel formato di data breve del sistema.</span><span class="sxs-lookup"><span data-stu-id="f5e9f-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="f5e9f-110">Tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="f5e9f-110">Numeric Data Types</span></span>](../../programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="f5e9f-111">Stringa che rappresenta il numero.</span><span class="sxs-lookup"><span data-stu-id="f5e9f-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="f5e9f-112">CStr e data</span><span class="sxs-lookup"><span data-stu-id="f5e9f-112">CStr and Date</span></span>  
 <span data-ttu-id="f5e9f-113">Il `Date` tipo contiene sempre le informazioni di data e ora.</span><span class="sxs-lookup"><span data-stu-id="f5e9f-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="f5e9f-114">Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 gennaio dell'anno 1) come *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora.</span><span class="sxs-lookup"><span data-stu-id="f5e9f-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="f5e9f-115">`CStr`non include valori neutri nella stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="f5e9f-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="f5e9f-116">Se ad esempio si esegue `#January 1, 0001 9:30:00#` la conversione in una stringa, il risultato sarà "9:30:00 AM"; le informazioni sulla data vengono annullate.</span><span class="sxs-lookup"><span data-stu-id="f5e9f-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="f5e9f-117">Tuttavia, le informazioni sulla data sono ancora presenti nel `Date` valore originale e possono essere ripristinate con funzioni come <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .</span><span class="sxs-lookup"><span data-stu-id="f5e9f-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5e9f-118">La `CStr` funzione esegue la conversione in base alle impostazioni cultura correnti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f5e9f-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="f5e9f-119">Per ottenere la rappresentazione di stringa di un numero in determinate impostazioni cultura, usare il metodo del numero `ToString(IFormatProvider)` .</span><span class="sxs-lookup"><span data-stu-id="f5e9f-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="f5e9f-120">Ad esempio, usare <xref:System.Double.ToString%2A?displayProperty=nameWithType> quando si converte un valore di tipo `Double` in un oggetto `String` .</span><span class="sxs-lookup"><span data-stu-id="f5e9f-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e9f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5e9f-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="f5e9f-122">CString</span><span class="sxs-lookup"><span data-stu-id="f5e9f-122">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="f5e9f-123">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="f5e9f-123">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="f5e9f-124">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="f5e9f-124">Date Data Type</span></span>](../data-types/date-data-type.md)
