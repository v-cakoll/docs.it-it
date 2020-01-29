---
title: Esplorare i dati con il controllo BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
ms.openlocfilehash: 10508cb447e70cc387f9d98effa3bc4b5ccbbaa9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736006"
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="ef299-102">Procedura: Esplorare i dati con il controllo BindingNavigator Windows Form</span><span class="sxs-lookup"><span data-stu-id="ef299-102">How to: Navigate Data with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="ef299-103">L'introduzione del controllo <xref:System.Windows.Forms.BindingNavigator> in Windows Form consente agli sviluppatori di fornire agli utenti finali un'interfaccia utente di navigazione e modifica di dati semplice nei form che creano.</span><span class="sxs-lookup"><span data-stu-id="ef299-103">The advent of the <xref:System.Windows.Forms.BindingNavigator> control in Windows Forms enables developers to provide end users with a simple data navigation and manipulation user interface on the forms they create.</span></span>  
  
 <span data-ttu-id="ef299-104"><xref:System.Windows.Forms.BindingNavigator> è un controllo <xref:System.Windows.Forms.ToolStrip> con pulsanti preconfigurati per la navigazione al primo, ultimo, successivo e precedente record in un set di dati e fornisce anche i pulsanti per aggiungere ed eliminare i record.</span><span class="sxs-lookup"><span data-stu-id="ef299-104">The <xref:System.Windows.Forms.BindingNavigator> control is a <xref:System.Windows.Forms.ToolStrip> control with buttons preconfigured for navigation to the first, last, next, and previous record in a data set, as well as buttons to add and delete records.</span></span> <span data-ttu-id="ef299-105">L'aggiunta di pulsanti al controllo <xref:System.Windows.Forms.BindingNavigator> è facile perché si tratta di un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="ef299-105">Adding buttons to the <xref:System.Windows.Forms.BindingNavigator> control is easy, because it is a <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ef299-106">Per esempi, vedere [procedura: aggiungere i pulsanti carica, Salva e Annulla al controllo Windows Forms BindingNavigator](load-save-and-cancel-bindingnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="ef299-106">For examples, see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](load-save-and-cancel-bindingnavigator.md).</span></span>  
  
 <span data-ttu-id="ef299-107">Per ogni pulsante del controllo <xref:System.Windows.Forms.BindingNavigator> esiste un membro corrispondente del componente <xref:System.Windows.Forms.BindingSource> che fornisce consente la stessa funzionalità a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="ef299-107">For each button on the <xref:System.Windows.Forms.BindingNavigator> control, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically allows the same functionality.</span></span> <span data-ttu-id="ef299-108">Il pulsante <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A>, ad esempio, corrisponde al metodo <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> del componente <xref:System.Windows.Forms.BindingSource>, il pulsante <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> corrisponde al metodo <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> e così via.</span><span class="sxs-lookup"><span data-stu-id="ef299-108">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span> <span data-ttu-id="ef299-109">Di conseguenza, l'abilitazione del controllo <xref:System.Windows.Forms.BindingNavigator> per navigare tra i record di dati risulta facile quanto impostare la proprietà <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> nel componente <xref:System.Windows.Forms.BindingSource> appropriato del form.</span><span class="sxs-lookup"><span data-stu-id="ef299-109">As a result, enabling the <xref:System.Windows.Forms.BindingNavigator> control to navigate data records is a simple as setting its <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the appropriate <xref:System.Windows.Forms.BindingSource> component on the form.</span></span>  
  
### <a name="to-set-up-the-bindingnavigator-control"></a><span data-ttu-id="ef299-110">Per configurare il controllo BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="ef299-110">To set up the BindingNavigator control</span></span>  
  
1. <span data-ttu-id="ef299-111">Aggiungere un componente <xref:System.Windows.Forms.BindingSource> denominato `bindingSource1` e due controlli <xref:System.Windows.Forms.TextBox> denominati `textBox1` e `textBox2`.</span><span class="sxs-lookup"><span data-stu-id="ef299-111">Add a <xref:System.Windows.Forms.BindingSource> component named `bindingSource1` and two <xref:System.Windows.Forms.TextBox> controls named `textBox1` and `textBox2`.</span></span>  
  
2. <span data-ttu-id="ef299-112">Associare `bindingSource1` ai dati e i controlli textbox a `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="ef299-112">Bind `bindingSource1` to data, and the textbox controls to `bindingSource1`.</span></span> <span data-ttu-id="ef299-113">A tale scopo, incollare il codice seguente nel form e chiamare `LoadData` dal costruttore del form o dal metodo di gestione eventi <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="ef299-113">To do this, paste the following code into your form and call `LoadData` from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="ef299-114">Aggiungere un controllo <xref:System.Windows.Forms.BindingNavigator> denominato `bindingNavigator1` al form.</span><span class="sxs-lookup"><span data-stu-id="ef299-114">Add a <xref:System.Windows.Forms.BindingNavigator> control named `bindingNavigator1` to your form.</span></span>  
  
4. <span data-ttu-id="ef299-115">Impostare la proprietà <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> per `bindingNavigator1` su `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="ef299-115">Set the <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property for `bindingNavigator1` to `bindingSource1`.</span></span> <span data-ttu-id="ef299-116">È possibile farlo con la finestra di progettazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="ef299-116">You can do this with the designer or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="ef299-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef299-117">Example</span></span>  
 <span data-ttu-id="ef299-118">L'esempio di codice seguente è l'esempio completo dei passaggi elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ef299-118">The following code example is the complete example for the steps listed previously.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ef299-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ef299-119">Compiling the Code</span></span>  
 <span data-ttu-id="ef299-120">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef299-120">This example requires:</span></span>  
  
- <span data-ttu-id="ef299-121">Riferimenti agli assembly System, System.Data, System.Drawing, System.Windows.Forms e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="ef299-121">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef299-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef299-122">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="ef299-123">Controllo BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="ef299-123">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="ef299-124">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ef299-124">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
