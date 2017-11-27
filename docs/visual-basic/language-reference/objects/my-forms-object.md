---
title: Oggetto My.Forms
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5aa7af1f07a29660335d968c1ecc17be5f8beec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="myforms-object"></a><span data-ttu-id="f47b7-102">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="f47b7-102">My.Forms Object</span></span>
<span data-ttu-id="f47b7-103">Fornisce proprietà per l'accesso a un'istanza di ogni Windows form dichiarato nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f47b7-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f47b7-104">Note</span><span class="sxs-lookup"><span data-stu-id="f47b7-104">Remarks</span></span>  
 <span data-ttu-id="f47b7-105">Il `My.Forms` oggetto fornisce un'istanza di ciascun form nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f47b7-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="f47b7-106">Il nome della proprietà è identico al nome del modulo a cui accede la proprietà.</span><span class="sxs-lookup"><span data-stu-id="f47b7-106">The name of the property is the same as the name of the form that the property accesses.</span></span> <span data-ttu-id="f47b7-107">Per informazioni sull'aggiunta di form a un progetto, vedere [procedura: aggiungere Windows Form a un progetto](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="f47b7-107">For information about adding forms to a project, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="f47b7-108">È possibile accedere ai form forniti il `My.Forms` oggetto utilizzando il nome del modulo, senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="f47b7-108">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="f47b7-109">Poiché il nome della proprietà è lo stesso nome di tipo del form, questo consente di accedere a un modulo come se disponesse di un'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="f47b7-109">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="f47b7-110">Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="f47b7-110">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="f47b7-111">Il `My.Forms` oggetto espone solo il form associato al progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f47b7-111">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="f47b7-112">Non fornisce l'accesso ai moduli dichiarati nelle DLL di cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="f47b7-112">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="f47b7-113">Per accedere a un modulo che fornisce una DLL, è necessario utilizzare il nome completo del modulo, scritto come *NomeDLL*. *Nomemodulo*.</span><span class="sxs-lookup"><span data-stu-id="f47b7-113">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="f47b7-114">È possibile utilizzare il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> proprietà da ottenere una raccolta di tutti i form aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f47b7-114">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="f47b7-115">L'oggetto e le relative proprietà sono disponibili solo per le applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="f47b7-115">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f47b7-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f47b7-116">Properties</span></span>  
 <span data-ttu-id="f47b7-117">Ogni proprietà del `My.Forms` oggetto consente di accedere a un'istanza di un form nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f47b7-117">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="f47b7-118">Il nome della proprietà è identico al nome del modulo che accede a proprietà e il tipo della proprietà è identico al tipo del form.</span><span class="sxs-lookup"><span data-stu-id="f47b7-118">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f47b7-119">Se si verifica un conflitto di nome, il nome della proprietà per accedere a un modulo è *RootNamespace*_*Namespace*\_*nomemodulo*.</span><span class="sxs-lookup"><span data-stu-id="f47b7-119">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="f47b7-120">Ad esempio, considerare due form denominati `Form1.`se uno di questi moduli è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, è possibile accedere al form tramite `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="f47b7-120">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="f47b7-121">Il `My.Forms` oggetto consente di accedere all'istanza del form principale dell'applicazione che è stato creato all'avvio.</span><span class="sxs-lookup"><span data-stu-id="f47b7-121">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="f47b7-122">Per tutti gli altri moduli di `My.Forms` oggetto crea una nuova istanza del modulo quando l'accesso e l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f47b7-122">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="f47b7-123">I tentativi successivi di accedere a questa proprietà restituiscono tale istanza del form.</span><span class="sxs-lookup"><span data-stu-id="f47b7-123">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="f47b7-124">Per rimuovere un modulo assegnando `Nothing` per la proprietà per tale modulo.</span><span class="sxs-lookup"><span data-stu-id="f47b7-124">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="f47b7-125">Le chiamate di setter di proprietà di <xref:System.Windows.Forms.Form.Close%2A> metodo del form e quindi assegna `Nothing` al valore archiviato.</span><span class="sxs-lookup"><span data-stu-id="f47b7-125">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="f47b7-126">Se si assegna un valore diverso da `Nothing` alla proprietà, il metodo set genera un <xref:System.ArgumentException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="f47b7-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="f47b7-127">È possibile verificare se una proprietà del `My.Forms` oggetto archivia un'istanza del form tramite il `Is` o `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="f47b7-127">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="f47b7-128">È possibile utilizzare tali operatori per verificare se il valore della proprietà è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="f47b7-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f47b7-129">In genere, il `Is` o `IsNot` operatore deve leggere il valore della proprietà per eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="f47b7-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="f47b7-130">Tuttavia, se il valore della proprietà è `Nothing`, la proprietà crea una nuova istanza del form e restituisce tale istanza.</span><span class="sxs-lookup"><span data-stu-id="f47b7-130">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="f47b7-131">Tuttavia, il compilatore Visual Basic gestisce le proprietà del `My.Forms` dell'oggetto in modo diverso e consente la `Is` o `IsNot` operatore per controllare lo stato della proprietà senza modificarne il valore.</span><span class="sxs-lookup"><span data-stu-id="f47b7-131">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f47b7-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="f47b7-132">Example</span></span>  
 <span data-ttu-id="f47b7-133">Questo esempio viene modificato il titolo del valore predefinito `SidebarMenu` form.</span><span class="sxs-lookup"><span data-stu-id="f47b7-133">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="f47b7-134">Per eseguire questo esempio, il progetto deve disporre di un form denominato `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="f47b7-134">For this example to work, your project must have a form named `SidebarMenu`.</span></span> <span data-ttu-id="f47b7-135">Per ulteriori informazioni, vedere [procedura: aggiungere Windows Form a un progetto](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="f47b7-135">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="f47b7-136">Il codice funziona solo in un progetto applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="f47b7-136">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f47b7-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f47b7-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="f47b7-138">Disponibilità per il tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="f47b7-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="f47b7-139">Tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="f47b7-139">Project type</span></span>|<span data-ttu-id="f47b7-140">Disponibile</span><span class="sxs-lookup"><span data-stu-id="f47b7-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="f47b7-141">Applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="f47b7-141">Windows Application</span></span>|<span data-ttu-id="f47b7-142">**Sì**</span><span class="sxs-lookup"><span data-stu-id="f47b7-142">**Yes**</span></span>|  
|<span data-ttu-id="f47b7-143">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="f47b7-143">Class Library</span></span>|<span data-ttu-id="f47b7-144">No</span><span class="sxs-lookup"><span data-stu-id="f47b7-144">No</span></span>|  
|<span data-ttu-id="f47b7-145">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="f47b7-145">Console Application</span></span>|<span data-ttu-id="f47b7-146">No</span><span class="sxs-lookup"><span data-stu-id="f47b7-146">No</span></span>|  
|<span data-ttu-id="f47b7-147">Libreria di controlli Windows</span><span class="sxs-lookup"><span data-stu-id="f47b7-147">Windows Control Library</span></span>|<span data-ttu-id="f47b7-148">No</span><span class="sxs-lookup"><span data-stu-id="f47b7-148">No</span></span>|  
|<span data-ttu-id="f47b7-149">Libreria di controlli Web</span><span class="sxs-lookup"><span data-stu-id="f47b7-149">Web Control Library</span></span>|<span data-ttu-id="f47b7-150">No</span><span class="sxs-lookup"><span data-stu-id="f47b7-150">No</span></span>|  
|<span data-ttu-id="f47b7-151">Servizio Windows</span><span class="sxs-lookup"><span data-stu-id="f47b7-151">Windows Service</span></span>|<span data-ttu-id="f47b7-152">No</span><span class="sxs-lookup"><span data-stu-id="f47b7-152">No</span></span>|  
|<span data-ttu-id="f47b7-153">Sito Web</span><span class="sxs-lookup"><span data-stu-id="f47b7-153">Web Site</span></span>|<span data-ttu-id="f47b7-154">No</span><span class="sxs-lookup"><span data-stu-id="f47b7-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f47b7-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f47b7-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="f47b7-156">Oggetti</span><span class="sxs-lookup"><span data-stu-id="f47b7-156">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="f47b7-157">Procedura: aggiungere un progetto Windows Form</span><span class="sxs-lookup"><span data-stu-id="f47b7-157">How to: Add Windows Forms to a Project</span></span>](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)  
 [<span data-ttu-id="f47b7-158">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="f47b7-158">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="f47b7-159">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="f47b7-159">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="f47b7-160">Accesso ai form di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="f47b7-160">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
