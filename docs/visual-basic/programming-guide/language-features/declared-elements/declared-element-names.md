---
title: Dichiarare i nomi degli elementi (Visual Basic) | Documenti di Microsoft
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
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
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
ms.openlocfilehash: 899bcb2ecc8f5c07fdf4592e15827ff67f55c136
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="5f3da-102">Nomi di elementi dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f3da-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="5f3da-103">Ogni elemento dichiarato è un nome, detto anche un *identificatore*, il codice utilizzato per fare riferimento a esso.</span><span class="sxs-lookup"><span data-stu-id="5f3da-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5f3da-104">Regole</span><span class="sxs-lookup"><span data-stu-id="5f3da-104">Rules</span></span>  
 <span data-ttu-id="5f3da-105">Nome dell'elemento in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] deve rispettare le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f3da-105">An element name in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="5f3da-106">Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="5f3da-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="5f3da-107">Deve contenere solo caratteri alfabetici, cifre e caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="5f3da-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="5f3da-108">Deve contenere almeno un carattere alfabetico o cifra decimale che inizia con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="5f3da-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="5f3da-109">Non è necessario più di 1023 caratteri.</span><span class="sxs-lookup"><span data-stu-id="5f3da-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="5f3da-110">La lunghezza massima di 1023 caratteri si applica anche all'intera stringa di un nome completo, ad esempio `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="5f3da-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="5f3da-111">L'esempio seguente mostra alcuni nomi di elemento valido.</span><span class="sxs-lookup"><span data-stu-id="5f3da-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="5f3da-112">L'esempio seguente mostra alcuni nomi di elemento non valido.</span><span class="sxs-lookup"><span data-stu-id="5f3da-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="5f3da-113">Il primo contiene solo un carattere di sottolineatura, il secondo inizia con una cifra decimale e il terzo contiene un carattere non valido ($).</span><span class="sxs-lookup"><span data-stu-id="5f3da-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="5f3da-114">I nomi degli elementi a partire da un carattere di sottolineatura (`_`) non fanno parte del [indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che definisce tali nomi.</span><span class="sxs-lookup"><span data-stu-id="5f3da-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="5f3da-115">Tuttavia, un carattere di sottolineatura in qualsiasi altra posizione nel nome di un elemento è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="5f3da-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="5f3da-116">Linee guida per la lunghezza nome</span><span class="sxs-lookup"><span data-stu-id="5f3da-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="5f3da-117">In pratica, il nome deve essere il più breve possibile durante identificare chiaramente la natura dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="5f3da-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="5f3da-118">Ciò migliora la leggibilità del codice e si riduce la dimensione della linea di lunghezza e file di origine.</span><span class="sxs-lookup"><span data-stu-id="5f3da-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="5f3da-119">D'altra parte, il nome non deve essere troppo breve che non adeguatamente descrive ciò che rappresenta l'elemento e come utilizzato dal codice.</span><span class="sxs-lookup"><span data-stu-id="5f3da-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="5f3da-120">Ciò è importante per la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="5f3da-120">This is important for the readability of your code.</span></span> <span data-ttu-id="5f3da-121">Se qualcun altro sta tentando di capire, o dall'utente sono guardando molto tempo dopo che è stato scritto, nomi di elemento appropriato possono salvare una notevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="5f3da-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="5f3da-122">Nomi in sequenza escape</span><span class="sxs-lookup"><span data-stu-id="5f3da-122">Escaped Names</span></span>  
 <span data-ttu-id="5f3da-123">In genere, un nome di elemento non deve corrispondere alle parole chiave riservate dal [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], ad esempio `Case` o `Friend`.</span><span class="sxs-lookup"><span data-stu-id="5f3da-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="5f3da-124">Tuttavia, è possibile definire un *nome forzato*, che è racchiuso tra parentesi quadre (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="5f3da-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="5f3da-125">Un nome forzato può corrispondere a qualsiasi [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] (parola chiave), poiché le parentesi quadre rimuovere qualsiasi ambiguità.</span><span class="sxs-lookup"><span data-stu-id="5f3da-125">An escaped name can match any [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="5f3da-126">È inoltre possibile utilizzare le parentesi quando si fa riferimento al nome nel codice.</span><span class="sxs-lookup"><span data-stu-id="5f3da-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="5f3da-127">In generale, è necessario utilizzare nomi in sequenza escape solo quando:</span><span class="sxs-lookup"><span data-stu-id="5f3da-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="5f3da-128">Il codice è stata eseguita la migrazione da una versione precedente di [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] che non era riservata la parola chiave viene utilizzata come un nome; o</span><span class="sxs-lookup"><span data-stu-id="5f3da-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="5f3da-129">Si lavora con il codice scritto in un'altra lingua in cui non è riservata alla parola chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="5f3da-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="5f3da-130">In caso contrario, è consigliabile rinominare l'elemento se il relativo nome in conflitto con una parola chiave.</span><span class="sxs-lookup"><span data-stu-id="5f3da-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="5f3da-131">Ambiente di sviluppo integrato (IDE) fornisce un modo semplice per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="5f3da-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="5f3da-132">Per ulteriori informazioni, vedere [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="5f3da-132">For more information, see [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="5f3da-133">Distinzione maiuscole/minuscole nei nomi</span><span class="sxs-lookup"><span data-stu-id="5f3da-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="5f3da-134">I nomi di elemento in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="5f3da-134">Element names in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] are case-insensitive.</span></span> <span data-ttu-id="5f3da-135">Ciò significa che quando il compilatore confronta due nomi che differiscono solo nelle maiuscole, li interpreta come lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="5f3da-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="5f3da-136">Ad esempio, se si ha `ABC` e `abc` , il compilatore li interpreta come se facessero riferimento allo stesso elemento dichiarato.</span><span class="sxs-lookup"><span data-stu-id="5f3da-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="5f3da-137">Tuttavia, common language runtime (CLR) utilizza l'associazione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="5f3da-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="5f3da-138">Perciò, quando si genera un assembly o una DLL e la si rende disponibile ad altri assembly, i nomi distinguono fra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="5f3da-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="5f3da-139">Se ad esempio si definisce una classe con un elemento denominato `ABC`e altri assembly usano la classe mediante il Common Language Runtime, devono fare riferimento all'elemento come `ABC`.</span><span class="sxs-lookup"><span data-stu-id="5f3da-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="5f3da-140">Se si successivamente ricompilare la classe e modificare il nome dell'elemento per `abc`, gli altri assembly che utilizzano la classe non è più possano accedere all'elemento.</span><span class="sxs-lookup"><span data-stu-id="5f3da-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="5f3da-141">Pertanto, quando si rilascia una versione aggiornata di un assembly, non si devono modificare le maiuscole e le minuscole degli elementi pubblici.</span><span class="sxs-lookup"><span data-stu-id="5f3da-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="5f3da-142">I nomi e le impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="5f3da-142">Names and Locales</span></span>  
 <span data-ttu-id="5f3da-143">Confronto dei nomi è indipendente dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="5f3da-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="5f3da-144">Se due nomi corrispondono in una lingua, è possibile garantirne la corrispondenza in tutte le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="5f3da-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3da-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f3da-145">See Also</span></span>  
 <span data-ttu-id="5f3da-146">[Elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f3da-146">[Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span></span>  
<span data-ttu-id="5f3da-147"> [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="5f3da-147"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="5f3da-148"> [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="5f3da-148"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="5f3da-149"> [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="5f3da-149"> [Statements](../../../../visual-basic/language-reference/statements/index.md)</span></span>
