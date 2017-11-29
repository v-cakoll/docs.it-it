---
title: Valori restituiti dalla funzione CStr (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b498c9b1b7916467c96ed2c645c7131192a5e8b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="aed88-102">Valori restituiti dalla funzione CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aed88-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="aed88-103">Nella tabella seguente vengono descritti i valori restituiti per `CStr` per diversi tipi di dati di `expression`.</span><span class="sxs-lookup"><span data-stu-id="aed88-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="aed88-104">Se `expression` è di tipo</span><span class="sxs-lookup"><span data-stu-id="aed88-104">If `expression` type is</span></span>|<span data-ttu-id="aed88-105">`CStr`Restituisce</span><span class="sxs-lookup"><span data-stu-id="aed88-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="aed88-106">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="aed88-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="aed88-107">Una stringa contenente "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="aed88-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="aed88-108">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="aed88-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="aed88-109">Stringa contenente un `Date` valore (data e ora) nel formato di data breve del sistema.</span><span class="sxs-lookup"><span data-stu-id="aed88-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="aed88-110">Tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="aed88-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="aed88-111">Stringa che rappresenta il numero.</span><span class="sxs-lookup"><span data-stu-id="aed88-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="aed88-112">Data e CStr</span><span class="sxs-lookup"><span data-stu-id="aed88-112">CStr and Date</span></span>  
 <span data-ttu-id="aed88-113">Il `Date` tipo contiene sempre le informazioni sia data e ora.</span><span class="sxs-lookup"><span data-stu-id="aed88-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="aed88-114">Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 ° gennaio dell'anno 1) da un *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora.</span><span class="sxs-lookup"><span data-stu-id="aed88-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="aed88-115">`CStr`non include valori neutri nella stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="aed88-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="aed88-116">Ad esempio, se si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato è "9:30:00 AM"; le informazioni sulla data viene eliminate.</span><span class="sxs-lookup"><span data-stu-id="aed88-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="aed88-117">Tuttavia, le informazioni sulla data è ancora presente nell'originale `Date` valore e possono essere recuperate con funzioni, ad esempio <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span><span class="sxs-lookup"><span data-stu-id="aed88-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aed88-118">Il `CStr` funzione esegue la conversione in base alle impostazioni cultura correnti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aed88-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="aed88-119">Per ottenere la rappresentazione di stringa di un numero in una lingua specifica, utilizzare il numero `ToString(IFormatProvider)` metodo.</span><span class="sxs-lookup"><span data-stu-id="aed88-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="aed88-120">Ad esempio, utilizzare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` per un `String`.</span><span class="sxs-lookup"><span data-stu-id="aed88-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed88-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aed88-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [<span data-ttu-id="aed88-122">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="aed88-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="aed88-123">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="aed88-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="aed88-124">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="aed88-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
