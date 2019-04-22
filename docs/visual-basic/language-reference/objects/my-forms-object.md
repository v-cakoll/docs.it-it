---
title: Oggetto My. Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 4998097b910a504461a34af3cc159ddb1c74cc62
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832554"
---
# <a name="myforms-object"></a><span data-ttu-id="1ad81-102">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="1ad81-102">My.Forms Object</span></span>
<span data-ttu-id="1ad81-103">Fornisce le proprietà per l'accesso a un'istanza di ogni modulo di Windows dichiarato nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="1ad81-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ad81-104">Note</span><span class="sxs-lookup"><span data-stu-id="1ad81-104">Remarks</span></span>  
 <span data-ttu-id="1ad81-105">Il `My.Forms` oggetto fornisce un'istanza di ogni forma nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="1ad81-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="1ad81-106">Il nome della proprietà è identico al nome del form che accede a proprietà.</span><span class="sxs-lookup"><span data-stu-id="1ad81-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="1ad81-107">È possibile accedere ai form forniti il `My.Forms` oggetto utilizzando il nome del modulo, senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="1ad81-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="1ad81-108">Poiché il nome della proprietà è lo stesso nome di tipo del form, in questo modo è possibile accedere a un modulo come se avesse un'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="1ad81-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="1ad81-109">Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="1ad81-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="1ad81-110">Il `My.Forms` oggetto espone solo le forme associate al progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="1ad81-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="1ad81-111">Non fornisce l'accesso ai moduli dichiarati nelle DLL di cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="1ad81-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="1ad81-112">Per accedere a un modulo che fornisce una DLL, è necessario usare il nome completo del modulo, scritto come *DllName*. *Nomemodulo*.</span><span class="sxs-lookup"><span data-stu-id="1ad81-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="1ad81-113">È possibile usare il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> proprietà da ottenere una raccolta di tutti i form aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1ad81-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="1ad81-114">L'oggetto e le relative proprietà sono disponibili solo per le applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="1ad81-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1ad81-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1ad81-115">Properties</span></span>  
 <span data-ttu-id="1ad81-116">Ogni proprietà del `My.Forms` oggetto consente di accedere a un'istanza di un form nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="1ad81-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="1ad81-117">Il nome della proprietà è identico al nome del form che accede a proprietà e il tipo della proprietà è identico al tipo del form.</span><span class="sxs-lookup"><span data-stu-id="1ad81-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ad81-118">Se si verifica un conflitto di nomi, è il nome della proprietà per accedere a un form *RootNamespace*_*Namespace*\_*nomemodulo*.</span><span class="sxs-lookup"><span data-stu-id="1ad81-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="1ad81-119">Ad esempio, considerare due form denominati `Form1.`se uno di questi moduli è nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, è necessario accedere al form tramite `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="1ad81-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="1ad81-120">Il `My.Forms` oggetto consente di accedere all'istanza del form principale dell'applicazione che è stato creato all'avvio.</span><span class="sxs-lookup"><span data-stu-id="1ad81-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="1ad81-121">Per tutti gli altri moduli di `My.Forms` oggetto crea una nuova istanza del form quando si accede e archiviarli.</span><span class="sxs-lookup"><span data-stu-id="1ad81-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="1ad81-122">I tentativi successivi di accedere a tale proprietà restituiscono quell'istanza del form.</span><span class="sxs-lookup"><span data-stu-id="1ad81-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="1ad81-123">È possibile rimuovere un form assegnando `Nothing` alla proprietà per tale modulo.</span><span class="sxs-lookup"><span data-stu-id="1ad81-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="1ad81-124">La proprietà setter chiama il <xref:System.Windows.Forms.Form.Close%2A> metodo del form e quindi assegna `Nothing` al valore archiviato.</span><span class="sxs-lookup"><span data-stu-id="1ad81-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="1ad81-125">Se si assegna un valore qualsiasi diverso da `Nothing` alla proprietà setter genera un <xref:System.ArgumentException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="1ad81-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="1ad81-126">È possibile verificare se una proprietà del `My.Forms` oggetto archivia un'istanza del form usando la `Is` o `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="1ad81-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="1ad81-127">È possibile usare tali operatori per verificare se il valore della proprietà è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1ad81-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ad81-128">In genere, il `Is` o `IsNot` operatore ha leggere il valore della proprietà per eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="1ad81-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="1ad81-129">Tuttavia, se la proprietà attualmente Archivia `Nothing`, la proprietà crea una nuova istanza della forma e quindi restituisce quell'istanza.</span><span class="sxs-lookup"><span data-stu-id="1ad81-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="1ad81-130">Tuttavia, il compilatore Visual Basic considera le proprietà del `My.Forms` dell'oggetto in modo diverso e consente il `Is` o `IsNot` operatore per controllare lo stato della proprietà senza modificarne il valore.</span><span class="sxs-lookup"><span data-stu-id="1ad81-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ad81-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ad81-131">Example</span></span>  
 <span data-ttu-id="1ad81-132">Questo esempio viene modificato il titolo dell'oggetto default `SidebarMenu` form.</span><span class="sxs-lookup"><span data-stu-id="1ad81-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 <span data-ttu-id="1ad81-133">Per questo esempio funzioni, il progetto deve avere un modulo denominato `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="1ad81-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="1ad81-134">Questo codice funziona solo in un progetto di applicazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1ad81-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ad81-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ad81-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="1ad81-136">Disponibilità dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="1ad81-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="1ad81-137">Tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="1ad81-137">Project type</span></span>|<span data-ttu-id="1ad81-138">Disponibile</span><span class="sxs-lookup"><span data-stu-id="1ad81-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="1ad81-139">Applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="1ad81-139">Windows Application</span></span>|<span data-ttu-id="1ad81-140">**Sì**</span><span class="sxs-lookup"><span data-stu-id="1ad81-140">**Yes**</span></span>|  
