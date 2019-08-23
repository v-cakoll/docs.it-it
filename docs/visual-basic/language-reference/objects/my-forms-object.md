---
title: Oggetto My. Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9fa5c77dd12c98100e3d17fc473a6802180d1e32
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965975"
---
# <a name="myforms-object"></a><span data-ttu-id="a726c-102">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="a726c-102">My.Forms Object</span></span>
<span data-ttu-id="a726c-103">Fornisce le proprietà per l'accesso a un'istanza di ogni Windows Form dichiarato nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="a726c-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a726c-104">Note</span><span class="sxs-lookup"><span data-stu-id="a726c-104">Remarks</span></span>  
 <span data-ttu-id="a726c-105">L' `My.Forms` oggetto fornisce un'istanza di ogni form nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="a726c-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="a726c-106">Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà.</span><span class="sxs-lookup"><span data-stu-id="a726c-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="a726c-107">È possibile accedere ai moduli forniti dall' `My.Forms` oggetto utilizzando il nome del form, senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="a726c-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="a726c-108">Poiché il nome della proprietà è uguale al nome del tipo del form, questo consente di accedere a un form come se disponesse di un'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="a726c-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="a726c-109">Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="a726c-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="a726c-110">L' `My.Forms` oggetto espone solo i form associati al progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="a726c-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="a726c-111">Non fornisce l'accesso ai moduli dichiarati in dll a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a726c-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="a726c-112">Per accedere a un modulo fornito da una DLL, è necessario utilizzare il nome completo del modulo, scritto come *dllname*. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="a726c-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="a726c-113">È possibile usare la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> proprietà per ottenere una raccolta di tutti i form aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a726c-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="a726c-114">L'oggetto e le relative proprietà sono disponibili solo per le applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="a726c-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a726c-115">Properties</span><span class="sxs-lookup"><span data-stu-id="a726c-115">Properties</span></span>  
 <span data-ttu-id="a726c-116">Ogni proprietà dell' `My.Forms` oggetto fornisce l'accesso a un'istanza di un form nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="a726c-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="a726c-117">Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà e il tipo della proprietà è uguale al tipo del form.</span><span class="sxs-lookup"><span data-stu-id="a726c-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a726c-118">Se si verifica un conflitto di nomi, il nome della proprietà per accedere a un modulo è *RootNamespace*_*spazio dei nomi*\_*FormName*.</span><span class="sxs-lookup"><span data-stu-id="a726c-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="a726c-119">Si considerino, ad esempio, `Form1.`due moduli denominati se uno di questi moduli `WindowsApplication1` è nello spazio dei `Namespace1`nomi radice e nello spazio dei nomi `My.Forms.WindowsApplication1_Namespace1_Form1`, si accederà a tale modulo tramite.</span><span class="sxs-lookup"><span data-stu-id="a726c-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="a726c-120">L' `My.Forms` oggetto consente di accedere all'istanza del modulo principale dell'applicazione creato all'avvio.</span><span class="sxs-lookup"><span data-stu-id="a726c-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="a726c-121">Per tutti gli altri form, `My.Forms` l'oggetto crea una nuova istanza del form quando vi si accede e la archivia.</span><span class="sxs-lookup"><span data-stu-id="a726c-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="a726c-122">I tentativi successivi di accesso a tale proprietà restituiscono tale istanza del form.</span><span class="sxs-lookup"><span data-stu-id="a726c-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="a726c-123">È possibile eliminare un form assegnando `Nothing` alla proprietà per il form.</span><span class="sxs-lookup"><span data-stu-id="a726c-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="a726c-124">Il setter della proprietà chiama <xref:System.Windows.Forms.Form.Close%2A> il metodo del form, quindi `Nothing` assegna il valore archiviato.</span><span class="sxs-lookup"><span data-stu-id="a726c-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="a726c-125">Se si assegna un valore diverso `Nothing` da alla proprietà, il setter genera un' <xref:System.ArgumentException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="a726c-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="a726c-126">È possibile verificare se una proprietà dell' `My.Forms` oggetto archivia un'istanza del form utilizzando l' `Is` operatore OR `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="a726c-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="a726c-127">È possibile utilizzare gli operatori per verificare se il valore della proprietà è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="a726c-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a726c-128">In genere, `Is` l' `IsNot` operatore o deve leggere il valore della proprietà per eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="a726c-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="a726c-129">Tuttavia, se la proprietà è attualmente `Nothing`archiviata, la proprietà crea una nuova istanza del form e quindi restituisce tale istanza.</span><span class="sxs-lookup"><span data-stu-id="a726c-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="a726c-130">Tuttavia, il compilatore Visual Basic considera le proprietà dell' `My.Forms` oggetto in modo diverso e consente all' `IsNot` `Is` operatore OR di controllare lo stato della proprietà senza modificarne il valore.</span><span class="sxs-lookup"><span data-stu-id="a726c-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a726c-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="a726c-131">Example</span></span>  
 <span data-ttu-id="a726c-132">In questo esempio viene modificato il titolo del `SidebarMenu` modulo predefinito.</span><span class="sxs-lookup"><span data-stu-id="a726c-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 <span data-ttu-id="a726c-133">Per il corretto funzionamento di questo esempio, il progetto deve avere un `SidebarMenu`formato denominato.</span><span class="sxs-lookup"><span data-stu-id="a726c-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="a726c-134">Questo codice funzionerà solo in un progetto di applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="a726c-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a726c-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a726c-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="a726c-136">Disponibilità per tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="a726c-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="a726c-137">Tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="a726c-137">Project type</span></span>|<span data-ttu-id="a726c-138">Disponibile</span><span class="sxs-lookup"><span data-stu-id="a726c-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="a726c-139">Applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="a726c-139">Windows Application</span></span>|<span data-ttu-id="a726c-140">**Sì**</span><span class="sxs-lookup"><span data-stu-id="a726c-140">**Yes**</span></span>|  
|<span data-ttu-id="a726c-141">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="a726c-141">Class Library</span></span>|<span data-ttu-id="a726c-142">No</span><span class="sxs-lookup"><span data-stu-id="a726c-142">No</span></span>|  
|<span data-ttu-id="a726c-143">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="a726c-143">Console Application</span></span>|<span data-ttu-id="a726c-144">No</span><span class="sxs-lookup"><span data-stu-id="a726c-144">No</span></span>|  
|<span data-ttu-id="a726c-145">Libreria di controlli Windows</span><span class="sxs-lookup"><span data-stu-id="a726c-145">Windows Control Library</span></span>|<span data-ttu-id="a726c-146">No</span><span class="sxs-lookup"><span data-stu-id="a726c-146">No</span></span>|  
|<span data-ttu-id="a726c-147">Libreria di controlli Web</span><span class="sxs-lookup"><span data-stu-id="a726c-147">Web Control Library</span></span>|<span data-ttu-id="a726c-148">No</span><span class="sxs-lookup"><span data-stu-id="a726c-148">No</span></span>|  
|<span data-ttu-id="a726c-149">Servizio Windows</span><span class="sxs-lookup"><span data-stu-id="a726c-149">Windows Service</span></span>|<span data-ttu-id="a726c-150">No</span><span class="sxs-lookup"><span data-stu-id="a726c-150">No</span></span>|  
|<span data-ttu-id="a726c-151">Sito Web</span><span class="sxs-lookup"><span data-stu-id="a726c-151">Web Site</span></span>|<span data-ttu-id="a726c-152">No</span><span class="sxs-lookup"><span data-stu-id="a726c-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a726c-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a726c-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="a726c-154">Oggetti</span><span class="sxs-lookup"><span data-stu-id="a726c-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="a726c-155">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="a726c-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="a726c-156">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="a726c-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="a726c-157">Accesso ai form di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="a726c-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
