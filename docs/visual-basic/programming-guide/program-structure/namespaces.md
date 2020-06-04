---
title: Spazi dei nomi
ms.date: 07/20/2015
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
ms.openlocfilehash: 087c6f02e1fca9cf2664ca76581c08a9b1a5e447
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398357"
---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="da958-102">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da958-102">Namespaces in Visual Basic</span></span>
<span data-ttu-id="da958-103">Gli spazi dei nomi organizzano gli oggetti definiti in un assembly.</span><span class="sxs-lookup"><span data-stu-id="da958-103">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="da958-104">Gli assembly possono contenere più spazi dei nomi, che a loro volta possono contenere altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-104">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="da958-105">Gli spazi dei nomi consentono di evitare problemi di ambiguità e di semplificare i riferimenti quando si usano gruppi di oggetti di grandi dimensioni, ad esempio librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="da958-105">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="da958-106">Ad esempio, il .NET Framework definisce la <xref:System.Windows.Forms.ListBox> classe nello <xref:System.Windows.Forms?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-106">For example, the .NET Framework defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="da958-107">Il frammento di codice seguente illustra come dichiarare una variabile usando il nome completo per questa classe:</span><span class="sxs-lookup"><span data-stu-id="da958-107">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 [!code-vb[VbVbalrApplication#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#6)]  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="da958-108">Evitare conflitti di nomi</span><span class="sxs-lookup"><span data-stu-id="da958-108">Avoiding Name Collisions</span></span>  
 <span data-ttu-id="da958-109">.NET Framework gli spazi dei nomi risolvono un problema talvolta denominato *inquinamento dello spazio dei nomi*, in cui lo sviluppatore di una libreria di classi è ostacolato dall'uso di nomi simili in un'altra libreria.</span><span class="sxs-lookup"><span data-stu-id="da958-109">.NET Framework namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="da958-110">Questi conflitti con i componenti esistenti sono talvolta denominati *conflitti di nomi*.</span><span class="sxs-lookup"><span data-stu-id="da958-110">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="da958-111">Se, ad esempio, si crea una nuova classe denominata `ListBox`, è possibile usarla all'interno del progetto senza qualificazione.</span><span class="sxs-lookup"><span data-stu-id="da958-111">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="da958-112">Tuttavia, se si vuole usare la classe .NET Framework <xref:System.Windows.Forms.ListBox> nello stesso progetto, è necessario usare un riferimento completo per rendere univoco il riferimento.</span><span class="sxs-lookup"><span data-stu-id="da958-112">However, if you want to use the .NET Framework <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="da958-113">Se il riferimento non è univoco, Visual Basic genera un errore che informa che il nome è ambiguo.</span><span class="sxs-lookup"><span data-stu-id="da958-113">If the reference is not unique, Visual Basic produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="da958-114">L'esempio di codice seguente illustra come dichiarare questi oggetti:</span><span class="sxs-lookup"><span data-stu-id="da958-114">The following code example demonstrates how to declare these objects:</span></span>  
  
 [!code-vb[VbVbalrApplication#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#7)]  
  
 <span data-ttu-id="da958-115">Nella figura seguente sono illustrate due gerarchie dello spazio dei nomi, entrambe contenenti un oggetto denominato `ListBox` :</span><span class="sxs-lookup"><span data-stu-id="da958-115">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`:</span></span>  
  
 ![Screenshot che mostra due gerarchie dello spazio dei nomi.](./media/namespaces/visual-basic-namespace-hierarchy.gif)  
  
 <span data-ttu-id="da958-117">Per impostazione predefinita, ogni file eseguibile creato con Visual Basic contiene uno spazio dei nomi con lo stesso nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-117">By default, every executable file you create with Visual Basic contains a namespace with the same name as your project.</span></span> <span data-ttu-id="da958-118">Se, ad esempio, si definisce un oggetto all'interno di un progetto denominato `ListBoxProject`, il file eseguibile ListBoxProject.exe conterrà uno spazio dei nomi chiamato `ListBoxProject`.</span><span class="sxs-lookup"><span data-stu-id="da958-118">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="da958-119">Più assembly possono usare lo stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-119">Multiple assemblies can use the same namespace.</span></span> <span data-ttu-id="da958-120">Visual Basic li considera come un singolo set di nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-120">Visual Basic treats them as a single set of names.</span></span> <span data-ttu-id="da958-121">È ad esempio possibile definire classi per uno spazio dei nomi chiamato `SomeNameSpace` in un assembly denominato `Assemb1`e altre classi per lo stesso spazio dei nomi da un assembly denominato `Assemb2`.</span><span class="sxs-lookup"><span data-stu-id="da958-121">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="da958-122">nomi completi</span><span class="sxs-lookup"><span data-stu-id="da958-122">Fully Qualified Names</span></span>  
 <span data-ttu-id="da958-123">I nomi completi sono riferimenti a oggetti preceduti dal nome dello spazio dei nomi in cui è definito l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="da958-123">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="da958-124">È possibile usare gli oggetti definiti in altri progetti se si crea un riferimento alla classe (scegliendo **Aggiungi riferimento** dal menu **Progetto** ) e quindi usare il nome completo per l'oggetto nel codice.</span><span class="sxs-lookup"><span data-stu-id="da958-124">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="da958-125">Il frammento di codice seguente mostra come usare il nome completo per un oggetto dallo spazio dei nomi di un altro progetto:</span><span class="sxs-lookup"><span data-stu-id="da958-125">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 [!code-vb[VbVbalrApplication#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#8)]  
  
 <span data-ttu-id="da958-126">I nomi completi impediscono i conflitti di denominazione perché consentono al compilatore di determinare quale oggetto viene usato.</span><span class="sxs-lookup"><span data-stu-id="da958-126">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="da958-127">I nomi stessi, tuttavia, possono diventare lunghi e complessi.</span><span class="sxs-lookup"><span data-stu-id="da958-127">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="da958-128">Per evitare questo problema, è possibile usare l'istruzione `Imports` per definire un *alias*, ossia un nome abbreviato utilizzabile al posto di un nome completo.</span><span class="sxs-lookup"><span data-stu-id="da958-128">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="da958-129">Ad esempio, il codice seguente crea alias per due nomi completi e usa questi alias per definire due oggetti.</span><span class="sxs-lookup"><span data-stu-id="da958-129">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 [!code-vb[VbVbalrApplication#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#9)]  
  
 [!code-vb[VbVbalrApplication#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#10)]  
  
 <span data-ttu-id="da958-130">Se si usa l'istruzione `Imports` senza un alias, è possibile usare tutti i nomi dello spazio dei nomi senza qualificazione, a condizione che siano univoci per il progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-130">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="da958-131">Se il progetto contiene istruzioni `Imports` per gli spazi dei nomi che contengono elementi con lo stesso nome, quando si usa il nome è necessario definirlo in modo completo.</span><span class="sxs-lookup"><span data-stu-id="da958-131">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="da958-132">Si supponga, ad esempio, che il progetto contenga le due istruzioni `Imports` seguenti:</span><span class="sxs-lookup"><span data-stu-id="da958-132">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 [!code-vb[VbVbalrApplication#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#11)]  
  
 <span data-ttu-id="da958-133">Se si tenta di utilizzare `Class1` senza la qualifica completa, Visual Basic genera un errore che informa che il nome `Class1` è ambiguo.</span><span class="sxs-lookup"><span data-stu-id="da958-133">If you attempt to use `Class1` without fully qualifying it, Visual Basic produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="da958-134">Istruzioni a livello di spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="da958-134">Namespace Level Statements</span></span>  
 <span data-ttu-id="da958-135">All'interno di uno spazio dei nomi è possibile definire elementi quali moduli, interfacce, classi, delegati, enumerazioni, strutture e altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-135">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="da958-136">Non è invece possibile definire elementi come proprietà, routine, variabili ed eventi a livello di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-136">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="da958-137">Questi elementi devono essere dichiarati all'interno di contenitori quali moduli, strutture o classi.</span><span class="sxs-lookup"><span data-stu-id="da958-137">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="da958-138">Parola chiave Global nei nomi completi</span><span class="sxs-lookup"><span data-stu-id="da958-138">Global Keyword in Fully Qualified Names</span></span>  
 <span data-ttu-id="da958-139">Se è stata definita una gerarchia annidata di spazi dei nomi, è possibile che per il codice interno alla gerarchia venga bloccato l'accesso allo spazio dei nomi <xref:System?displayProperty=nameWithType> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da958-139">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=nameWithType> namespace of the .NET Framework.</span></span> <span data-ttu-id="da958-140">L'esempio seguente illustra una gerarchia in cui lo spazio dei nomi `SpecialSpace.System` blocca l'accesso a <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="da958-140">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=nameWithType>.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="da958-141">Di conseguenza, il compilatore di Visual Basic non è in grado di risolvere il riferimento a <xref:System.Int32?displayProperty=nameWithType>perché `SpecialSpace.System` non definisce `Int32`.</span><span class="sxs-lookup"><span data-stu-id="da958-141">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=nameWithType>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="da958-142">Per iniziare la catena di qualificazione al livello più esterno della libreria di classi di .NET Framework è possibile usare la parola chiave `Global` .</span><span class="sxs-lookup"><span data-stu-id="da958-142">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="da958-143">In questo modo si può specificare lo spazio dei nomi <xref:System?displayProperty=nameWithType> o qualsiasi altro spazio dei nomi nella libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="da958-143">This allows you to specify the <xref:System?displayProperty=nameWithType> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="da958-144">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="da958-144">The following example illustrates this.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="da958-145">Usando `Global` è possibile accedere ad altri spazi dei nomi a livello di radice, ad esempio <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, e a qualsiasi spazio dei nomi associato al progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-145">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="da958-146">Parola chiave Global nelle istruzioni degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="da958-146">Global Keyword in Namespace Statements</span></span>  
 <span data-ttu-id="da958-147">La parola chiave `Global` può essere usata anche in un oggetto [Namespace Statement](../../language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="da958-147">You can also use the `Global` keyword in a [Namespace Statement](../../language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="da958-148">Ciò consente di definire uno spazio dei nomi all'esterno dello spazio dei nomi radice del progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-148">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="da958-149">Tutti gli spazi dei nomi inclusi nel progetto sono basati sullo spazio dei nomi radice definito per il progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-149">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="da958-150">Visual Studio assegna il nome del progetto come spazio dei nomi radice predefinito per tutto il codice del progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-150">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="da958-151">Se, ad esempio, il progetto è denominato `ConsoleApplication1`, i relativi elementi di programmazione appartengono allo spazio dei nomi `ConsoleApplication1`.</span><span class="sxs-lookup"><span data-stu-id="da958-151">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="da958-152">Se si dichiara `Namespace Magnetosphere`, i riferimenti a `Magnetosphere` nel progetto accedono a `ConsoleApplication1.Magnetosphere`.</span><span class="sxs-lookup"><span data-stu-id="da958-152">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="da958-153">Negli esempi seguenti viene usata la parola chiave `Global` per dichiarare uno spazio dei nomi all'esterno dello spazio dei nomi radice per il progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-153">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 [!code-vb[VbVbalrApplication#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#22)]  
  
 <span data-ttu-id="da958-154">In una dichiarazione dello spazio dei nomi la parola chiave `Global` non può essere annidata in un altro spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-154">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="da958-155">È possibile usare [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) per visualizzare e modificare lo **spazio dei nomi radice** del progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-155">You can use the [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="da958-156">Per i nuovi progetti, come **spazio dei nomi radice** predefinito viene usato il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="da958-156">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="da958-157">Per impostare `Global` come spazio dei nomi di primo livello, è possibile cancellare la voce **Spazio dei nomi radice** in modo da lasciare vuota la casella.</span><span class="sxs-lookup"><span data-stu-id="da958-157">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="da958-158">La cancellazione della voce **Spazio dei nomi radice** elimina la necessità di usare la parola chiave `Global` nelle dichiarazioni degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da958-158">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="da958-159">Se un'istruzione `Namespace` dichiara un nome che è anche uno spazio dei nomi in .NET Framework e la parola chiave `Global` non viene usata in un nome completo, lo spazio dei nomi di .NET Framework non sarà più disponibile.</span><span class="sxs-lookup"><span data-stu-id="da958-159">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="da958-160">Per abilitare l'accesso allo spazio dei nomi di .NET Framework senza usare la parola chiave `Global` , è possibile includere `Global` nell'istruzione `Namespace` .</span><span class="sxs-lookup"><span data-stu-id="da958-160">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="da958-161">L'esempio seguente mostra la dichiarazione dello spazio dei nomi `Global` con la parola chiave `System.Text` .</span><span class="sxs-lookup"><span data-stu-id="da958-161">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="da958-162">Se `Global` non è presente nella dichiarazione dello spazio dei nomi, <xref:System.Text.StringBuilder> non è accessibile, a meno che non si specifichi `Global.System.Text.StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="da958-162">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="da958-163">Per un progetto denominato `ConsoleApplication1`, i riferimenti a `System.Text` accedono a `ConsoleApplication1.System.Text` se non viene usata la parola chiave `Global` .</span><span class="sxs-lookup"><span data-stu-id="da958-163">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 [!code-vb[VbVbalrApplication#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="da958-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da958-164">See also</span></span>

- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms?displayProperty=nameWithType>
- [<span data-ttu-id="da958-165">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="da958-165">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="da958-166">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="da958-166">References and the Imports Statement</span></span>](references-and-the-imports-statement.md)
- [<span data-ttu-id="da958-167">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="da958-167">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="da958-168">Scrittura di codice nelle soluzioni Office</span><span class="sxs-lookup"><span data-stu-id="da958-168">Writing Code in Office Solutions</span></span>](/visualstudio/vsto/writing-code-in-office-solutions)
