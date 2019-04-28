---
title: Compilazione condizionale in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758457"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="0ac9c-102">Compilazione condizionale in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ac9c-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="0ac9c-103">Nelle *compilazione condizionale*, determinati blocchi di codice in un programma vengono compilati in modo selettivo, mentre altre vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="0ac9c-104">Ad esempio, è possibile scrivere il debug di istruzioni che confrontano la velocità dei diversi approcci per l'attività di programmazione stesso, oppure è possibile localizzare un'applicazione per più lingue.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="0ac9c-105">Le istruzioni di compilazione condizionale sono progettate per l'esecuzione durante la fase di compilazione, non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="0ac9c-106">È possibile indicare i blocchi di codice da compilare in modo condizionale con il `#If...Then...#Else` direttiva.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="0ac9c-107">Ad esempio, per creare il francese e tedesco versioni della stessa applicazione dallo stesso codice sorgente, si incorporano i segmenti di codice specifico della piattaforma nel `#If...Then` istruzioni che utilizzano costanti predefinite `FrenchVersion` e `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="0ac9c-108">Nell'esempio seguente viene illustrato come:</span><span class="sxs-lookup"><span data-stu-id="0ac9c-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="0ac9c-109">Se si imposta il valore della `FrenchVersion` costante di compilazione condizionale a `True` in fase di compilazione, il codice condizionale per la versione francese viene compilato.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="0ac9c-110">Se si imposta il valore della `GermanVersion` costante a `True`, il compilatore Usa la versione tedesca.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="0ac9c-111">Se nessuna delle due è impostata su `True`, il codice nell'ultimo `Else` bloccare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ac9c-112">Completamento automatico verrà non funziona quando la modifica del codice e l'uso di direttive di compilazione condizionale se il codice non fa parte di current branch.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="0ac9c-113">La dichiarazione di costanti di compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="0ac9c-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="0ac9c-114">È possibile impostare le costanti di compilazione condizionale in uno dei tre modi:</span><span class="sxs-lookup"><span data-stu-id="0ac9c-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="0ac9c-115">Nel **Progettazione progetti**</span><span class="sxs-lookup"><span data-stu-id="0ac9c-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="0ac9c-116">Nella riga di comando quando si usa il compilatore della riga di comando</span><span class="sxs-lookup"><span data-stu-id="0ac9c-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="0ac9c-117">Nel codice</span><span class="sxs-lookup"><span data-stu-id="0ac9c-117">In your code</span></span>  
  
 <span data-ttu-id="0ac9c-118">Costanti di compilazione condizionale hanno un ambito speciale e non è possibile accedervi dal codice standard.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="0ac9c-119">L'ambito di una costante di compilazione condizionale dipende dal modo in cui è impostata.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="0ac9c-120">La tabella seguente elenca l'ambito delle costanti dichiarato tramite ognuno dei tre metodi indicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="0ac9c-121">Modalità di impostazione (costante)</span><span class="sxs-lookup"><span data-stu-id="0ac9c-121">How constant is set</span></span>|<span data-ttu-id="0ac9c-122">Ambito della costante</span><span class="sxs-lookup"><span data-stu-id="0ac9c-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="0ac9c-123">**Creazione progetti**</span><span class="sxs-lookup"><span data-stu-id="0ac9c-123">**Project Designer**</span></span>|<span data-ttu-id="0ac9c-124">Public per tutti i file di progetto</span><span class="sxs-lookup"><span data-stu-id="0ac9c-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="0ac9c-125">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="0ac9c-125">Command line</span></span>|<span data-ttu-id="0ac9c-126">Public per tutti i file passati al compilatore della riga di comando</span><span class="sxs-lookup"><span data-stu-id="0ac9c-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="0ac9c-127">`#Const` istruzione nel codice</span><span class="sxs-lookup"><span data-stu-id="0ac9c-127">`#Const` statement in code</span></span>|<span data-ttu-id="0ac9c-128">Private del file in cui è dichiarata</span><span class="sxs-lookup"><span data-stu-id="0ac9c-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="0ac9c-129">Per impostare le costanti in Creazione progetti</span><span class="sxs-lookup"><span data-stu-id="0ac9c-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="0ac9c-130">-Prima di creare il file eseguibile, impostare le costanti **creazione progetti** seguendo i passaggi forniti nella [gestione dei progetti e le proprietà della soluzione](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="0ac9c-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="0ac9c-131">Per impostare le costanti nella riga di comando</span><span class="sxs-lookup"><span data-stu-id="0ac9c-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="0ac9c-132">-Usare il **/d** switch per inserire le costanti di compilazione condizionale, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0ac9c-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="0ac9c-133">Spazio non è necessario tra i **/d** switch e la prima costante.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="0ac9c-134">Per altre informazioni, vedere [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="0ac9c-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="0ac9c-135">Le dichiarazioni della riga di comando esegue l'override di dichiarazioni immesso nel **Progettazione progetti**, ma non cancellarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="0ac9c-136">Impostare gli argomenti **Progettazione progetti** rimangono valide per le compilazioni successive.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="0ac9c-137">Quando si scrivono le costanti nel codice stesso, non sono presenti regole strict per quanto riguarda la loro posizione, perché il relativo ambito sia l'intero modulo in cui sono dichiarate.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="0ac9c-138">Per impostare le costanti nel codice</span><span class="sxs-lookup"><span data-stu-id="0ac9c-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="0ac9c-139">-Collocare le costanti nel blocco di dichiarazione del modulo in cui vengono usati.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="0ac9c-140">Ciò consente di mantenere il codice organizzato e facili da leggere.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="0ac9c-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0ac9c-141">Related Topics</span></span>  
  
|<span data-ttu-id="0ac9c-142">Titolo</span><span class="sxs-lookup"><span data-stu-id="0ac9c-142">Title</span></span>|<span data-ttu-id="0ac9c-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ac9c-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="0ac9c-144">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="0ac9c-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="0ac9c-145">Vengono forniti suggerimenti per rendere il codice facile da leggere e gestire.</span><span class="sxs-lookup"><span data-stu-id="0ac9c-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="0ac9c-146">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="0ac9c-146">Reference</span></span>  
 [<span data-ttu-id="0ac9c-147">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="0ac9c-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="0ac9c-148">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="0ac9c-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="0ac9c-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ac9c-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
