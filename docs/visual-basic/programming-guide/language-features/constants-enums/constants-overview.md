---
title: Cenni preliminari sulle costanti (Visual Basic) | Documenti di Microsoft
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
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
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
ms.openlocfilehash: 2df21b9e3e814c654b355472aa645481060c6f68
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="b8c16-102">Cenni preliminari sulle costanti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8c16-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="b8c16-103">Una costante è un nome significativo che prende il posto di un numero o una stringa che non cambia.</span><span class="sxs-lookup"><span data-stu-id="b8c16-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="b8c16-104">Costanti di archiviano i valori, come suggerisce il nome, rimangono invariati nel corso dell'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8c16-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="b8c16-105">Notevolmente, è possibile migliorare la leggibilità del codice e semplificare la gestione tramite l'utilizzo di costanti.</span><span class="sxs-lookup"><span data-stu-id="b8c16-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="b8c16-106">Utilizzarle nel codice che contiene valori che vengono ripetuti o che dipendono da alcuni numeri che sono difficili da ricordare o non hanno alcun significato evidente.</span><span class="sxs-lookup"><span data-stu-id="b8c16-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="b8c16-107">Come creare e utilizzare le costanti</span><span class="sxs-lookup"><span data-stu-id="b8c16-107">How to Create and Use Constants</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b8c16-108">contiene un numero di costanti predefinite, utilizzate principalmente per la stampa e visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8c16-108"> contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="b8c16-109">È inoltre possibile creare costanti personalizzate mediante la `Const` istruzione, utilizzando le stesse linee guida per la creazione di un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="b8c16-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="b8c16-110">Se `Option Strict` è `On`, è necessario dichiarare in modo esplicito il tipo di costante.</span><span class="sxs-lookup"><span data-stu-id="b8c16-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="b8c16-111">Ambito di una costante, ovvero il set di tutto il codice che è possibile farvi riferimento senza la qualifica del nome è uguale a quello di una variabile dichiarata nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="b8c16-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="b8c16-112">Per creare una costante che esista nell'ambito di una particolare procedura, dichiararla all'interno di tale procedura.</span><span class="sxs-lookup"><span data-stu-id="b8c16-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="b8c16-113">Per creare una costante che sia disponibile in tutta l'applicazione, dichiararla utilizzando il `Public` (parola chiave) nella sezione dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="b8c16-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8c16-114">Sebbene costanti siano simili variabili, è possibile modificarle o assegnare di nuovi valori, come per le variabili.</span><span class="sxs-lookup"><span data-stu-id="b8c16-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="b8c16-115">Le costanti utilizzate nel codice possono essere definite dal modello a oggetti per i controlli o ai componenti utilizzati, o possono essere definiti dall'utente (vale a dire quelle create dall'utente).</span><span class="sxs-lookup"><span data-stu-id="b8c16-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="b8c16-116">Costanti in fase di compilazione e Runtime</span><span class="sxs-lookup"><span data-stu-id="b8c16-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="b8c16-117">Una costante in fase di compilazione viene calcolata al momento che il codice viene compilato, mentre una costante in fase di esecuzione può essere calcolata solo mentre è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8c16-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="b8c16-118">Una costante in fase di compilazione avrà lo stesso valore ogni volta che viene eseguita un'applicazione, mentre una costante in fase di esecuzione potrebbe cambiare ogni volta.</span><span class="sxs-lookup"><span data-stu-id="b8c16-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="b8c16-119">Costanti in fase di compilazione sono necessarie per i casi, ad esempio i limiti di matrice, le espressioni case o gli inizializzatori degli enumeratori.</span><span class="sxs-lookup"><span data-stu-id="b8c16-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8c16-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b8c16-120">In This Section</span></span>  
  
|<span data-ttu-id="b8c16-121">Definizione</span><span class="sxs-lookup"><span data-stu-id="b8c16-121">Definition</span></span>|<span data-ttu-id="b8c16-122">Termine</span><span class="sxs-lookup"><span data-stu-id="b8c16-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="b8c16-123">Procedura: Dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="b8c16-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="b8c16-124">Viene illustrato come utilizzare il `Const` istruzione per dichiarare una costante e impostarne il valore; dichiarando una costante, assegnare un nome significativo per il valore.</span><span class="sxs-lookup"><span data-stu-id="b8c16-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="b8c16-125">Costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="b8c16-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="b8c16-126">Viene descritto come creare costanti personalizzate, incluse le informazioni sulla definizione dell'ambito e come evitare riferimenti circolari.</span><span class="sxs-lookup"><span data-stu-id="b8c16-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="b8c16-127">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="b8c16-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="b8c16-128">Vengono fornite informazioni su come il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore Inizializza le costanti quando `Option Explicit` è disattivato.</span><span class="sxs-lookup"><span data-stu-id="b8c16-128">Provides information on how the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="b8c16-129">Procedura: Raggruppare i valori delle costanti correlate</span><span class="sxs-lookup"><span data-stu-id="b8c16-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="b8c16-130">Viene illustrato come raggruppare i valori costanti che sono correlati.</span><span class="sxs-lookup"><span data-stu-id="b8c16-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="b8c16-131">Riferimento</span><span class="sxs-lookup"><span data-stu-id="b8c16-131">Reference</span></span>  
  
|<span data-ttu-id="b8c16-132">Definizione</span><span class="sxs-lookup"><span data-stu-id="b8c16-132">Definition</span></span>|<span data-ttu-id="b8c16-133">Termine</span><span class="sxs-lookup"><span data-stu-id="b8c16-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="b8c16-134">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b8c16-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="b8c16-135">Vengono elencate le costanti predefinite da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8c16-135">Lists the constants predefined by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>|  
|[<span data-ttu-id="b8c16-136">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="b8c16-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="b8c16-137">Viene descritto il `Const` istruzione e il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="b8c16-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="b8c16-138">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="b8c16-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="b8c16-139">Viene descritto il `Option Strict` istruzione e il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="b8c16-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8c16-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8c16-140">See Also</span></span>  
 <span data-ttu-id="b8c16-141">[Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b8c16-141">[Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="b8c16-142"> [Procedura: inizializzare una variabile di matrice in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b8c16-142"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
