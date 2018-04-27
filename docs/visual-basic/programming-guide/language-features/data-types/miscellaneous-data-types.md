---
title: Tipi di dati vari (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f80aacccab4c215b3e3917cc73097080aa6b9941
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="ffd09-102">Tipi di dati vari (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffd09-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="ffd09-103">Visual Basic fornisce diversi tipi di dati che non sono orientati verso i numeri o caratteri.</span><span class="sxs-lookup"><span data-stu-id="ffd09-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="ffd09-104">In alternativa, occuparsi di dati speciali, ad esempio Sì/no valori, valori data/ora e oggetto indirizzi.</span><span class="sxs-lookup"><span data-stu-id="ffd09-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="ffd09-105">Per una tabella che mostra un confronto side-by-side dei tipi di dati Visual Basic, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="ffd09-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="ffd09-106">Tipo booleano</span><span class="sxs-lookup"><span data-stu-id="ffd09-106">Boolean Type</span></span>  
 <span data-ttu-id="ffd09-107">Il [tipo di dati Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) è un valore senza segno viene interpretato come `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="ffd09-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="ffd09-108">La larghezza dei dati dipende dalla piattaforma di implementazione.</span><span class="sxs-lookup"><span data-stu-id="ffd09-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="ffd09-109">Se una variabile può contenere solo valori di due stati, ad esempio true/false, sì/no o on/off, dichiararla come `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ffd09-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="ffd09-110">Date (tipo)</span><span class="sxs-lookup"><span data-stu-id="ffd09-110">Date Type</span></span>  
 <span data-ttu-id="ffd09-111">Il [tipo di dati Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) è un valore a 64 bit che contiene le informazioni sia data e ora.</span><span class="sxs-lookup"><span data-stu-id="ffd09-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="ffd09-112">Ogni incremento rappresenta 100 nanosecondi di tempo trascorso dall'inizio (12:00 AM) del 1 ° gennaio dell'anno 1 del calendario gregoriano.</span><span class="sxs-lookup"><span data-stu-id="ffd09-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="ffd09-113">Se una variabile può contenere un valore di data, un valore di ora o entrambi, dichiararla come `Date`.</span><span class="sxs-lookup"><span data-stu-id="ffd09-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="ffd09-114">Tipo di oggetto</span><span class="sxs-lookup"><span data-stu-id="ffd09-114">Object Type</span></span>  
 <span data-ttu-id="ffd09-115">Il [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) è un indirizzo a 32 bit che punta a un'istanza dell'oggetto all'interno dell'applicazione o in un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="ffd09-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="ffd09-116">Un `Object` variabile può fare riferimento a qualsiasi oggetto riconosciuto dall'applicazione o ai dati di qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="ffd09-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="ffd09-117">Sono inclusi sia *i tipi di valore*, ad esempio `Integer`, `Boolean`e le istanze della struttura, e *tipi di riferimento*, che sono istanze di oggetti creati da classi, ad esempio `String`e <xref:System.Windows.Forms.Form>e matrice di istanze.</span><span class="sxs-lookup"><span data-stu-id="ffd09-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="ffd09-118">Se una variabile archivia un puntatore a un'istanza di una classe che non si conosce in fase di compilazione o se può puntare a vari tipi di dati, dichiararlo come `Object`.</span><span class="sxs-lookup"><span data-stu-id="ffd09-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="ffd09-119">Il vantaggio del `Object` è di tipo di dati che è possibile utilizzare per archiviare i dati di qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="ffd09-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="ffd09-120">Lo svantaggio è che sono necessarie ulteriori operazioni che richiedono più tempo di esecuzione e rendere l'applicazione di esecuzione più lenta.</span><span class="sxs-lookup"><span data-stu-id="ffd09-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="ffd09-121">Se si utilizza un `Object` variabili per i tipi di valore, si devono sostenere *boxing* e *unboxing*.</span><span class="sxs-lookup"><span data-stu-id="ffd09-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="ffd09-122">Se si utilizza per i tipi di riferimento, sono necessarie *ad associazione tardiva*.</span><span class="sxs-lookup"><span data-stu-id="ffd09-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd09-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffd09-123">See Also</span></span>  
 [<span data-ttu-id="ffd09-124">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="ffd09-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="ffd09-125">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="ffd09-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="ffd09-126">Tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="ffd09-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="ffd09-127">Dati di tipo carattere</span><span class="sxs-lookup"><span data-stu-id="ffd09-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="ffd09-128">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="ffd09-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="ffd09-129">Associazione anticipata e tardiva</span><span class="sxs-lookup"><span data-stu-id="ffd09-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
