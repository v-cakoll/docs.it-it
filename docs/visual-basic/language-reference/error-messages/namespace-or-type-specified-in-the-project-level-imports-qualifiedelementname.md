---
title: "Namespace o il tipo specificato nelle importazioni a livello di progetto&lt;qualifiedelementname&gt;&quot; non contiene alcun membro pubblico o non è possibile trovare | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
dev_langs:
- VB
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
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
ms.openlocfilehash: 301e2bd419f0b4723ff76c2bdd2187c4c412e174
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="f1fb1-102">Namespace o il tipo specificato nelle importazioni a livello di progetto&lt;qualifiedelementname&gt;' non contiene alcun membro pubblico o non trovato</span><span class="sxs-lookup"><span data-stu-id="f1fb1-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="f1fb1-103">Namespace o il tipo specificato nelle importazioni a livello di progetto\<qualifiedelementname >' non contiene alcun membro pubblico o non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="f1fb1-104">Assicurarsi che lo spazio dei nomi o il tipo è definito e contiene almeno un membro pubblico.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="f1fb1-105">Assicurarsi che il nome di alias non contenga altri alias.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="f1fb1-106">Una proprietà di importazione di un progetto specifica un elemento contenitore che può essere trovato o non definisce alcun `Public` membri.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="f1fb1-107">Oggetto *contenente l'elemento* può essere un spazio dei nomi, classe, struttura, modulo, interfaccia o enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="f1fb1-108">Contiene membri, ad esempio variabili, le procedure o altri elementi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="f1fb1-109">Lo scopo dell'importazione è di consentire al codice per accedere ai membri dello spazio dei nomi o tipo senza la necessità di fornire il nome completo.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="f1fb1-110">Il progetto potrebbe essere necessario anche aggiungere un riferimento al tipo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="f1fb1-111">Per ulteriori informazioni, vedere "Importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f1fb1-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="f1fb1-112">Se il compilatore non trova l'elemento contenitore specificato, non sarà possibile risolvere i riferimenti che lo utilizzano.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="f1fb1-113">Se viene trovato l'elemento, ma l'elemento non espone alcun `Public` membri, quindi nessun riferimento può avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="f1fb1-114">In entrambi i casi è significativo per importare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="f1fb1-115">Utilizzare il **progettazione** per specificare gli elementi da importare.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="f1fb1-116">Utilizzare il **spazi dei nomi importati** sezione la **riferimenti** pagina.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="f1fb1-117">È possibile ottenere il **Progettazione progetti** facendo doppio clic su di **progetto** icona in **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="f1fb1-118">**ID errore:** BC40057</span><span class="sxs-lookup"><span data-stu-id="f1fb1-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f1fb1-119">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f1fb1-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="f1fb1-120">Aprire il **Progettazione progetti** e passare il **riferimento** pagina.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="f1fb1-121">Nel **spazi dei nomi importati** sezione, verificare che l'elemento contenitore è accessibile dal progetto.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="f1fb1-122">Verificare che l'elemento contenitore esponga almeno `Public` membro.</span><span class="sxs-lookup"><span data-stu-id="f1fb1-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1fb1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1fb1-123">See Also</span></span>  
 <span data-ttu-id="f1fb1-124">[Riferimenti (pagina), Creazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="f1fb1-124">[References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="f1fb1-125"> [NIB procedura: modificare le proprietà del progetto e le impostazioni di configurazione](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="f1fb1-125"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="f1fb1-126"> [Pubblica](../../../visual-basic/language-reference/modifiers/public.md) </span><span class="sxs-lookup"><span data-stu-id="f1fb1-126"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span></span>  
<span data-ttu-id="f1fb1-127"> [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="f1fb1-127"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="f1fb1-128"> [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="f1fb1-128"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
