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
ms.openlocfilehash: 5b810af86f8659ffbe27d23d36aece408516a9bd
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972051"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="70083-102">Riferimenti e istruzione Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70083-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="70083-103">È possibile rendere disponibili oggetti esterni per il progetto scegliendo il comando **Aggiungi riferimento** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="70083-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="70083-104">I riferimenti in Visual Basic possono puntare ad assembly, che sono simili alle librerie dei tipi ma contengono ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="70083-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="70083-105">Istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="70083-105">The Imports Statement</span></span>  
 <span data-ttu-id="70083-106">Gli assembly includono uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="70083-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="70083-107">Quando si aggiunge un riferimento a un assembly, è anche possibile aggiungere un' `Imports` istruzione a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="70083-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="70083-108">L' `Imports` istruzione fornisce un contesto di ambito che consente di utilizzare solo la parte dello spazio dei nomi necessaria per fornire un riferimento univoco.</span><span class="sxs-lookup"><span data-stu-id="70083-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="70083-109">L' `Imports` istruzione ha la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="70083-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="70083-110">`Aliasname`fa riferimento a un nome breve che è possibile utilizzare all'interno del codice per fare riferimento a uno spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="70083-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="70083-111">`Namespace`è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o tramite `Imports` un'istruzione precedente.</span><span class="sxs-lookup"><span data-stu-id="70083-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="70083-112">Un modulo può contenere un numero qualsiasi `Imports` di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="70083-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="70083-113">Devono essere visualizzate dopo qualsiasi `Option` istruzione, se presente, ma prima di qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="70083-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70083-114">Non confondere i riferimenti del progetto `Imports` con l'istruzione `Declare` o l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="70083-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="70083-115">I riferimenti al progetto rendono disponibili oggetti esterni, ad esempio oggetti negli assembly, per Visual Basic progetti.</span><span class="sxs-lookup"><span data-stu-id="70083-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="70083-116">L' `Imports` istruzione viene utilizzata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce l'accesso a tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="70083-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="70083-117">L' `Declare` istruzione viene utilizzata per dichiarare un riferimento a una procedura esterna in una libreria di collegamento dinamico (dll).</span><span class="sxs-lookup"><span data-stu-id="70083-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="70083-118">Utilizzo degli alias con l'istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="70083-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="70083-119">L' `Imports` istruzione semplifica l'accesso ai metodi delle classi eliminando la necessità di digitare in modo esplicito i nomi completi dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="70083-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="70083-120">Gli alias consentono di assegnare un nome amichevole a una sola parte di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="70083-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="70083-121">Ad esempio, la sequenza ritorno a capo/avanzamento riga che causa la visualizzazione di una singola porzione di testo su più righe fa parte del <xref:Microsoft.VisualBasic.ControlChars> modulo <xref:Microsoft.VisualBasic?displayProperty=nameWithType> nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="70083-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="70083-122">Per usare questa costante in un programma senza un alias, è necessario digitare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="70083-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="70083-123">`Imports`le istruzioni devono essere sempre le prime righe immediatamente successive `Option` a qualsiasi istruzione in un modulo.</span><span class="sxs-lookup"><span data-stu-id="70083-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="70083-124">Il frammento di codice seguente illustra come importare e assegnare un alias al <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modulo:</span><span class="sxs-lookup"><span data-stu-id="70083-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="70083-125">I riferimenti futuri a questo spazio dei nomi possono essere notevolmente più brevi:</span><span class="sxs-lookup"><span data-stu-id="70083-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="70083-126">Se un' `Imports` istruzione non include un nome di alias, è possibile usare gli elementi definiti nello spazio dei nomi importato nel modulo senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="70083-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="70083-127">Se il nome dell'alias è specificato, deve essere usato come qualificatore per i nomi contenuti in tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="70083-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70083-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70083-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="70083-129">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70083-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="70083-130">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="70083-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="70083-131">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="70083-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
