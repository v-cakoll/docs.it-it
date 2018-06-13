---
title: Namespace o il tipo specificato nelle importazioni a livello di progetto &#39; &lt;nomeelementoqualificato&gt; &#39; &#39;t contiene membri pubblici o non è stato trovato
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: d6d0c931262d892ec3e65888a76f25218b23d868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595813"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="699cf-102">Namespace o il tipo specificato nelle importazioni a livello di progetto &#39; &lt;nomeelementoqualificato&gt; &#39; &#39;t contiene membri pubblici o non è stato trovato</span><span class="sxs-lookup"><span data-stu-id="699cf-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="699cf-103">Namespace o il tipo specificato nelle importazioni a livello di progetto\<nomelementoqualificato >' non contiene alcun membro pubblico o non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="699cf-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="699cf-104">Verificare che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico.</span><span class="sxs-lookup"><span data-stu-id="699cf-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="699cf-105">Assicurarsi che il nome di alias non contenga altri alias.</span><span class="sxs-lookup"><span data-stu-id="699cf-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="699cf-106">Una proprietà di importazione di un progetto specifica un elemento contenitore che può essere trovato o non definisce alcun `Public` membri.</span><span class="sxs-lookup"><span data-stu-id="699cf-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="699cf-107">Oggetto *contenente l'elemento* può essere un spazio dei nomi, classe, struttura, modulo, interfaccia o enumerazione.</span><span class="sxs-lookup"><span data-stu-id="699cf-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="699cf-108">Contiene membri, ad esempio variabili, procedure o altri elementi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="699cf-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="699cf-109">Lo scopo di importazione è di consentire al codice per accedere ai membri di tipo o spazio dei nomi senza dover fornire il nome completo.</span><span class="sxs-lookup"><span data-stu-id="699cf-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="699cf-110">Il progetto potrebbe essere necessario anche aggiungere un riferimento al tipo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="699cf-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="699cf-111">Per ulteriori informazioni, vedere "Importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="699cf-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="699cf-112">Se il compilatore non trova l'elemento contenitore specificato, non sarà possibile risolvere i riferimenti che lo utilizzano.</span><span class="sxs-lookup"><span data-stu-id="699cf-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="699cf-113">Se viene trovato l'elemento, ma l'elemento non espone alcun `Public` membri, quindi alcun riferimento può avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="699cf-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="699cf-114">In entrambi i casi è significativo per importare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="699cf-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="699cf-115">Utilizzare il **progettazione** per specificare gli elementi da importare.</span><span class="sxs-lookup"><span data-stu-id="699cf-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="699cf-116">Utilizzare il **spazi dei nomi importati** sezione la **riferimenti** pagina.</span><span class="sxs-lookup"><span data-stu-id="699cf-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="699cf-117">È possibile ottenere il **Progettazione progetti** facendo doppio clic su di **progetto** icona in **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="699cf-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="699cf-118">**ID errore:** BC40057</span><span class="sxs-lookup"><span data-stu-id="699cf-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="699cf-119">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="699cf-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="699cf-120">Aprire il **Progettazione progetti** e passare il **riferimento** pagina.</span><span class="sxs-lookup"><span data-stu-id="699cf-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="699cf-121">Nel **spazi dei nomi importati** sezione, verificare che l'elemento contenitore sia accessibile dal progetto.</span><span class="sxs-lookup"><span data-stu-id="699cf-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="699cf-122">Verificare che l'elemento contenitore esponga almeno `Public` membro.</span><span class="sxs-lookup"><span data-stu-id="699cf-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699cf-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="699cf-123">See Also</span></span>  
 [<span data-ttu-id="699cf-124">Pagina Riferimenti, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="699cf-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [<span data-ttu-id="699cf-125">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="699cf-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="699cf-126">Public</span><span class="sxs-lookup"><span data-stu-id="699cf-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="699cf-127">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="699cf-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="699cf-128">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="699cf-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
