---
title: Riferimenti a elementi dichiarati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 0fca02ab2dcb507c1129f18f31a25c7809fc9710
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296706"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="dfacd-102">Riferimenti a elementi dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfacd-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="dfacd-103">Quando il codice fa riferimento a un elemento dichiarato, il compilatore Visual Basic corrisponde al nome nel riferimento alla dichiarazione appropriata di tale nome.</span><span class="sxs-lookup"><span data-stu-id="dfacd-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="dfacd-104">Se più di un elemento viene dichiarato con lo stesso nome, è possibile controllare quale di questi elementi è a cui fa riferimento *qualificazione* il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="dfacd-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="dfacd-105">Il compilatore tenta di ottenere un riferimento a una dichiarazione del nome e il *ambito più ristretto*.</span><span class="sxs-lookup"><span data-stu-id="dfacd-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="dfacd-106">Ciò significa inizia con il creazione del riferimento del codice e procede verso l'esterno attraverso livelli successivi di contenente gli elementi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="dfacd-107">Nell'esempio seguente mostra i riferimenti a due variabili con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="dfacd-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="dfacd-108">Nell'esempio vengono dichiarate due variabili, ogni colonna nome `totalCount`, a diversi livelli di ambito nel modulo `container`.</span><span class="sxs-lookup"><span data-stu-id="dfacd-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="dfacd-109">Quando la procedura `showCount` consente di visualizzare `totalCount` senza qualifica, il compilatore Visual Basic si risolve il riferimento alla dichiarazione con ambito più ristretto, vale a dire la dichiarazione locale all'interno `showCount`.</span><span class="sxs-lookup"><span data-stu-id="dfacd-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="dfacd-110">Quando qualifica `totalCount` con il modulo contenente `container`, il compilatore risolve il riferimento alla dichiarazione con ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="dfacd-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="dfacd-111">Un nome di elemento di qualificazione</span><span class="sxs-lookup"><span data-stu-id="dfacd-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="dfacd-112">Se si desidera eseguire l'override di questo processo di ricerca e specificare un nome dichiarato in un ambito più ampio, è necessario *qualificare* al nome dell'elemento contenitore dell'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="dfacd-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="dfacd-113">In alcuni casi, potrebbe anche dover qualificare l'elemento che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="dfacd-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="dfacd-114">Qualificare un nome significa che lo precede nell'istruzione del codice sorgente con le informazioni che identificano in cui è definito l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="dfacd-115">Queste informazioni viene chiamate un *stringa di qualificazione*.</span><span class="sxs-lookup"><span data-stu-id="dfacd-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="dfacd-116">Può includere uno o più spazi dei nomi e un modulo, classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="dfacd-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="dfacd-117">La stringa di qualificazione necessario specificare in modo non ambiguo il modulo, classe o struttura che contiene l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="dfacd-118">Il contenitore a loro volta potrebbe trovarsi in un altro elemento che lo contiene, in genere uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="dfacd-119">Potrebbe essere necessario includere gli elementi che lo contiene diversi nella stringa di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="dfacd-120">Per accedere a un elemento dichiarato dal relativo nome completo della classe</span><span class="sxs-lookup"><span data-stu-id="dfacd-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="dfacd-121">Determinare il percorso in cui è stato definito l'elemento.</span><span class="sxs-lookup"><span data-stu-id="dfacd-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="dfacd-122">Potrebbe trattarsi di uno spazio dei nomi o anche una gerarchia di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="dfacd-123">Nello spazio dei nomi di livello più basso, l'elemento deve essere incluso in un modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="dfacd-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2. <span data-ttu-id="dfacd-124">Determinare il percorso di qualificazione in base alla posizione dell'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="dfacd-125">Iniziare con lo spazio dei nomi di livello più alto, procedere con lo spazio dei nomi di livello più basso e terminare con il modulo, classe o struttura che contiene l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="dfacd-126">Ogni elemento nel percorso deve contenere l'elemento che lo segue.</span><span class="sxs-lookup"><span data-stu-id="dfacd-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="dfacd-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="dfacd-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="dfacd-128">Preparare la stringa di qualificazione per l'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="dfacd-129">Inserire un punto (`.`) dopo ogni elemento nel percorso.</span><span class="sxs-lookup"><span data-stu-id="dfacd-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="dfacd-130">L'applicazione deve avere accesso a ogni elemento nella stringa di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="dfacd-131">Scrivere l'espressione o istruzione di assegnazione che fa riferimento all'elemento di destinazione in modo normale.</span><span class="sxs-lookup"><span data-stu-id="dfacd-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="dfacd-132">Anteporre al nome di elemento di destinazione con la stringa di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="dfacd-133">Il nome deve seguire immediatamente il punto (`.`) che segue il modulo, classe o struttura che contiene l'elemento.</span><span class="sxs-lookup"><span data-stu-id="dfacd-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="dfacd-134">Il compilatore Usa la stringa di qualificazione per individuare una dichiarazione di non crittografata e non ambigua a cui può trovare il riferimento all'elemento di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="dfacd-135">Potrebbe anche essere necessario qualificare un riferimento al nome, se l'applicazione può accedere a più di un elemento di programmazione che ha lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="dfacd-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="dfacd-136">Ad esempio, il <xref:System.Windows.Forms> e <xref:System.Web.UI.WebControls> spazi dei nomi di entrambi contengono una `Label` classe (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="dfacd-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="dfacd-137">Se l'applicazione Usa entrambi o se definisce il proprio `Label` (classe), è necessario distinguere i diversi `Label` oggetti.</span><span class="sxs-lookup"><span data-stu-id="dfacd-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="dfacd-138">Includere l'alias di importazione o dello spazio dei nomi nella dichiarazione di variabile.</span><span class="sxs-lookup"><span data-stu-id="dfacd-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="dfacd-139">Nell'esempio seguente usa l'alias di importazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="dfacd-140">Membri di altri elementi contenitore</span><span class="sxs-lookup"><span data-stu-id="dfacd-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="dfacd-141">Quando si usa un membro non condiviso di un'altra classe o struttura, è innanzitutto necessario qualificare il nome del membro con una variabile o espressione che punti a un'istanza della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="dfacd-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="dfacd-142">Nell'esempio riportato di seguito `demoClass` è un'istanza di una classe denominata `class1`.</span><span class="sxs-lookup"><span data-stu-id="dfacd-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="dfacd-143">È possibile usare il nome della classe per qualificare un membro che non è [condiviso](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="dfacd-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="dfacd-144">È innanzitutto necessario creare un'istanza in una variabile oggetto (in questo caso `demoClass`) e quindi farvi riferimento tramite il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="dfacd-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="dfacd-145">Se una classe o struttura ha un `Shared` membro, è possibile qualificare il membro con il nome di classe o struttura o con una variabile o espressione che punti a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="dfacd-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="dfacd-146">Un modulo non dispone di tutte le istanze separate e tutti i relativi membri sono `Shared` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dfacd-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="dfacd-147">Pertanto, qualificare un membro del modulo con il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="dfacd-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="dfacd-148">Nell'esempio seguente mostra riferimenti qualificati a procedure di membri di modulo.</span><span class="sxs-lookup"><span data-stu-id="dfacd-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="dfacd-149">Nell'esempio viene dichiarata due `Sub` procedure, entrambi denominati `perform`, in moduli diversi in un progetto.</span><span class="sxs-lookup"><span data-stu-id="dfacd-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="dfacd-150">Ciascuna di esse può essere specificato senza qualifica all'interno di un proprio modulo ma deve essere completo se viene fatto riferimento da qualsiasi altra posizione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="dfacd-151">Perché fa riferimento l'elemento finale nel `module3` non soddisfa i requisiti `perform`, il compilatore non è possibile risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="dfacd-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="dfacd-152">Riferimenti a progetti</span><span class="sxs-lookup"><span data-stu-id="dfacd-152">References to Projects</span></span>  
 <span data-ttu-id="dfacd-153">Per usare [pubblici](../../../../visual-basic/language-reference/modifiers/public.md) gli elementi definiti in un altro progetto, è innanzitutto necessario impostare un *riferimento* per quel progetto assembly o libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="dfacd-154">Per impostare un riferimento, fare clic su **Aggiungi riferimento** nel **progetto** menu o utilizzare il [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opzione del compilatore da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dfacd-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="dfacd-155">Ad esempio, è possibile usare il modello a oggetti XML del [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfacd-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="dfacd-156">Se si imposta un riferimento la <xref:System.Xml> dello spazio dei nomi, è possibile dichiarare e usare una delle relative classi, ad esempio <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="dfacd-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="dfacd-157">L'esempio seguente usa <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="dfacd-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="dfacd-158">Importazione di elementi contenitore</span><span class="sxs-lookup"><span data-stu-id="dfacd-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="dfacd-159">È possibile usare la [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) al *importare* gli spazi dei nomi che contengono i moduli o classi che si desiderano utilizzare.</span><span class="sxs-lookup"><span data-stu-id="dfacd-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="dfacd-160">In questo modo è possibile fare riferimento agli elementi definiti in uno spazio dei nomi importato senza qualificare completamente i relativi nomi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="dfacd-161">Nell'esempio seguente riscritto l'esempio precedente per importare il <xref:System.Xml> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="dfacd-162">Inoltre, il `Imports` istruzione è possibile definire un *alias di importazione* per ogni spazio dei nomi importato.</span><span class="sxs-lookup"><span data-stu-id="dfacd-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="dfacd-163">Ciò può rendere il codice sorgente più breve e facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="dfacd-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="dfacd-164">Nell'esempio seguente riscrive l'esempio precedente per usare `xD` come alias per il <xref:System.Xml> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="dfacd-165">Il `Imports` istruzione non rende disponibili elementi di altri progetti all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="dfacd-166">Vale a dire, non viene preso il posto di un riferimento all'impostazione.</span><span class="sxs-lookup"><span data-stu-id="dfacd-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="dfacd-167">L'importazione di uno spazio dei nomi appena rimuove il requisito per qualificare i nomi definiti nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dfacd-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="dfacd-168">È anche possibile usare il `Imports` per importare i moduli, classi, strutture ed enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="dfacd-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="dfacd-169">È quindi possibile usare i membri degli elementi importati senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="dfacd-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="dfacd-170">Tuttavia, è sempre necessario qualificare i membri non condivisi di classi e strutture con una variabile o espressione che restituisce un'istanza della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="dfacd-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="dfacd-171">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="dfacd-171">Naming Guidelines</span></span>  
 <span data-ttu-id="dfacd-172">Quando si definiscono due o più elementi di programmazione che hanno lo stesso nome, una *ambiguità dei nomi* può verificarsi quando il compilatore prova a risolvere un riferimento a tale nome.</span><span class="sxs-lookup"><span data-stu-id="dfacd-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="dfacd-173">Se più di una definizione nell'ambito, o se non è una definizione nell'ambito, il riferimento è non risolvibile.</span><span class="sxs-lookup"><span data-stu-id="dfacd-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="dfacd-174">Per un esempio, vedere "Esempio di riferimento qualificato" in questa pagina della Guida.</span><span class="sxs-lookup"><span data-stu-id="dfacd-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="dfacd-175">È possibile evitare ambiguità dei nomi mediante l'assegnazione di tutti gli elementi di nomi univoci.</span><span class="sxs-lookup"><span data-stu-id="dfacd-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="dfacd-176">Quindi è possibile creare riferimento a tutti gli elementi senza dover qualificare il nome con un spazio dei nomi, modulo o classe.</span><span class="sxs-lookup"><span data-stu-id="dfacd-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="dfacd-177">È anche possibile ridurre le probabilità di errore che fa riferimento a un elemento non corretto.</span><span class="sxs-lookup"><span data-stu-id="dfacd-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="dfacd-178">Shadowing</span><span class="sxs-lookup"><span data-stu-id="dfacd-178">Shadowing</span></span>  
 <span data-ttu-id="dfacd-179">Quando due elementi di programmazione condividono lo stesso nome, è possibile nascondere uno di essi, oppure *shadow*, un altro.</span><span class="sxs-lookup"><span data-stu-id="dfacd-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="dfacd-180">Un elemento nascosto non è disponibile per riferimento; al contrario, quando il codice usi il nome dell'elemento nascosto, il compilatore Visual Basic si risolve nell'elemento di shadowing.</span><span class="sxs-lookup"><span data-stu-id="dfacd-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="dfacd-181">Per una spiegazione più dettagliata con esempi, vedere [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="dfacd-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfacd-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfacd-182">See also</span></span>

- [<span data-ttu-id="dfacd-183">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="dfacd-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="dfacd-184">Caratteristiche di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="dfacd-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="dfacd-185">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="dfacd-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="dfacd-186">Variabili</span><span class="sxs-lookup"><span data-stu-id="dfacd-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="dfacd-187">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="dfacd-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="dfacd-188">Operatore New</span><span class="sxs-lookup"><span data-stu-id="dfacd-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="dfacd-189">Public</span><span class="sxs-lookup"><span data-stu-id="dfacd-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
