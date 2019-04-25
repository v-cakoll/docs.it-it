---
title: Nomi di elementi dichiarati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: 5b1f8ccc402f7f5928a33f434664b0f28d108e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61828620"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="0d6da-102">Nomi di elementi dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d6da-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="0d6da-103">Ogni elemento dichiarato è un nome, detto anche un *identificatore*, che viene usato il codice per fare riferimento a esso.</span><span class="sxs-lookup"><span data-stu-id="0d6da-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0d6da-104">Regole</span><span class="sxs-lookup"><span data-stu-id="0d6da-104">Rules</span></span>  
 <span data-ttu-id="0d6da-105">Il nome di un elemento in Visual Basic è necessario rispettare le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d6da-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
-   <span data-ttu-id="0d6da-106">Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="0d6da-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="0d6da-107">Deve contenere solo caratteri alfabetici, cifre decimali e caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="0d6da-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="0d6da-108">Deve contenere almeno un carattere alfabetico o una cifra decimale se inizia con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="0d6da-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="0d6da-109">Non deve essere lungo più di 1023 caratteri.</span><span class="sxs-lookup"><span data-stu-id="0d6da-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="0d6da-110">La lunghezza massima di 1023 caratteri inoltre valida per l'intera stringa di un nome completo, ad esempio `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="0d6da-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="0d6da-111">L'esempio seguente illustra alcuni nomi di elemento valido.</span><span class="sxs-lookup"><span data-stu-id="0d6da-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="0d6da-112">L'esempio seguente illustra alcuni nomi di elemento non valido.</span><span class="sxs-lookup"><span data-stu-id="0d6da-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="0d6da-113">Il primo contiene solo un carattere di sottolineatura, il secondo inizia con una cifra decimale e il terzo contiene un carattere non valido ($).</span><span class="sxs-lookup"><span data-stu-id="0d6da-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="0d6da-114">Nomi di elementi a partire da un carattere di sottolineatura (`_`) non fanno parte delle [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), in modo che il codice conforme a CLS non è possibile utilizzare un componente che definisce tali nomi.</span><span class="sxs-lookup"><span data-stu-id="0d6da-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="0d6da-115">Tuttavia, un carattere di sottolineatura in qualsiasi altra posizione nel nome di un elemento è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="0d6da-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="0d6da-116">Nome lunghezza orientamenti</span><span class="sxs-lookup"><span data-stu-id="0d6da-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="0d6da-117">Ai fini pratici, il nome deve essere più corte possibili durante identificare chiaramente la natura dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0d6da-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="0d6da-118">Ciò migliora la leggibilità del codice e riduce le dimensioni di file di origine e lunghezza riga.</span><span class="sxs-lookup"><span data-stu-id="0d6da-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="0d6da-119">D'altra parte, il nome non deve essere così breve che non in modo adeguato descrive ciò che rappresenta l'elemento e modo in cui il codice lo usa.</span><span class="sxs-lookup"><span data-stu-id="0d6da-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="0d6da-120">Questo è importante per la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="0d6da-120">This is important for the readability of your code.</span></span> <span data-ttu-id="0d6da-121">Se qualcun altro tenta di comprenderne il concetto, o se ne sta analizzando, molto tempo dopo che è stato scritto, i nomi degli elementi adatto può risparmiare una notevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="0d6da-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="0d6da-122">Nomi con caratteri di escape</span><span class="sxs-lookup"><span data-stu-id="0d6da-122">Escaped Names</span></span>  
 <span data-ttu-id="0d6da-123">In genere, un nome di elemento non deve corrispondere la parola chiave riservata, ad esempio da Visual Basic `Case` o `Friend`.</span><span class="sxs-lookup"><span data-stu-id="0d6da-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="0d6da-124">Tuttavia, è possibile definire un' *nome forzato*, che è racchiuso tra parentesi quadre (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="0d6da-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="0d6da-125">Un nome con caratteri di escape può corrispondere a qualsiasi parola chiave Visual Basic, poiché le parentesi quadre rimuovere qualsiasi ambiguità.</span><span class="sxs-lookup"><span data-stu-id="0d6da-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="0d6da-126">È anche possibile usare le parentesi quadre quando si fa riferimento al nome in un secondo momento nel codice.</span><span class="sxs-lookup"><span data-stu-id="0d6da-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="0d6da-127">In generale, è consigliabile usare nomi con caratteri di escape solo se:</span><span class="sxs-lookup"><span data-stu-id="0d6da-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="0d6da-128">Il codice è eseguita la migrazione da una versione precedente di Visual Basic che non era riservata la parola chiave viene usata come un nome. o</span><span class="sxs-lookup"><span data-stu-id="0d6da-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="0d6da-129">Si lavora con il codice scritto in un altro linguaggio in cui la parola chiave specificata non è riservata.</span><span class="sxs-lookup"><span data-stu-id="0d6da-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="0d6da-130">In caso contrario, è consigliabile rinominare l'elemento se il nome è in conflitto con una parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0d6da-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="0d6da-131">L'ambiente di sviluppo integrato (IDE) fornisce un modo semplice per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="0d6da-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="0d6da-132">Per altre informazioni, vedere [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="0d6da-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="0d6da-133">Distinzione maiuscole/minuscole nei nomi</span><span class="sxs-lookup"><span data-stu-id="0d6da-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="0d6da-134">I nomi degli elementi in Visual Basic sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0d6da-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="0d6da-135">Ciò significa che quando il compilatore consente di confrontare due nomi che differiscono solo nelle maiuscole, li interpreta come lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="0d6da-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="0d6da-136">Ad esempio, se si ha `ABC` e `abc` , il compilatore li interpreta come se facessero riferimento allo stesso elemento dichiarato.</span><span class="sxs-lookup"><span data-stu-id="0d6da-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="0d6da-137">Tuttavia, common language runtime (CLR) utilizza l'associazione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0d6da-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="0d6da-138">Perciò, quando si genera un assembly o una DLL e la si rende disponibile ad altri assembly, i nomi distinguono fra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0d6da-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="0d6da-139">Se ad esempio si definisce una classe con un elemento denominato `ABC`e altri assembly usano la classe mediante il Common Language Runtime, devono fare riferimento all'elemento come `ABC`.</span><span class="sxs-lookup"><span data-stu-id="0d6da-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="0d6da-140">Se si successivamente ricompila la classe e modificare il nome dell'elemento a `abc`, gli altri assembly usano la classe non è più è stato possibile accedere a quell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0d6da-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="0d6da-141">Pertanto, quando si rilascia una versione aggiornata di un assembly, non si devono modificare le maiuscole e le minuscole degli elementi pubblici.</span><span class="sxs-lookup"><span data-stu-id="0d6da-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="0d6da-142">I nomi e le impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="0d6da-142">Names and Locales</span></span>  
 <span data-ttu-id="0d6da-143">Confronto dei nomi è indipendente dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="0d6da-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="0d6da-144">Se due nomi corrisponde a una delle impostazioni locali, essi sono garantiti in modo che corrispondano in tutte le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="0d6da-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6da-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d6da-145">See also</span></span>

- [<span data-ttu-id="0d6da-146">Elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="0d6da-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="0d6da-147">Caratteristiche di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="0d6da-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="0d6da-148">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="0d6da-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="0d6da-149">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="0d6da-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
