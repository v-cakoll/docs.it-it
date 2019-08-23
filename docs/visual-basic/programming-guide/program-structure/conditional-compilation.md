---
title: Compilazione condizionale in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 1bee64568ff92468e29226a395f7e5335387e256
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945578"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="331b6-102">Compilazione condizionale in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="331b6-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="331b6-103">Nella *compilazione condizionale*, determinati blocchi di codice in un programma vengono compilati in modo selettivo mentre altri vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="331b6-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="331b6-104">È ad esempio possibile scrivere istruzioni di debug che confrontano la velocità di approcci diversi alla stessa attività di programmazione oppure è possibile localizzare un'applicazione per più linguaggi.</span><span class="sxs-lookup"><span data-stu-id="331b6-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="331b6-105">Le istruzioni di compilazione condizionale sono progettate per essere eseguite in fase di compilazione, non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="331b6-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="331b6-106">È possibile indicare blocchi di codice da compilare in modo condizionale con `#If...Then...#Else` la direttiva.</span><span class="sxs-lookup"><span data-stu-id="331b6-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="331b6-107">Ad esempio, per creare versioni in francese e in lingua tedesca della stessa applicazione dallo stesso codice sorgente, è possibile incorporare segmenti di codice specifici della piattaforma `#If...Then` nelle istruzioni usando le `FrenchVersion` costanti predefinite e `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="331b6-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="331b6-108">Nell'esempio seguente viene illustrato come:</span><span class="sxs-lookup"><span data-stu-id="331b6-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="331b6-109">Se si imposta il valore della `FrenchVersion` costante di compilazione condizionale su `True` in fase di compilazione, viene compilato il codice condizionale per la versione francese.</span><span class="sxs-lookup"><span data-stu-id="331b6-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="331b6-110">Se si imposta il valore della `GermanVersion` costante su `True`, il compilatore utilizzerà la versione tedesca.</span><span class="sxs-lookup"><span data-stu-id="331b6-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="331b6-111">Se nessuno dei due è `True`impostato su, viene eseguito il `Else` codice nell'ultimo blocco.</span><span class="sxs-lookup"><span data-stu-id="331b6-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="331b6-112">Il completamento automatico non funzionerà quando si modifica il codice e si usano le direttive di compilazione condizionale se il codice non fa parte del ramo corrente.</span><span class="sxs-lookup"><span data-stu-id="331b6-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="331b6-113">Dichiarazione di costanti di compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="331b6-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="331b6-114">È possibile impostare le costanti di compilazione condizionale in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="331b6-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="331b6-115">In **Progettazione progetti**</span><span class="sxs-lookup"><span data-stu-id="331b6-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="331b6-116">Dalla riga di comando quando si usa il compilatore da riga di comando</span><span class="sxs-lookup"><span data-stu-id="331b6-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="331b6-117">Nel codice</span><span class="sxs-lookup"><span data-stu-id="331b6-117">In your code</span></span>  
  
 <span data-ttu-id="331b6-118">Le costanti di compilazione condizionale hanno un ambito speciale e non è possibile accedervi dal codice standard.</span><span class="sxs-lookup"><span data-stu-id="331b6-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="331b6-119">L'ambito di una costante di compilazione condizionale dipende dal modo in cui è impostato.</span><span class="sxs-lookup"><span data-stu-id="331b6-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="331b6-120">La tabella seguente elenca l'ambito delle costanti dichiarate usando ognuno dei tre modi descritti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="331b6-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="331b6-121">Impostazione della costante</span><span class="sxs-lookup"><span data-stu-id="331b6-121">How constant is set</span></span>|<span data-ttu-id="331b6-122">Ambito della costante</span><span class="sxs-lookup"><span data-stu-id="331b6-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="331b6-123">**Progettazione progetti**</span><span class="sxs-lookup"><span data-stu-id="331b6-123">**Project Designer**</span></span>|<span data-ttu-id="331b6-124">Pubblico in tutti i file del progetto</span><span class="sxs-lookup"><span data-stu-id="331b6-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="331b6-125">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="331b6-125">Command line</span></span>|<span data-ttu-id="331b6-126">Pubblico per tutti i file passati al compilatore da riga di comando</span><span class="sxs-lookup"><span data-stu-id="331b6-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="331b6-127">`#Const`istruzione nel codice</span><span class="sxs-lookup"><span data-stu-id="331b6-127">`#Const` statement in code</span></span>|<span data-ttu-id="331b6-128">Privato per il file in cui è dichiarato</span><span class="sxs-lookup"><span data-stu-id="331b6-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="331b6-129">Per impostare costanti in Progettazione progetti</span><span class="sxs-lookup"><span data-stu-id="331b6-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="331b6-130">-Prima di creare il file eseguibile, impostare costanti in **Progettazione progetti** attenendosi alla procedura descritta in [gestione delle proprietà del progetto e della soluzione](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="331b6-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="331b6-131">Per impostare costanti dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="331b6-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="331b6-132">-Usare l'opzione **/d** per immettere le costanti di compilazione condizionale, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="331b6-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="331b6-133">Non è necessario alcuno spazio tra l'opzione **/d** e la prima costante.</span><span class="sxs-lookup"><span data-stu-id="331b6-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="331b6-134">Per ulteriori informazioni, vedere [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="331b6-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="331b6-135">Le dichiarazioni della riga di comando eseguono l'override delle dichiarazioni immesse in **Progettazione progetti**, ma non le cancellano.</span><span class="sxs-lookup"><span data-stu-id="331b6-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="331b6-136">Gli argomenti impostati in **Progettazione progetti** rimangono attivi per le compilazioni successive.</span><span class="sxs-lookup"><span data-stu-id="331b6-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="331b6-137">Quando si scrivono costanti nel codice, non sono presenti regole rigide per la loro posizione, poiché il relativo ambito è l'intero modulo in cui sono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="331b6-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="331b6-138">Per impostare costanti nel codice</span><span class="sxs-lookup"><span data-stu-id="331b6-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="331b6-139">: Inserire le costanti nel blocco di dichiarazione del modulo in cui vengono usate.</span><span class="sxs-lookup"><span data-stu-id="331b6-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="331b6-140">Ciò consente di organizzare e semplificare la lettura del codice.</span><span class="sxs-lookup"><span data-stu-id="331b6-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="331b6-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="331b6-141">Related Topics</span></span>  
  
|<span data-ttu-id="331b6-142">Titolo</span><span class="sxs-lookup"><span data-stu-id="331b6-142">Title</span></span>|<span data-ttu-id="331b6-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="331b6-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="331b6-144">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="331b6-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="331b6-145">Fornisce suggerimenti per semplificare la lettura e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="331b6-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="331b6-146">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="331b6-146">Reference</span></span>  
 [<span data-ttu-id="331b6-147">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="331b6-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="331b6-148">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="331b6-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="331b6-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="331b6-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
