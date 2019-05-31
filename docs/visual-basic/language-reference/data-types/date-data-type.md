---
title: Tipo di dati Date (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: 970c69b36eecd110dd81b6a3700fbb0a7eea2834
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66424031"
---
# <a name="date-data-type-visual-basic"></a><span data-ttu-id="2e32f-102">Tipo di dati Date (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e32f-102">Date Data Type (Visual Basic)</span></span>
<span data-ttu-id="2e32f-103">Contiene valori a 64 bit (8 byte) conformi alle specifiche IEEE che rappresentano le date comprese tra l'1 gennaio dell'anno 0001 e il 31 dicembre dell'anno 9999 e le ore comprese tra le 00.00.00 (mezzanotte) e le 23.59.59.9999999.</span><span class="sxs-lookup"><span data-stu-id="2e32f-103">Holds IEEE 64-bit (8-byte) values that represent dates ranging from January 1 of the year 0001 through December 31 of the year 9999, and times from 12:00:00 AM (midnight) through 11:59:59.9999999 PM.</span></span> <span data-ttu-id="2e32f-104">Ogni incremento rappresenta 100 nanosecondi di tempo trascorso dall'inizio del 1° gennaio dell'anno 1 del calendario gregoriano.</span><span class="sxs-lookup"><span data-stu-id="2e32f-104">Each increment represents 100 nanoseconds of elapsed time since the beginning of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="2e32f-105">Il valore massimo rappresenta 100 nanosecondi prima dell'inizio del 1° gennaio dell'anno 10000.</span><span class="sxs-lookup"><span data-stu-id="2e32f-105">The maximum value represents 100 nanoseconds before the beginning of January 1 of the year 10000.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e32f-106">Note</span><span class="sxs-lookup"><span data-stu-id="2e32f-106">Remarks</span></span>  
 <span data-ttu-id="2e32f-107">Usare il tipo di dati `Date` per contenere valori di data, di ora o entrambi.</span><span class="sxs-lookup"><span data-stu-id="2e32f-107">Use the `Date` data type to contain date values, time values, or date and time values.</span></span>  
  
 <span data-ttu-id="2e32f-108">Il valore predefinito di `Date` è 00.00.00 (mezzanotte) del 1° gennaio 0001.</span><span class="sxs-lookup"><span data-stu-id="2e32f-108">The default value of `Date` is 0:00:00 (midnight) on January 1, 0001.</span></span>  
  
 <span data-ttu-id="2e32f-109">È possibile ottenere la data e l'ora corrente dalla classe <xref:Microsoft.VisualBasic.DateAndTime>.</span><span class="sxs-lookup"><span data-stu-id="2e32f-109">You can get the current date and time from the <xref:Microsoft.VisualBasic.DateAndTime> class.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="2e32f-110">Requisiti di formato</span><span class="sxs-lookup"><span data-stu-id="2e32f-110">Format Requirements</span></span>  
 <span data-ttu-id="2e32f-111">È necessario racchiudere un valore letterale `Date` tra simboli di cancelletto (`# #`).</span><span class="sxs-lookup"><span data-stu-id="2e32f-111">You must enclose a `Date` literal within number signs (`# #`).</span></span> <span data-ttu-id="2e32f-112">Il valore della data deve essere specificato nel formato M/g/aaaa, ad esempio `#5/31/1993#`, oppure aaaa-MM-gg, ad esempio `#1993-5-31#`.</span><span class="sxs-lookup"><span data-stu-id="2e32f-112">You must specify the date value in the format M/d/yyyy, for example `#5/31/1993#`, or yyyy-MM-dd, for example `#1993-5-31#`.</span></span> <span data-ttu-id="2e32f-113">Quando si specifica prima l'anno, è possibile usare le barre.</span><span class="sxs-lookup"><span data-stu-id="2e32f-113">You can use slashes when specifying the year first.</span></span>  <span data-ttu-id="2e32f-114">Questo requisito è indipendente dalle impostazioni locali usate e dalle impostazioni relative al formato di data e ora del computer.</span><span class="sxs-lookup"><span data-stu-id="2e32f-114">This requirement is independent of your locale and your computer's date and time format settings.</span></span>  
  
 <span data-ttu-id="2e32f-115">Il motivo di questa limitazione è che il significato del codice non deve mai cambiare a seconda delle impostazioni locali con cui l'applicazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="2e32f-115">The reason for this restriction is that the meaning of your code should never change depending on the locale in which your application is running.</span></span> <span data-ttu-id="2e32f-116">Si supponga di impostare come hardcoded il valore letterale `Date``#3/4/1998#` per rappresentare la data del 4 marzo 1998.</span><span class="sxs-lookup"><span data-stu-id="2e32f-116">Suppose you hard-code a `Date` literal of `#3/4/1998#` and intend it to mean March 4, 1998.</span></span> <span data-ttu-id="2e32f-117">Se nelle impostazioni locali è definito il formato mm/gg/aaaa, la compilazione di 3/4/1998 viene eseguita nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="2e32f-117">In a locale that uses mm/dd/yyyy, 3/4/1998 compiles as you intend.</span></span> <span data-ttu-id="2e32f-118">Ma si supponga che si distribuisce l'applicazione in molti paesi/aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="2e32f-118">But suppose you deploy your application in many countries/regions.</span></span> <span data-ttu-id="2e32f-119">Se nelle impostazioni locali è definito il formato gg/mm/aaaa, il valore letterale hardcoded verrà compilato come 3 aprile 1998.</span><span class="sxs-lookup"><span data-stu-id="2e32f-119">In a locale that uses dd/mm/yyyy, your hard-coded literal would compile to April 3, 1998.</span></span> <span data-ttu-id="2e32f-120">Se invece è definito il formato aaaa/mm/gg, il valore letterale non sarà valido (1998 aprile 0003) e verrà generato un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="2e32f-120">In a locale that uses yyyy/mm/dd, the literal would be invalid (April 1998, 0003) and cause a compiler error.</span></span>  
  
## <a name="workarounds"></a><span data-ttu-id="2e32f-121">Soluzioni</span><span class="sxs-lookup"><span data-stu-id="2e32f-121">Workarounds</span></span>  
 <span data-ttu-id="2e32f-122">Per convertire un valore letterale `Date` nel formato delle impostazioni locali in uso o in un formato personalizzato, fornire il valore letterale alla funzione <xref:Microsoft.VisualBasic.Strings.Format%2A>, specificando un formato di data predefinito o definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2e32f-122">To convert a `Date` literal to the format of your locale, or to a custom format, supply the literal to the <xref:Microsoft.VisualBasic.Strings.Format%2A> function, specifying either a predefined or user-defined date format.</span></span> <span data-ttu-id="2e32f-123">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="2e32f-123">The following example demonstrates this.</span></span>  
  
```  
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))  
```  
  
 <span data-ttu-id="2e32f-124">In alternativa, si può usare uno dei costruttori di overload della struttura <xref:System.DateTime> per assemblare un valore di data e ora.</span><span class="sxs-lookup"><span data-stu-id="2e32f-124">Alternatively, you can use one of the overloaded constructors of the <xref:System.DateTime> structure to assemble a date and time value.</span></span> <span data-ttu-id="2e32f-125">L'esempio seguente crea un valore per rappresentare le ore 12.14 del 31 maggio 1993.</span><span class="sxs-lookup"><span data-stu-id="2e32f-125">The following example creates a value to represent May 31, 1993 at 12:14 in the afternoon.</span></span>  
  
```  
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)  
```  
  
## <a name="hour-format"></a><span data-ttu-id="2e32f-126">Formato dell'ora</span><span class="sxs-lookup"><span data-stu-id="2e32f-126">Hour Format</span></span>  
 <span data-ttu-id="2e32f-127">È possibile specificare il valore dell'ora nel formato 12 o 24 ore, ad esempio `#1:15:30 PM#` o `#13:15:30#`.</span><span class="sxs-lookup"><span data-stu-id="2e32f-127">You can specify the time value in either 12-hour or 24-hour format, for example `#1:15:30 PM#` or `#13:15:30#`.</span></span> <span data-ttu-id="2e32f-128">Tuttavia, se non si specificano i minuti o i secondi, è necessario indicare AM o PM.</span><span class="sxs-lookup"><span data-stu-id="2e32f-128">However, if you do not specify either the minutes or the seconds, you must specify AM or PM.</span></span>  
  
## <a name="date-and-time-defaults"></a><span data-ttu-id="2e32f-129">Valori predefiniti di data e ora</span><span class="sxs-lookup"><span data-stu-id="2e32f-129">Date and Time Defaults</span></span>  
 <span data-ttu-id="2e32f-130">Se non si include una data in un valore letterale di data/ora, Visual Basic imposta la parte del valore relativa alla data sul 1° gennaio 0001.</span><span class="sxs-lookup"><span data-stu-id="2e32f-130">If you do not include a date in a date/time literal, Visual Basic sets the date part of the value to January 1, 0001.</span></span> <span data-ttu-id="2e32f-131">Se non si include un'ora in un valore letterale di data/ora, Visual Basic imposta la parte del valore relativa all'ora sull'inizio della giornata, ossia mezzanotte (00.00.00).</span><span class="sxs-lookup"><span data-stu-id="2e32f-131">If you do not include a time in a date/time literal, Visual Basic sets the time part of the value to the start of the day, that is, midnight (0:00:00).</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="2e32f-132">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="2e32f-132">Type Conversions</span></span>  
 <span data-ttu-id="2e32f-133">Se un valore `Date` viene convertito nel tipo `String`, Visual Basic esegue il rendering della data e dell'ora rispettivamente in base al formato breve e al formato 12 o 24 ore specificati nelle impostazioni locali di runtime.</span><span class="sxs-lookup"><span data-stu-id="2e32f-133">If you convert a `Date` value to the `String` type, Visual Basic renders the date according to the short date format specified by the run-time locale, and it renders the time according to the time format (either 12-hour or 24-hour) specified by the run-time locale.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="2e32f-134">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="2e32f-134">Programming Tips</span></span>  
  
- <span data-ttu-id="2e32f-135">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="2e32f-135">**Interop Considerations.**</span></span> <span data-ttu-id="2e32f-136">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di data/ora in altri ambienti non sono compatibili con il tipo `Date` di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2e32f-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that date/time types in other environments are not compatible with the Visual Basic `Date` type.</span></span> <span data-ttu-id="2e32f-137">Se si passa un argomento di data/ora a un componente di questo tipo, nel nuovo codice Visual Basic è necessario dichiararlo come `Double` anziché come `Date` e usare i metodi di conversione <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> e <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e32f-137">If you are passing a date/time argument to such a component, declare it as `Double` instead of `Date` in your new Visual Basic code, and use the conversion methods <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> and <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="2e32f-138">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="2e32f-138">**Type Characters.**</span></span> <span data-ttu-id="2e32f-139">`Date` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="2e32f-139">`Date` has no literal type character or identifier type character.</span></span> <span data-ttu-id="2e32f-140">Il compilatore considera tuttavia i valori letterali racchiusi tra simboli del cancelletto (`# #`) come valori `Date`.</span><span class="sxs-lookup"><span data-stu-id="2e32f-140">However, the compiler treats literals enclosed within number signs (`# #`) as `Date`.</span></span>  
  
- <span data-ttu-id="2e32f-141">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="2e32f-141">**Framework Type.**</span></span> <span data-ttu-id="2e32f-142">Il tipo corrispondente in .NET Framework è la struttura <xref:System.DateTime?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e32f-142">The corresponding type in the .NET Framework is the <xref:System.DateTime?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e32f-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e32f-143">Example</span></span>  
 <span data-ttu-id="2e32f-144">Una variabile o una costante del tipo di dati `Date` contiene sia la data che l'ora.</span><span class="sxs-lookup"><span data-stu-id="2e32f-144">A variable or constant of the `Date` data type holds both the date and the time.</span></span> <span data-ttu-id="2e32f-145">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2e32f-145">The following example illustrates this.</span></span>  
  
```  
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e32f-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e32f-146">See also</span></span>

- <xref:System.DateTime?displayProperty=nameWithType>
- [<span data-ttu-id="2e32f-147">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="2e32f-147">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2e32f-148">Stringhe di formato di data e ora standard</span><span class="sxs-lookup"><span data-stu-id="2e32f-148">Standard Date and Time Format Strings</span></span>](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [<span data-ttu-id="2e32f-149">Custom Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="2e32f-149">Custom Date and Time Format Strings</span></span>](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [<span data-ttu-id="2e32f-150">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="2e32f-150">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2e32f-151">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="2e32f-151">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2e32f-152">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="2e32f-152">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
