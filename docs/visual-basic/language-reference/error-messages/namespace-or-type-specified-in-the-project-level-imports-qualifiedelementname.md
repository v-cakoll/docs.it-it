---
title: Lo spazio dei nomi o il tipo specificato nelle importazioni '<qualifiedelementname>' a livello di progetto non contiene alcun membro pubblico o non è definito
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 0ee235252d69e6f77ce53b048f45e73d0969e864
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409452"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="a703b-102">Lo spazio dei nomi o il tipo specificato nelle importazioni '\<qualifiedelementname>' a livello di progetto non contiene alcun membro pubblico o non è definito</span><span class="sxs-lookup"><span data-stu-id="a703b-102">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>
<span data-ttu-id="a703b-103">Lo spazio dei nomi o il tipo specificato nelle importazioni a livello di progetto ' \<qualifiedelementname> ' non contiene alcun membro pubblico o non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="a703b-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="a703b-104">Verificare che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico.</span><span class="sxs-lookup"><span data-stu-id="a703b-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="a703b-105">Verificare che il nome dell'alias non contenga altri alias.</span><span class="sxs-lookup"><span data-stu-id="a703b-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="a703b-106">Una proprietà import di un progetto specifica un elemento contenitore che non può essere trovato o non definisce `Public` membri.</span><span class="sxs-lookup"><span data-stu-id="a703b-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="a703b-107">Un *elemento contenitore* può essere uno spazio dei nomi, una classe, una struttura, un modulo, un'interfaccia o un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a703b-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="a703b-108">L'elemento contenitore contiene membri, ad esempio variabili, procedure o altri elementi contenenti.</span><span class="sxs-lookup"><span data-stu-id="a703b-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="a703b-109">Lo scopo dell'importazione è consentire al codice di accedere ai membri dello spazio dei nomi o ai tipi senza doverli qualificare.</span><span class="sxs-lookup"><span data-stu-id="a703b-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="a703b-110">Il progetto potrebbe anche dover aggiungere un riferimento allo spazio dei nomi o al tipo.</span><span class="sxs-lookup"><span data-stu-id="a703b-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="a703b-111">Per ulteriori informazioni, vedere "importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="a703b-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="a703b-112">Se il compilatore non riesce a trovare l'elemento contenitore specificato, non può risolvere i riferimenti che lo usano.</span><span class="sxs-lookup"><span data-stu-id="a703b-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="a703b-113">Se trova l'elemento, ma l'elemento non espone `Public` membri, nessun riferimento può avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a703b-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="a703b-114">In entrambi i casi non è significativo importare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="a703b-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="a703b-115">Per specificare gli elementi da importare, è possibile utilizzare **Progettazione progetti** .</span><span class="sxs-lookup"><span data-stu-id="a703b-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="a703b-116">Utilizzare la sezione **spazi dei nomi importati** della pagina **riferimenti** .</span><span class="sxs-lookup"><span data-stu-id="a703b-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="a703b-117">È possibile ottenere la creazione di **progetti** facendo doppio clic sull'icona del **progetto** in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="a703b-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="a703b-118">**ID errore:** BC40057</span><span class="sxs-lookup"><span data-stu-id="a703b-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a703b-119">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a703b-119">To correct this error</span></span>  
  
1. <span data-ttu-id="a703b-120">Aprire **Progettazione progetti** e passare alla pagina di **riferimento** .</span><span class="sxs-lookup"><span data-stu-id="a703b-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2. <span data-ttu-id="a703b-121">Nella sezione **spazi dei nomi importati** verificare che l'elemento contenitore sia accessibile dal progetto.</span><span class="sxs-lookup"><span data-stu-id="a703b-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3. <span data-ttu-id="a703b-122">Verificare che l'elemento contenitore esponga almeno un `Public` membro.</span><span class="sxs-lookup"><span data-stu-id="a703b-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a703b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a703b-123">See also</span></span>

- [<span data-ttu-id="a703b-124">Riferimenti (pagina), Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a703b-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="a703b-125">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="a703b-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="a703b-126">Pubblica</span><span class="sxs-lookup"><span data-stu-id="a703b-126">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="a703b-127">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a703b-127">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="a703b-128">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="a703b-128">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