|<span data-ttu-id="1ad81-141">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="1ad81-141">Class Library</span></span>|<span data-ttu-id="1ad81-142">No</span><span class="sxs-lookup"><span data-stu-id="1ad81-142">No</span></span>|  
|<span data-ttu-id="1ad81-143">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="1ad81-143">Console Application</span></span>|<span data-ttu-id="1ad81-144">No</span><span class="sxs-lookup"><span data-stu-id="1ad81-144">No</span></span>|  
|<span data-ttu-id="1ad81-145">Libreria di controlli Windows</span><span class="sxs-lookup"><span data-stu-id="1ad81-145">Windows Control Library</span></span>|<span data-ttu-id="1ad81-146">No</span><span class="sxs-lookup"><span data-stu-id="1ad81-146">No</span></span>|  
|<span data-ttu-id="1ad81-147">Libreria di controlli Web</span><span class="sxs-lookup"><span data-stu-id="1ad81-147">Web Control Library</span></span>|<span data-ttu-id="1ad81-148">No</span><span class="sxs-lookup"><span data-stu-id="1ad81-148">No</span></span>|  
|<span data-ttu-id="1ad81-149">Servizio Windows</span><span class="sxs-lookup"><span data-stu-id="1ad81-149">Windows Service</span></span>|<span data-ttu-id="1ad81-150">No</span><span class="sxs-lookup"><span data-stu-id="1ad81-150">No</span></span>|  
|<span data-ttu-id="1ad81-151">Sito Web</span><span class="sxs-lookup"><span data-stu-id="1ad81-151">Web Site</span></span>|<span data-ttu-id="1ad81-152">No</span><span class="sxs-lookup"><span data-stu-id="1ad81-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ad81-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ad81-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="1ad81-154">Oggetti</span><span class="sxs-lookup"><span data-stu-id="1ad81-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="1ad81-155">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="1ad81-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="1ad81-156">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="1ad81-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="1ad81-157">Accesso ai form di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="1ad81-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
