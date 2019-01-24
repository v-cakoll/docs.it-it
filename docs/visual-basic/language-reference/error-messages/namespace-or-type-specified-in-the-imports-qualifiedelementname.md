---
title: Namespace o il tipo specificato nelle istruzioni Imports &#39; &lt;nomeelementoqualificato&gt; &#39; &#39;t contiene membri pubblici o non è stata trovata
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 21c0794fb4ed6104204fba5d49e37394eff24865
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552138"
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="d72b5-102">Namespace o il tipo specificato nelle istruzioni Imports &#39; &lt;nomeelementoqualificato&gt; &#39; &#39;t contiene membri pubblici o non è stata trovata</span><span class="sxs-lookup"><span data-stu-id="d72b5-102">Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="d72b5-103">Namespace o il tipo specificato nelle istruzioni 'Imports\<nomeelementoqualificato >' non contiene alcun membro pubblico o non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="d72b5-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="d72b5-104">Assicurarsi che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico.</span><span class="sxs-lookup"><span data-stu-id="d72b5-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="d72b5-105">Assicurarsi che il nome di alias non contenga altri alias.</span><span class="sxs-lookup"><span data-stu-id="d72b5-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="d72b5-106">Un' `Imports` istruzione specifica un elemento contenitore che può essere trovato o non definisce alcun `Public` membri.</span><span class="sxs-lookup"><span data-stu-id="d72b5-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="d72b5-107">Oggetto *contenente l'elemento* può essere un spazio dei nomi, classe, struttura, modulo, interfaccia o enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d72b5-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="d72b5-108">L'elemento contenitore contiene membri, ad esempio variabili, routine o altri elementi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="d72b5-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="d72b5-109">Lo scopo dell'importazione è di consentire al codice per accedere ai membri dello spazio dei nomi o un tipo senza dover fornire il nome completo.</span><span class="sxs-lookup"><span data-stu-id="d72b5-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="d72b5-110">Il progetto potrebbe essere necessario anche aggiungere un riferimento al tipo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d72b5-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="d72b5-111">Per altre informazioni, vedere "Importazione di elementi contenitore" nella [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d72b5-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="d72b5-112">Se il compilatore non trova l'elemento contenitore specificato, non sarà possibile risolvere i riferimenti che lo usano.</span><span class="sxs-lookup"><span data-stu-id="d72b5-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="d72b5-113">Se viene trovato l'elemento ma l'elemento non espone alcun `Public` membri, non esiste alcun riferimento può essere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d72b5-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="d72b5-114">In entrambi i casi è significativo per l'elemento import.</span><span class="sxs-lookup"><span data-stu-id="d72b5-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="d72b5-115">Tenere presente che se si importa un elemento che lo contiene e assegnarvi un alias di importazione, quindi è possibile usare tale alias di importazione per importare un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="d72b5-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="d72b5-116">Il codice seguente genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d72b5-116">The following code generates a compiler error.</span></span>  
  
 <span data-ttu-id="d72b5-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span><span class="sxs-lookup"><span data-stu-id="d72b5-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span></span>  
  
 <span data-ttu-id="d72b5-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span><span class="sxs-lookup"><span data-stu-id="d72b5-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span></span>  
  
 <span data-ttu-id="d72b5-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span><span class="sxs-lookup"><span data-stu-id="d72b5-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span></span>  
  
 <span data-ttu-id="d72b5-120">**ID errore:** BC40056</span><span class="sxs-lookup"><span data-stu-id="d72b5-120">**Error ID:** BC40056</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d72b5-121">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d72b5-121">To correct this error</span></span>  
  
1.  <span data-ttu-id="d72b5-122">Verificare che l'elemento contenitore è accessibile dal progetto.</span><span class="sxs-lookup"><span data-stu-id="d72b5-122">Verify that the containing element is accessible from your project.</span></span>  
  
2.  <span data-ttu-id="d72b5-123">Verificare che la specifica dell'elemento contenitore non è inclusa qualsiasi alias di importazione da un'altra importazione.</span><span class="sxs-lookup"><span data-stu-id="d72b5-123">Verify that the specification of the containing element does not include any import alias from another import.</span></span>  
  
3.  <span data-ttu-id="d72b5-124">Verificare che l'elemento contenitore espone ad almeno uno `Public` membro.</span><span class="sxs-lookup"><span data-stu-id="d72b5-124">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72b5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d72b5-125">See also</span></span>
- [<span data-ttu-id="d72b5-126">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="d72b5-126">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="d72b5-127">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="d72b5-127">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="d72b5-128">Public</span><span class="sxs-lookup"><span data-stu-id="d72b5-128">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="d72b5-129">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d72b5-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="d72b5-130">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="d72b5-130">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
