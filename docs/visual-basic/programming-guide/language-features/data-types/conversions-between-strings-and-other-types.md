---
title: Conversioni fra stringhe e altri tipi (Visual Basic) | Documenti di Microsoft
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
- data type conversion, string
- conversions, type
- string conversion
- conversions, data type
- type conversion, string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
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
ms.openlocfilehash: 34eb32cb6e640d681db6853aaa164d84acca7e4f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="7af65-102">Conversioni fra stringhe e altri tipi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7af65-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="7af65-103">È possibile convertire un valore numerico, `Boolean`, o valore di data/ora un `String`.</span><span class="sxs-lookup"><span data-stu-id="7af65-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="7af65-104">È inoltre possibile convertire nella direzione inversa, ovvero da un valore stringa e numerici, `Boolean`, o `Date` , purché il contenuto della stringa può essere interpretato come un valore valido del tipo di dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7af65-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="7af65-105">In caso contrario, si verifica un errore di run-time.</span><span class="sxs-lookup"><span data-stu-id="7af65-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="7af65-106">Le conversioni per tutte queste assegnazioni, in entrambe le direzioni, sono conversioni di restrizione.</span><span class="sxs-lookup"><span data-stu-id="7af65-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="7af65-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span><span class="sxs-lookup"><span data-stu-id="7af65-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="7af65-108">Il <xref:Microsoft.VisualBasic.Strings.Format%2A>e <xref:Microsoft.VisualBasic.Conversion.Val%2A>funzioni forniscono un maggiore controllo sulle conversioni fra stringhe e numeri.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A></span><span class="sxs-lookup"><span data-stu-id="7af65-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="7af65-109">Se è stato definito una classe o struttura, è possibile definire operatori di conversione di tipo tra `String` e il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="7af65-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="7af65-110">Per ulteriori informazioni, vedere [procedura: definire un operatore di conversione](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7af65-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="7af65-111">Conversione di numeri in stringhe</span><span class="sxs-lookup"><span data-stu-id="7af65-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="7af65-112">È possibile utilizzare il `Format` funzione per convertire un numero in una stringa formattata, che può includere non solo le cifre appropriate ma anche simboli, ad esempio un simbolo di valuta di formattazione (ad esempio `$`), migliaia separatori o *i simboli di raggruppamento delle cifre* (come `,`) e un separatore decimale (come `.`).</span><span class="sxs-lookup"><span data-stu-id="7af65-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="7af65-113">`Format`utilizza automaticamente i simboli appropriati in base al **opzioni internazionali** impostazioni specificate nelle finestre **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="7af65-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="7af65-114">Si noti che il concatenamento (`&`) (operatore) può convertire un numero in una stringa in modo implicito, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7af65-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="7af65-115">Conversione di stringhe in numeri</span><span class="sxs-lookup"><span data-stu-id="7af65-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="7af65-116">È possibile utilizzare il `Val` funzione per convertire esplicitamente le cifre in una stringa in un numero.</span><span class="sxs-lookup"><span data-stu-id="7af65-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="7af65-117">`Val`legge la stringa fino a quando non viene rilevato un carattere diverso da una cifra, spazio, scheda, avanzamento riga o periodo.</span><span class="sxs-lookup"><span data-stu-id="7af65-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="7af65-118">Le sequenze "/ O" e "/ H" alterano la base del sistema di numerazione e terminare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="7af65-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="7af65-119">Fino a quando termina la lettura, `Val` converte tutti i caratteri appropriati in un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="7af65-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="7af65-120">Ad esempio, l'istruzione seguente restituisce il valore `141.825`.</span><span class="sxs-lookup"><span data-stu-id="7af65-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="7af65-121">Quando [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] converte una stringa in un valore numerico, utilizza il **opzioni internazionali** impostazioni specificate nelle finestre **Pannello di controllo** per interpretare le migliaia separatore, il separatore decimale e il simbolo di valuta.</span><span class="sxs-lookup"><span data-stu-id="7af65-121">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="7af65-122">Ciò significa che una conversione potrebbe avere esito positivo con un'impostazione ma non su un altro.</span><span class="sxs-lookup"><span data-stu-id="7af65-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="7af65-123">Ad esempio, `"$14.20"` accettabile nelle impostazioni locali inglese (Stati Uniti) ma non in qualsiasi lingua francese.</span><span class="sxs-lookup"><span data-stu-id="7af65-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af65-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7af65-124">See Also</span></span>  
 <span data-ttu-id="7af65-125">[Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7af65-125">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="7af65-126"> [Ampliamento e restrizione conversioni](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7af65-126"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="7af65-127"> [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7af65-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="7af65-128"> [Procedura: convertire un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="7af65-128"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="7af65-129"> [Conversioni di matrici](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7af65-129"> [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span></span>  
<span data-ttu-id="7af65-130"> [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="7af65-130"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="7af65-131"> [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="7af65-131"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="7af65-132"> [Introduzione alle applicazioni internazionali basate su .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span><span class="sxs-lookup"><span data-stu-id="7af65-132"> [Introduction to International Applications Based on the .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span></span>
