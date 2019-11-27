---
title: Riferimenti e istruzione Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347270"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="569bc-102">Riferimenti e istruzione Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="569bc-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="569bc-103">È possibile rendere disponibili oggetti esterni per il progetto scegliendo il comando **Aggiungi riferimento** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="569bc-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="569bc-104">I riferimenti in Visual Basic possono puntare ad assembly, che sono simili alle librerie dei tipi ma contengono ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="569bc-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="569bc-105">Istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="569bc-105">The Imports Statement</span></span>  
 <span data-ttu-id="569bc-106">Gli assembly includono uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="569bc-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="569bc-107">Quando si aggiunge un riferimento a un assembly, è anche possibile aggiungere un'istruzione `Imports` a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="569bc-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="569bc-108">L'istruzione `Imports` fornisce un contesto di ambito che consente di utilizzare solo la parte dello spazio dei nomi necessaria per fornire un riferimento univoco.</span><span class="sxs-lookup"><span data-stu-id="569bc-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="569bc-109">L'istruzione `Imports` presenta la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="569bc-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="569bc-110">`Aliasname` fa riferimento a un nome breve che è possibile usare all'interno del codice per fare riferimento a uno spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="569bc-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="569bc-111">`Namespace` è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o tramite un'istruzione `Imports` precedente.</span><span class="sxs-lookup"><span data-stu-id="569bc-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="569bc-112">Un modulo può contenere un numero qualsiasi di istruzioni `Imports`.</span><span class="sxs-lookup"><span data-stu-id="569bc-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="569bc-113">Devono essere visualizzate dopo qualsiasi istruzione `Option`, se presente, ma prima di qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="569bc-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="569bc-114">Non confondere i riferimenti del progetto con l'istruzione `Imports` o l'istruzione `Declare`.</span><span class="sxs-lookup"><span data-stu-id="569bc-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="569bc-115">I riferimenti al progetto rendono disponibili oggetti esterni, ad esempio oggetti negli assembly, per Visual Basic progetti.</span><span class="sxs-lookup"><span data-stu-id="569bc-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="569bc-116">L'istruzione `Imports` viene utilizzata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce l'accesso a tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="569bc-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="569bc-117">L'istruzione `Declare` viene utilizzata per dichiarare un riferimento a una procedura esterna in una libreria di collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="569bc-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="569bc-118">Utilizzo degli alias con l'istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="569bc-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="569bc-119">L'istruzione `Imports` rende più semplice accedere ai metodi delle classi eliminando la necessità di digitare in modo esplicito i nomi completi dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="569bc-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="569bc-120">Gli alias consentono di assegnare un nome amichevole a una sola parte di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="569bc-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="569bc-121">Ad esempio, la sequenza ritorno a capo/avanzamento riga che determina la visualizzazione di una singola parte di testo su più righe fa parte del modulo <xref:Microsoft.VisualBasic.ControlChars> nello spazio dei nomi <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="569bc-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="569bc-122">Per usare questa costante in un programma senza un alias, è necessario digitare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="569bc-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="569bc-123">le istruzioni `Imports` devono essere sempre le prime righe immediatamente successive alle istruzioni `Option` in un modulo.</span><span class="sxs-lookup"><span data-stu-id="569bc-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="569bc-124">Il frammento di codice seguente illustra come importare e assegnare un alias al modulo <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="569bc-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="569bc-125">I riferimenti futuri a questo spazio dei nomi possono essere notevolmente più brevi:</span><span class="sxs-lookup"><span data-stu-id="569bc-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="569bc-126">Se un'istruzione `Imports` non include un nome di alias, è possibile usare gli elementi definiti nello spazio dei nomi importato nel modulo senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="569bc-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="569bc-127">Se il nome dell'alias è specificato, deve essere usato come qualificatore per i nomi contenuti in tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="569bc-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="569bc-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="569bc-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="569bc-129">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="569bc-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="569bc-130">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="569bc-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="569bc-131">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="569bc-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
