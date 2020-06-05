---
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 23bff2eb098982f67ecb1b709e59096d5259a644
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405183"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="868f4-102">Riferimenti a elementi dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="868f4-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="868f4-103">Quando il codice fa riferimento a un elemento dichiarato, il compilatore Visual Basic corrisponde al nome nel riferimento alla dichiarazione appropriata di tale nome.</span><span class="sxs-lookup"><span data-stu-id="868f4-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="868f4-104">Se più di un elemento viene dichiarato con lo stesso nome, è possibile controllare a quali di questi elementi deve essere fatto riferimento *qualificando* il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="868f4-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="868f4-105">Il compilatore tenta di far corrispondere un riferimento a un nome a una dichiarazione di nome con l' *ambito più restrittivo*.</span><span class="sxs-lookup"><span data-stu-id="868f4-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="868f4-106">Ciò significa che inizia con il codice che fa riferimento e funziona in modo esterno attraverso i livelli successivi di elementi che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="868f4-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="868f4-107">Nell'esempio seguente vengono illustrati i riferimenti a due variabili con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="868f4-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="868f4-108">Nell'esempio vengono dichiarate due variabili, ciascuna denominata `totalCount` , a diversi livelli di ambito nel modulo `container` .</span><span class="sxs-lookup"><span data-stu-id="868f4-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="868f4-109">Quando la procedura `showCount` viene visualizzata `totalCount` senza qualificazione, il Visual Basic compilatore risolve il riferimento alla dichiarazione con l'ambito più piccolo, ovvero la dichiarazione locale all'interno di `showCount` .</span><span class="sxs-lookup"><span data-stu-id="868f4-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="868f4-110">Quando si qualifica `totalCount` con il modulo contenitore `container` , il compilatore risolve il riferimento alla dichiarazione con l'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="868f4-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="868f4-111">Qualificazione del nome di un elemento</span><span class="sxs-lookup"><span data-stu-id="868f4-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="868f4-112">Se si desidera eseguire l'override di questo processo di ricerca e specificare un nome dichiarato in un ambito più ampio, è necessario *qualificare* il nome con l'elemento contenitore dell'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="868f4-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="868f4-113">In alcuni casi, potrebbe anche essere necessario qualificare l'elemento contenitore.</span><span class="sxs-lookup"><span data-stu-id="868f4-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="868f4-114">Per qualificare un nome si intende precederlo nell'istruzione source con le informazioni che identificano la posizione in cui è definito l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="868f4-115">Queste informazioni sono definite *stringa di qualificazione*.</span><span class="sxs-lookup"><span data-stu-id="868f4-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="868f4-116">Può includere uno o più spazi dei nomi e un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="868f4-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="868f4-117">La stringa di qualificazione deve specificare in modo univoco il modulo, la classe o la struttura contenente l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="868f4-118">Il contenitore può a sua volta trovarsi in un altro elemento contenitore, in genere uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="868f4-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="868f4-119">Potrebbe essere necessario includere diversi elementi contenenti nella stringa di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="868f4-120">Per accedere a un elemento dichiarato qualificando il nome</span><span class="sxs-lookup"><span data-stu-id="868f4-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="868f4-121">Determinare la posizione in cui è stato definito l'elemento.</span><span class="sxs-lookup"><span data-stu-id="868f4-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="868f4-122">Potrebbe includere uno spazio dei nomi o persino una gerarchia di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="868f4-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="868f4-123">All'interno dello spazio dei nomi di livello più basso, l'elemento deve essere contenuto in un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="868f4-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. <span data-ttu-id="868f4-124">Determinare un percorso di qualificazione in base alla posizione dell'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="868f4-125">Iniziare con lo spazio dei nomi di livello più alto, passare allo spazio dei nomi di livello più basso e terminare con il modulo, la classe o la struttura contenente l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="868f4-126">Ogni elemento nel percorso deve contenere l'elemento che lo segue.</span><span class="sxs-lookup"><span data-stu-id="868f4-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="868f4-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="868f4-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="868f4-128">Preparare la stringa di qualificazione per l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="868f4-129">Inserire un punto ( `.` ) dopo ogni elemento del percorso.</span><span class="sxs-lookup"><span data-stu-id="868f4-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="868f4-130">L'applicazione deve avere accesso a ogni elemento nella stringa di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="868f4-131">Scrivere l'espressione o l'istruzione di assegnazione che fa riferimento all'elemento di destinazione nel modo normale.</span><span class="sxs-lookup"><span data-stu-id="868f4-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="868f4-132">Precede il nome dell'elemento di destinazione con la stringa di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="868f4-133">Il nome deve seguire immediatamente il punto ( `.` ) che segue il modulo, la classe o la struttura che contiene l'elemento.</span><span class="sxs-lookup"><span data-stu-id="868f4-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="868f4-134">Il compilatore usa la stringa di qualificazione per trovare una dichiarazione chiara e non ambigua a cui può corrispondere il riferimento all'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="868f4-135">Potrebbe anche essere necessario qualificare un riferimento al nome se l'applicazione ha accesso a più di un elemento di programmazione con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="868f4-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="868f4-136">Ad esempio, gli <xref:System.Windows.Forms> <xref:System.Web.UI.WebControls> spazi dei nomi e contengono entrambi una `Label` classe ( <xref:System.Windows.Forms.Label?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="868f4-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="868f4-137">Se l'applicazione usa entrambi o se definisce la propria `Label` classe, è necessario distinguere i diversi `Label` oggetti.</span><span class="sxs-lookup"><span data-stu-id="868f4-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="868f4-138">Includere lo spazio dei nomi o l'alias di importazione nella dichiarazione di variabile.</span><span class="sxs-lookup"><span data-stu-id="868f4-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="868f4-139">Nell'esempio seguente viene usato l'alias di importazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="868f4-140">Membri di altri elementi contenenti</span><span class="sxs-lookup"><span data-stu-id="868f4-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="868f4-141">Quando si utilizza un membro non condiviso di un'altra classe o struttura, è necessario innanzitutto qualificare il nome del membro con una variabile o un'espressione che punta a un'istanza della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="868f4-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="868f4-142">Nell'esempio seguente `demoClass` è un'istanza di una classe denominata `class1` .</span><span class="sxs-lookup"><span data-stu-id="868f4-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="868f4-143">Non è possibile usare il nome della classe per qualificare un membro non [condiviso](../../../language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="868f4-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="868f4-144">È innanzitutto necessario creare un'istanza in una variabile oggetto (in questo caso `demoClass` ) e quindi farvi riferimento tramite il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="868f4-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="868f4-145">Se una classe o una struttura dispone di un `Shared` membro, è possibile qualificare il membro con il nome della classe o della struttura oppure con una variabile o un'espressione che punta a un'istanza di.</span><span class="sxs-lookup"><span data-stu-id="868f4-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="868f4-146">Un modulo non dispone di istanze separate e tutti i relativi membri sono `Shared` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="868f4-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="868f4-147">Pertanto, è necessario qualificare un membro del modulo con il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="868f4-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="868f4-148">Nell'esempio seguente vengono illustrati i riferimenti completi alle procedure dei membri del modulo.</span><span class="sxs-lookup"><span data-stu-id="868f4-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="868f4-149">Nell'esempio vengono dichiarate due `Sub` procedure, entrambe denominate `perform` , in moduli diversi in un progetto.</span><span class="sxs-lookup"><span data-stu-id="868f4-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="868f4-150">Ognuno di essi può essere specificato senza qualificazione all'interno del proprio modulo, ma deve essere qualificato se vi si fa riferimento da qualsiasi altra posizione.</span><span class="sxs-lookup"><span data-stu-id="868f4-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="868f4-151">Poiché il riferimento finale in non `module3` è qualificata `perform` , il compilatore non è in grado di risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="868f4-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="868f4-152">Riferimenti ai progetti</span><span class="sxs-lookup"><span data-stu-id="868f4-152">References to Projects</span></span>  
 <span data-ttu-id="868f4-153">Per usare elementi [pubblici](../../../language-reference/modifiers/public.md) definiti in un altro progetto, è necessario innanzitutto impostare un *riferimento* all'assembly o alla libreria dei tipi del progetto.</span><span class="sxs-lookup"><span data-stu-id="868f4-153">To use [Public](../../../language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="868f4-154">Per impostare un riferimento, fare clic su **Aggiungi riferimento** nel menu **progetto** oppure utilizzare l'opzione del compilatore della riga [di comando-Reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="868f4-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [-reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="868f4-155">È ad esempio possibile utilizzare il modello a oggetti XML del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="868f4-155">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="868f4-156">Se si imposta un riferimento allo <xref:System.Xml> spazio dei nomi, è possibile dichiarare e utilizzare una delle relative classi, ad esempio <xref:System.Xml.XmlDocument> .</span><span class="sxs-lookup"><span data-stu-id="868f4-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="868f4-157">Nell'esempio seguente viene utilizzato <xref:System.Xml.XmlDocument>:</span><span class="sxs-lookup"><span data-stu-id="868f4-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="868f4-158">Importazione di elementi contenenti</span><span class="sxs-lookup"><span data-stu-id="868f4-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="868f4-159">È possibile utilizzare l' [istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) per *importare* gli spazi dei nomi che contengono i moduli o le classi che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="868f4-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="868f4-160">In questo modo è possibile fare riferimento agli elementi definiti in uno spazio dei nomi importato senza qualificare il nome completo.</span><span class="sxs-lookup"><span data-stu-id="868f4-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="868f4-161">Nell'esempio seguente viene riscritto l'esempio precedente per importare lo <xref:System.Xml> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="868f4-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="868f4-162">Inoltre, l' `Imports` istruzione può definire un *alias di importazione* per ogni spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="868f4-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="868f4-163">Questo può rendere il codice sorgente più breve e più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="868f4-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="868f4-164">Nell'esempio seguente viene riscritto l'esempio precedente da utilizzare `xD` come alias per lo <xref:System.Xml> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="868f4-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="868f4-165">L' `Imports` istruzione non rende disponibili gli elementi di altri progetti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="868f4-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="868f4-166">Ciò significa che non viene eseguita l'impostazione di un riferimento.</span><span class="sxs-lookup"><span data-stu-id="868f4-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="868f4-167">Se si importa uno spazio dei nomi, viene semplicemente rimosso il requisito per qualificare i nomi definiti nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="868f4-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="868f4-168">È anche possibile usare l' `Imports` istruzione per importare moduli, classi, strutture ed enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="868f4-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="868f4-169">È quindi possibile usare i membri di tali elementi importati senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="868f4-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="868f4-170">Tuttavia, è sempre necessario qualificare i membri non condivisi di classi e strutture con una variabile o un'espressione che restituisce un'istanza della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="868f4-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="868f4-171">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="868f4-171">Naming Guidelines</span></span>  
 <span data-ttu-id="868f4-172">Quando si definiscono due o più elementi di programmazione con lo stesso nome, un' *ambiguità dei nomi* può verificarsi quando il compilatore tenta di risolvere un riferimento a tale nome.</span><span class="sxs-lookup"><span data-stu-id="868f4-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="868f4-173">Se più di una definizione è nell'ambito o se nessuna definizione è nell'ambito, il riferimento è irrisolvibile.</span><span class="sxs-lookup"><span data-stu-id="868f4-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="868f4-174">Per un esempio, vedere "esempio di riferimento completo" in questa pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="868f4-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="868f4-175">È possibile evitare l'ambiguità dei nomi assegnando a tutti gli elementi nomi univoci.</span><span class="sxs-lookup"><span data-stu-id="868f4-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="868f4-176">È quindi possibile fare riferimento a qualsiasi elemento senza che sia necessario qualificarne il nome con uno spazio dei nomi, un modulo o una classe.</span><span class="sxs-lookup"><span data-stu-id="868f4-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="868f4-177">Si riducono inoltre le probabilità di riferimento accidentale all'elemento errato.</span><span class="sxs-lookup"><span data-stu-id="868f4-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="868f4-178">Shadowing</span><span class="sxs-lookup"><span data-stu-id="868f4-178">Shadowing</span></span>  
 <span data-ttu-id="868f4-179">Quando due elementi di programmazione condividono lo stesso nome, uno di essi può nascondere, o *ombreggiare*, l'altro.</span><span class="sxs-lookup"><span data-stu-id="868f4-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="868f4-180">Un elemento ombreggiato non è disponibile per riferimento. al contrario, quando il codice usa il nome dell'elemento ombreggiato, il compilatore Visual Basic lo risolve nell'elemento shadowing.</span><span class="sxs-lookup"><span data-stu-id="868f4-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="868f4-181">Per una spiegazione più dettagliata con esempi, vedere [shadowing in Visual Basic](shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="868f4-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868f4-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="868f4-182">See also</span></span>

- [<span data-ttu-id="868f4-183">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="868f4-183">Declared Element Names</span></span>](declared-element-names.md)
- [<span data-ttu-id="868f4-184">Caratteristiche di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="868f4-184">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="868f4-185">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="868f4-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="868f4-186">Variabili</span><span class="sxs-lookup"><span data-stu-id="868f4-186">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="868f4-187">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="868f4-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="868f4-188">Operatore New</span><span class="sxs-lookup"><span data-stu-id="868f4-188">New Operator</span></span>](../../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="868f4-189">Pubblica</span><span class="sxs-lookup"><span data-stu-id="868f4-189">Public</span></span>](../../../language-reference/modifiers/public.md)
