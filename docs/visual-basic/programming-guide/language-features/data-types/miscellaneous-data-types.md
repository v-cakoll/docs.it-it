---
title: Tipi di dati vari (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ed7b61a5ec57ff85347f2c257e321ab9ec425274
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="0595b-102">Tipi di dati vari (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0595b-102">Miscellaneous Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0595b-103">fornisce diversi tipi di dati che non sono riconducibili a numeri o caratteri.</span><span class="sxs-lookup"><span data-stu-id="0595b-103"> supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="0595b-104">Al contrario, gestiscano dati specializzati, ad esempio Sì/no valori, valori data/ora e gli indirizzi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="0595b-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="0595b-105">Per una tabella che mostra un confronto side-by-side di [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipi di dati, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="0595b-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="0595b-106">Tipo booleano</span><span class="sxs-lookup"><span data-stu-id="0595b-106">Boolean Type</span></span>  
 <span data-ttu-id="0595b-107">Il [tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) è un valore senza segno viene interpretato come `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="0595b-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="0595b-108">Ampiezza dei relativi dati dipende dalla piattaforma di implementazione.</span><span class="sxs-lookup"><span data-stu-id="0595b-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="0595b-109">Se una variabile può contenere solo i valori di due stati, ad esempio true/false, sì/no o on/off, dichiararla come `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0595b-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="0595b-110">Date (tipo)</span><span class="sxs-lookup"><span data-stu-id="0595b-110">Date Type</span></span>  
 <span data-ttu-id="0595b-111">Il [tipo di dati Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) è un valore a 64 bit che contiene informazioni sia data e ora.</span><span class="sxs-lookup"><span data-stu-id="0595b-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="0595b-112">Ogni incremento rappresenta 100 nanosecondi di tempo trascorso dall'inizio (12:00 AM) del 1 ° gennaio dell'anno 1 nel calendario gregoriano.</span><span class="sxs-lookup"><span data-stu-id="0595b-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="0595b-113">Se una variabile può contenere un valore di data, un valore di ora o entrambi, dichiararla come `Date`.</span><span class="sxs-lookup"><span data-stu-id="0595b-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="0595b-114">Tipo di oggetto</span><span class="sxs-lookup"><span data-stu-id="0595b-114">Object Type</span></span>  
 <span data-ttu-id="0595b-115">Il [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) è un indirizzo a 32 bit che punta a un'istanza dell'oggetto all'interno dell'applicazione o in un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="0595b-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="0595b-116">Un `Object` variabile può fare riferimento a qualsiasi oggetto riconosciuto dall'applicazione o ai dati di qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="0595b-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="0595b-117">Sono inclusi sia *i tipi di valore*, ad esempio `Integer`, `Boolean`e le istanze della struttura, e *tipi di riferimento*, che sono istanze degli oggetti creati dalle classi, ad esempio `String` e <xref:System.Windows.Forms.Form>e le istanze di matrici.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="0595b-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="0595b-118">Se una variabile archivia un puntatore a un'istanza di una classe che non si conosce in fase di compilazione o se può puntare a vari tipi di dati, dichiararla come `Object`.</span><span class="sxs-lookup"><span data-stu-id="0595b-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="0595b-119">Il vantaggio di `Object` è di tipo di dati che è possibile utilizzare per archiviare i dati di qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="0595b-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="0595b-120">Lo svantaggio è che sono necessarie operazioni aggiuntive che richiedono più tempo di esecuzione e rendere l'applicazione calo delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0595b-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="0595b-121">Se si utilizza un `Object` variabili per i tipi di valore, si incorre in *boxing* e *unboxing*.</span><span class="sxs-lookup"><span data-stu-id="0595b-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="0595b-122">Se è utilizzata per i tipi di riferimento, sono necessarie *l'associazione tardiva*.</span><span class="sxs-lookup"><span data-stu-id="0595b-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0595b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0595b-123">See Also</span></span>  
 <span data-ttu-id="0595b-124">[Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="0595b-124">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
<span data-ttu-id="0595b-125"> [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0595b-125"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="0595b-126"> [Tipi di dati numerici](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0595b-126"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="0595b-127"> [Tipi di dati carattere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0595b-127"> [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span></span>  
<span data-ttu-id="0595b-128"> [Risoluzione dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0595b-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="0595b-129"> [Associazione anticipata e tardiva](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="0595b-129"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
