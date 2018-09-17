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
ms.openlocfilehash: 89d360e5caa3cdb0dd1ecb985ea7ba727e5a6d9d
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45692671"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="a33fb-102">Riferimenti e istruzione Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a33fb-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="a33fb-103">È possibile rendere gli oggetti esterni disponibili al progetto scegliendo il **Aggiungi riferimento** comando le **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="a33fb-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="a33fb-104">I riferimenti in Visual Basic possono puntare agli assembly, che sono come le librerie dei tipi ma contengono ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="a33fb-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="a33fb-105">Istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="a33fb-105">The Imports Statement</span></span>  
 <span data-ttu-id="a33fb-106">Assembly includono uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a33fb-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="a33fb-107">Quando si aggiunge un riferimento a un assembly, è anche possibile aggiungere un `Imports` istruzione a un modulo che controlla la visibilità degli spazi dei nomi dell'assembly all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="a33fb-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="a33fb-108">Il `Imports` istruzione fornisce un contesto dell'ambito che ti permette di usare solo la parte dello spazio dei nomi necessari per fornire un riferimento univoco.</span><span class="sxs-lookup"><span data-stu-id="a33fb-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="a33fb-109">Il `Imports` istruzione ha la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a33fb-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="a33fb-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="a33fb-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="a33fb-111">`Aliasname` fa riferimento a un nome breve che è possibile usare all'interno del codice per fare riferimento a uno spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="a33fb-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="a33fb-112">`Namespace` è uno spazio dei nomi disponibile tramite un riferimento al progetto, tramite una definizione all'interno del progetto o una precedente `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a33fb-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="a33fb-113">Un modulo può contenere un numero qualsiasi di `Imports` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a33fb-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="a33fb-114">È necessario specificarle dopo qualsiasi `Option` (istruzioni), se presente, ma prima di qualsiasi altro codice.</span><span class="sxs-lookup"><span data-stu-id="a33fb-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a33fb-115">Non confondere i riferimenti di progetto con il `Imports` istruzione o il `Declare` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a33fb-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="a33fb-116">I riferimenti al progetto rendere gli oggetti esterni, ad esempio oggetti negli assembly, disponibili per i progetti Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a33fb-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="a33fb-117">Il `Imports` istruzione viene usata per semplificare l'accesso ai riferimenti del progetto, ma non fornisce l'accesso a questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="a33fb-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="a33fb-118">Il `Declare` istruzione viene usata per dichiarare un riferimento a una routine esterna in una libreria di collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="a33fb-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="a33fb-119">Utilizzo degli alias con l'istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="a33fb-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="a33fb-120">Il `Imports` istruzione semplifica l'accesso ai metodi delle classi, eliminando la necessità di tipizzare in modo esplicito i nomi completi dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a33fb-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="a33fb-121">Gli alias consentono di assegnare un nome più descrittivo a una sola parte di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a33fb-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="a33fb-122">Ad esempio, il ritorno a capo/avanzamento riga sequenza che provoca un'unica parte di testo da visualizzare su più righe fa parte del <xref:Microsoft.VisualBasic.ControlChars> modulo nel <xref:Microsoft.VisualBasic?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a33fb-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a33fb-123">Per usare questa costante in un programma senza un alias, è necessario digitare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a33fb-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="a33fb-124">`Imports` le istruzioni devono sempre essere le prime righe immediatamente successive alle `Option` istruzioni in un modulo.</span><span class="sxs-lookup"><span data-stu-id="a33fb-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="a33fb-125">Il frammento di codice seguente viene illustrato come importare e assegnare un alias per il <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modulo:</span><span class="sxs-lookup"><span data-stu-id="a33fb-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="a33fb-126">I riferimenti futuri di questo spazio dei nomi possono essere notevolmente più brevi:</span><span class="sxs-lookup"><span data-stu-id="a33fb-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="a33fb-127">Se un `Imports` istruzione non include un nome di alias, gli elementi definiti nello spazio dei nomi importato possono essere usati nel modulo senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="a33fb-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="a33fb-128">Se viene specificato il nome dell'alias, deve essere usato come qualificatore per i nomi dei contenuti all'interno di tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a33fb-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33fb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a33fb-129">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="a33fb-130">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a33fb-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
- [<span data-ttu-id="a33fb-131">Assembly e Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a33fb-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="a33fb-132">Procedura: Creare e usare assembly dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="a33fb-132">How to: Create and Use Assemblies Using the Command Line</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)  
- [<span data-ttu-id="a33fb-133">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="a33fb-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
