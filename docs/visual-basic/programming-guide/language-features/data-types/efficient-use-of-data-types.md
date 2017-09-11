---
title: Utilizzo efficiente dei tipi di dati (Visual Basic) | Documenti di Microsoft
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
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
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
ms.openlocfilehash: ca8d5885aea12a3f1f9cb35f08bf63c1a89e7ebc
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="9c68c-102">Utilizzo efficiente dei tipi di dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c68c-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="9c68c-103">Le variabili non dichiarate e le variabili dichiarate senza un tipo di dati vengono assegnate i `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="9c68c-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="9c68c-104">Questo facilita la scrittura di programmi rapidamente, ma è possibile che vengano eseguite più lentamente.</span><span class="sxs-lookup"><span data-stu-id="9c68c-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="9c68c-105">Tipizzazione forte</span><span class="sxs-lookup"><span data-stu-id="9c68c-105">Strong Typing</span></span>  
 <span data-ttu-id="9c68c-106">Specifica dei tipi di dati per tutte le variabili è noto come *la tipizzazione forte*.</span><span class="sxs-lookup"><span data-stu-id="9c68c-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="9c68c-107">Con la tipizzazione forte presenta diversi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="9c68c-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="9c68c-108">Consente il supporto IntelliSense per le variabili.</span><span class="sxs-lookup"><span data-stu-id="9c68c-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="9c68c-109">Ciò consente di visualizzare le relative proprietà e gli altri membri durante la digitazione del codice.</span><span class="sxs-lookup"><span data-stu-id="9c68c-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="9c68c-110">Consente di usufruire del controllo del tipo del compilatore.</span><span class="sxs-lookup"><span data-stu-id="9c68c-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="9c68c-111">Questo memorizza nella cache le istruzioni che possono avere esito negativo in fase di esecuzione a causa di errori, ad esempio overflow.</span><span class="sxs-lookup"><span data-stu-id="9c68c-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="9c68c-112">Inoltre, intercetta le chiamate ai metodi su oggetti che non li supportano.</span><span class="sxs-lookup"><span data-stu-id="9c68c-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="9c68c-113">Comporta un'esecuzione più rapida del codice.</span><span class="sxs-lookup"><span data-stu-id="9c68c-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="9c68c-114">Tipi di dati più efficienti</span><span class="sxs-lookup"><span data-stu-id="9c68c-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="9c68c-115">Per le variabili che non contengono mai frazioni, i tipi di dati integrali sono più efficienti rispetto ai tipi non integrali.</span><span class="sxs-lookup"><span data-stu-id="9c68c-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="9c68c-116">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` e `UInteger` sono i tipi numerici più efficienti.</span><span class="sxs-lookup"><span data-stu-id="9c68c-116">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="9c68c-117">Per i numeri frazionari, `Double` è il tipo di dati più efficiente, perché i processori disponibili sulle attuali piattaforme eseguono operazioni a virgola mobile a precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="9c68c-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="9c68c-118">Tuttavia, le operazioni con `Double` non sono più veloci con i tipi integrali, ad esempio `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9c68c-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="9c68c-119">Specifica il tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9c68c-119">Specifying Data Type</span></span>  
 <span data-ttu-id="9c68c-120">Utilizzare il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) per dichiarare una variabile di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="9c68c-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="9c68c-121">È possibile specificare contemporaneamente il livello di accesso tramite il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md), [protetti](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privata](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9c68c-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="9c68c-122">Conversione di caratteri</span><span class="sxs-lookup"><span data-stu-id="9c68c-122">Character Conversion</span></span>  
 <span data-ttu-id="9c68c-123">Il `AscW` e `ChrW` funzioni operano in Unicode.</span><span class="sxs-lookup"><span data-stu-id="9c68c-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="9c68c-124">È necessario utilizzarle in alternativa a `Asc` e `Chr`, che devono essere convertite in Unicode.</span><span class="sxs-lookup"><span data-stu-id="9c68c-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c68c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c68c-125">See Also</span></span>  
 <span data-ttu-id="9c68c-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A></span><span class="sxs-lookup"><span data-stu-id="9c68c-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></span></span>   
 <span data-ttu-id="9c68c-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="9c68c-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
 <span data-ttu-id="9c68c-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A></span><span class="sxs-lookup"><span data-stu-id="9c68c-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></span></span>   
 <span data-ttu-id="9c68c-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="9c68c-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>   
<span data-ttu-id="9c68c-130"> [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c68c-130"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="9c68c-131"> [Tipi di dati numerici](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="9c68c-131"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="9c68c-132"> [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="9c68c-132"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="9c68c-133"> [Uso di IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span><span class="sxs-lookup"><span data-stu-id="9c68c-133"> [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span></span>
