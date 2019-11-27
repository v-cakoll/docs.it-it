---
title: Oggetto My.Forms
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: db86704fdc8120ccac5f4489c80a515834ad888f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350366"
---
# <a name="myforms-object"></a><span data-ttu-id="faa48-102">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="faa48-102">My.Forms Object</span></span>

<span data-ttu-id="faa48-103">Fornisce le proprietà per l'accesso a un'istanza di ogni Windows Form dichiarato nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="faa48-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>

## <a name="remarks"></a><span data-ttu-id="faa48-104">Note</span><span class="sxs-lookup"><span data-stu-id="faa48-104">Remarks</span></span>

<span data-ttu-id="faa48-105">L'oggetto `My.Forms` fornisce un'istanza di ogni form nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="faa48-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="faa48-106">Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà.</span><span class="sxs-lookup"><span data-stu-id="faa48-106">The name of the property is the same as the name of the form that the property accesses.</span></span>

<span data-ttu-id="faa48-107">È possibile accedere ai moduli forniti dall'oggetto `My.Forms` usando il nome del form, senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="faa48-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="faa48-108">Poiché il nome della proprietà è uguale al nome del tipo del form, questo consente di accedere a un form come se disponesse di un'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="faa48-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="faa48-109">Ad esempio, `My.Forms.Form1.Show` equivale a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="faa48-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>

<span data-ttu-id="faa48-110">L'oggetto `My.Forms` espone solo i form associati al progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="faa48-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="faa48-111">Non fornisce l'accesso ai moduli dichiarati in dll a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="faa48-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="faa48-112">Per accedere a un modulo fornito da una DLL, è necessario utilizzare il nome completo del modulo, scritto come *dllname*. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="faa48-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>

<span data-ttu-id="faa48-113">È possibile usare la proprietà <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> per ottenere una raccolta di tutti i form aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="faa48-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>

<span data-ttu-id="faa48-114">L'oggetto e le relative proprietà sono disponibili solo per le applicazioni Windows.</span><span class="sxs-lookup"><span data-stu-id="faa48-114">The object and its properties are available only for Windows applications.</span></span>

## <a name="properties"></a><span data-ttu-id="faa48-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="faa48-115">Properties</span></span>

<span data-ttu-id="faa48-116">Ogni proprietà dell'oggetto `My.Forms` fornisce l'accesso a un'istanza di un form nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="faa48-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="faa48-117">Il nome della proprietà è uguale al nome del modulo a cui accede la proprietà e il tipo della proprietà è uguale al tipo del form.</span><span class="sxs-lookup"><span data-stu-id="faa48-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>

> [!NOTE]
> <span data-ttu-id="faa48-118">Se si verifica un conflitto di nomi, il nome della proprietà per accedere a un modulo è *RootNamespace*_*namespace*\_*FormName*.</span><span class="sxs-lookup"><span data-stu-id="faa48-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="faa48-119">Si considerino, ad esempio, due moduli denominati `Form1.`se uno di questi form si trova nello spazio dei nomi radice `WindowsApplication1` e nello spazio dei nomi `Namespace1`, si accederà a tale modulo tramite `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="faa48-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>

<span data-ttu-id="faa48-120">L'oggetto `My.Forms` consente di accedere all'istanza del modulo principale dell'applicazione creato all'avvio.</span><span class="sxs-lookup"><span data-stu-id="faa48-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="faa48-121">Per tutti gli altri form, l'oggetto `My.Forms` crea una nuova istanza del form quando vi si accede e la archivia.</span><span class="sxs-lookup"><span data-stu-id="faa48-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="faa48-122">I tentativi successivi di accesso a tale proprietà restituiscono tale istanza del form.</span><span class="sxs-lookup"><span data-stu-id="faa48-122">Subsequent attempts to access that property return that instance of the form.</span></span>

<span data-ttu-id="faa48-123">È possibile eliminare un form assegnando `Nothing` alla proprietà per il form.</span><span class="sxs-lookup"><span data-stu-id="faa48-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="faa48-124">Il setter della proprietà chiama il metodo <xref:System.Windows.Forms.Form.Close%2A> del form, quindi assegna `Nothing` al valore archiviato.</span><span class="sxs-lookup"><span data-stu-id="faa48-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="faa48-125">Se si assegna un valore diverso da `Nothing` alla proprietà, il setter genera un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="faa48-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="faa48-126">È possibile verificare se una proprietà dell'oggetto `My.Forms` archivia un'istanza del form utilizzando l'operatore `Is` o `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="faa48-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="faa48-127">È possibile utilizzare tali operatori per verificare se il valore della proprietà è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="faa48-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>

