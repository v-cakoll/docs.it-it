---
title: Riferimenti e istruzione Imports (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: d767f42f8c836995064623b4aca15c86c98ec643
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651850"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="ed94c-102">Riferimenti e istruzione Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed94c-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="ed94c-103">È possibile rendere gli oggetti esterni disponibili al progetto scegliendo il **Aggiungi riferimento** comando il **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="ed94c-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="ed94c-104">Riferimenti in Visual Basic possono puntare a assembly, ovvero come librerie dei tipi, ma contengono ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="ed94c-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="ed94c-105">Istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="ed94c-105">The Imports Statement</span></span>  
 <span data-ttu-id="ed94c-106">Gli assembly includono uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ed94c-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="ed94c-107">Quando si aggiunge un riferimento a un assembly, è inoltre possibile aggiungere un `Imports` istruzione a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="ed94c-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="ed94c-108">Il `Imports` istruzione fornisce un contesto di ambito che consente di utilizzare solo la parte dello spazio dei nomi necessari per fornire un riferimento univoco.</span><span class="sxs-lookup"><span data-stu-id="ed94c-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="ed94c-109">Il `Imports` istruzione presenta la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ed94c-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="ed94c-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="ed94c-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="ed94c-111">`Aliasname` fa riferimento a un nome breve, che è possibile utilizzare all'interno di codice per fare riferimento a uno spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="ed94c-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="ed94c-112">`Namespace` è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o tramite una precedente `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="ed94c-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="ed94c-113">Un modulo può contenere un numero qualsiasi di `Imports` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="ed94c-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="ed94c-114">È necessario specificarle dopo qualsiasi `Option` istruzioni, se presente, ma prima di qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="ed94c-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed94c-115">Non confondere i riferimenti di progetto con il `Imports` istruzione o `Declare` istruzione.</span><span class="sxs-lookup"><span data-stu-id="ed94c-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="ed94c-116">Riferimenti al progetto rendono oggetti esterni, ad esempio oggetti negli assembly, disponibili per i progetti di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ed94c-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="ed94c-117">Il `Imports` istruzione viene utilizzata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce accesso a questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="ed94c-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="ed94c-118">Il `Declare` istruzione viene utilizzata per dichiarare un riferimento a una routine esterna in una libreria di collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="ed94c-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="ed94c-119">Utilizzo degli alias con l'istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="ed94c-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="ed94c-120">Il `Imports` istruzione semplifica l'accesso ai metodi delle classi, eliminando la necessità di tipo in modo esplicito il nome completo dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="ed94c-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="ed94c-121">Gli alias consentono di assegnare un nome più descrittivo solo una parte di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ed94c-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="ed94c-122">Ad esempio, il ritorno a capo/avanzamento riga sequenza che provoca un'unica parte di testo da visualizzare su più righe fa parte del <xref:Microsoft.VisualBasic.ControlChars> modulo il <xref:Microsoft.VisualBasic?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ed94c-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="ed94c-123">Per utilizzare questa costante in un programma senza un alias, è necessario digitare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ed94c-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="ed94c-124">`Imports` le istruzioni devono essere sempre le prime righe immediatamente dopo eventuali `Option` istruzioni in un modulo.</span><span class="sxs-lookup"><span data-stu-id="ed94c-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="ed94c-125">Frammento di codice seguente viene illustrato come importare e assegnare un alias per il <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modulo:</span><span class="sxs-lookup"><span data-stu-id="ed94c-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="ed94c-126">I riferimenti futuri a questo spazio dei nomi possono essere notevolmente inferiore:</span><span class="sxs-lookup"><span data-stu-id="ed94c-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="ed94c-127">Se un `Imports` istruzione non include un nome di alias, gli elementi definiti nello spazio dei nomi importato possono essere usati nel modulo senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="ed94c-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="ed94c-128">Se viene specificato il nome dell'alias, deve essere utilizzato come qualificatore per i nomi dei contenuti all'interno di tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ed94c-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed94c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed94c-129">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [<span data-ttu-id="ed94c-130">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed94c-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="ed94c-131">Assembly e Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="ed94c-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="ed94c-132">Procedura: Creare e usare assembly dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="ed94c-132">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="ed94c-133">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="ed94c-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