> [!NOTE]
> <span data-ttu-id="faa48-128">In genere, l'operatore `Is` o `IsNot` deve leggere il valore della proprietà per eseguire il confronto.</span><span class="sxs-lookup"><span data-stu-id="faa48-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="faa48-129">Tuttavia, se la proprietà archivia attualmente `Nothing`, la proprietà crea una nuova istanza del form e quindi restituisce tale istanza.</span><span class="sxs-lookup"><span data-stu-id="faa48-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="faa48-130">Tuttavia, il compilatore Visual Basic considera le proprietà dell'oggetto `My.Forms` in modo diverso e consente all'operatore `Is` o `IsNot` di controllare lo stato della proprietà senza modificarne il valore.</span><span class="sxs-lookup"><span data-stu-id="faa48-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>

## <a name="example"></a><span data-ttu-id="faa48-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="faa48-131">Example</span></span>

<span data-ttu-id="faa48-132">Questo esempio Mostra come modificare il titolo del modulo predefinito `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="faa48-132">This example changes the title of the default `SidebarMenu` form.</span></span>

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

<span data-ttu-id="faa48-133">Per il corretto funzionamento di questo esempio, il progetto deve avere un modulo denominato `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="faa48-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>

<span data-ttu-id="faa48-134">Questo codice funzionerà solo in un progetto di applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="faa48-134">This code will work only in a Windows Application project.</span></span>

## <a name="requirements"></a><span data-ttu-id="faa48-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="faa48-135">Requirements</span></span>

### <a name="availability-by-project-type"></a><span data-ttu-id="faa48-136">Disponibilità per tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="faa48-136">Availability by Project Type</span></span>

|<span data-ttu-id="faa48-137">Tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="faa48-137">Project type</span></span>|<span data-ttu-id="faa48-138">Disponibile</span><span class="sxs-lookup"><span data-stu-id="faa48-138">Available</span></span>|
|---|---|
|<span data-ttu-id="faa48-139">Applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="faa48-139">Windows Application</span></span>|<span data-ttu-id="faa48-140">**Sì**</span><span class="sxs-lookup"><span data-stu-id="faa48-140">**Yes**</span></span>|
|<span data-ttu-id="faa48-141">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="faa48-141">Class Library</span></span>|<span data-ttu-id="faa48-142">No</span><span class="sxs-lookup"><span data-stu-id="faa48-142">No</span></span>|
|<span data-ttu-id="faa48-143">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="faa48-143">Console Application</span></span>|<span data-ttu-id="faa48-144">No</span><span class="sxs-lookup"><span data-stu-id="faa48-144">No</span></span>|
|<span data-ttu-id="faa48-145">Libreria di controlli Windows</span><span class="sxs-lookup"><span data-stu-id="faa48-145">Windows Control Library</span></span>|<span data-ttu-id="faa48-146">No</span><span class="sxs-lookup"><span data-stu-id="faa48-146">No</span></span>|
|<span data-ttu-id="faa48-147">Libreria di controlli Web</span><span class="sxs-lookup"><span data-stu-id="faa48-147">Web Control Library</span></span>|<span data-ttu-id="faa48-148">No</span><span class="sxs-lookup"><span data-stu-id="faa48-148">No</span></span>|
|<span data-ttu-id="faa48-149">Servizio Windows</span><span class="sxs-lookup"><span data-stu-id="faa48-149">Windows Service</span></span>|<span data-ttu-id="faa48-150">No</span><span class="sxs-lookup"><span data-stu-id="faa48-150">No</span></span>|
|<span data-ttu-id="faa48-151">Sito Web</span><span class="sxs-lookup"><span data-stu-id="faa48-151">Web Site</span></span>|<span data-ttu-id="faa48-152">No</span><span class="sxs-lookup"><span data-stu-id="faa48-152">No</span></span>|

## <a name="see-also"></a><span data-ttu-id="faa48-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faa48-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="faa48-154">Oggetti</span><span class="sxs-lookup"><span data-stu-id="faa48-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="faa48-155">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="faa48-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="faa48-156">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="faa48-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="faa48-157">Accesso ai form di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="faa48-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
