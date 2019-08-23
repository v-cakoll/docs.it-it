---
title: Definizione di classi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
ms.openlocfilehash: 679f4fd55f142c2c4bb63a556feb95c074960b12
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914739"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="599b5-102">Procedura dettagliata: Definizione di classi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="599b5-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="599b5-103">In questa procedura dettagliata viene illustrato come definire le classi, che è possibile utilizzare per creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="599b5-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="599b5-104">Viene inoltre illustrato come aggiungere proprietà e metodi alla nuova classe e viene illustrato come inizializzare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="599b5-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="599b5-105">Per definire una classe</span><span class="sxs-lookup"><span data-stu-id="599b5-105">To define a class</span></span>
  
1. <span data-ttu-id="599b5-106">Per creare un progetto, fare clic su **nuovo progetto** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="599b5-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="599b5-107">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="599b5-107">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="599b5-108">Selezionare applicazione Windows dall'elenco dei modelli di progetto Visual Basic per visualizzare il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="599b5-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="599b5-109">Per aggiungere una nuova classe al progetto, fare clic su **Aggiungi classe** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="599b5-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="599b5-110">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="599b5-110">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="599b5-111">Selezionare il modello di **classe** .</span><span class="sxs-lookup"><span data-stu-id="599b5-111">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="599b5-112">Assegnare un nome alla `UserNameInfo.vb`nuova classe e quindi fare clic su **Aggiungi** per visualizzare il codice per la nuova classe.</span><span class="sxs-lookup"><span data-stu-id="599b5-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > <span data-ttu-id="599b5-113">È possibile usare l' **editor di codice** Visual Basic per aggiungere una classe al form di avvio digitando la `Class` parola chiave seguita dal nome della nuova classe.</span><span class="sxs-lookup"><span data-stu-id="599b5-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="599b5-114">L' **editor di codice** fornisce un' `End Class` istruzione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="599b5-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="599b5-115">Definire un campo privato per la classe aggiungendo il codice seguente tra le `Class` istruzioni e: `End Class`</span><span class="sxs-lookup"><span data-stu-id="599b5-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="599b5-116">Dichiarare il campo come `Private` significa che può essere utilizzato solo all'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="599b5-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="599b5-117">È possibile rendere disponibili i campi dall'esterno di una classe usando i modificatori di `Public` accesso, ad esempio, che forniscono maggiore accesso.</span><span class="sxs-lookup"><span data-stu-id="599b5-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="599b5-118">Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="599b5-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="599b5-119">Definire una proprietà per la classe aggiungendo il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="599b5-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="599b5-120">Definire un metodo per la classe aggiungendo il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="599b5-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="599b5-121">Definire un costruttore con parametri per la nuova classe aggiungendo una procedura denominata `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="599b5-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="599b5-122">Il `Sub New` costruttore viene chiamato automaticamente quando viene creato un oggetto basato su questa classe.</span><span class="sxs-lookup"><span data-stu-id="599b5-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="599b5-123">Questo costruttore imposta il valore del campo che contiene il nome utente.</span><span class="sxs-lookup"><span data-stu-id="599b5-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="599b5-124">Per creare un pulsante per testare la classe</span><span class="sxs-lookup"><span data-stu-id="599b5-124">To create a button to test the class</span></span>
  
1. <span data-ttu-id="599b5-125">Modificare il modulo di avvio in modalità progettazione facendo clic con il pulsante destro del mouse sul nome in **Esplora soluzioni** e quindi scegliendo **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="599b5-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="599b5-126">Per impostazione predefinita, il form di avvio per i progetti di applicazioni Windows è denominato Form1. vb.</span><span class="sxs-lookup"><span data-stu-id="599b5-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="599b5-127">Verrà visualizzato il form principale.</span><span class="sxs-lookup"><span data-stu-id="599b5-127">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="599b5-128">Aggiungere un pulsante al form principale e fare doppio clic su di esso per visualizzare il codice per `Button1_Click` il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="599b5-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="599b5-129">Aggiungere il codice seguente per chiamare la procedura di test:</span><span class="sxs-lookup"><span data-stu-id="599b5-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="599b5-130">Per eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="599b5-130">To run your application</span></span>
  
1. <span data-ttu-id="599b5-131">Eseguire l'applicazione premendo F5.</span><span class="sxs-lookup"><span data-stu-id="599b5-131">Run your application by pressing F5.</span></span> <span data-ttu-id="599b5-132">Fare clic sul pulsante nel form per chiamare la procedura di test.</span><span class="sxs-lookup"><span data-stu-id="599b5-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="599b5-133">Viene visualizzato un messaggio che informa che l'originale `UserName` è "Moore, Bobby", perché la procedura ha chiamato `Capitalize` il metodo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="599b5-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="599b5-134">Fare clic su **OK** per chiudere la finestra del messaggio.</span><span class="sxs-lookup"><span data-stu-id="599b5-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="599b5-135">La `Button1 Click` stored procedure modifica il valore `UserName` della proprietà e visualizza un messaggio che informa che il nuovo valore di `UserName` è "worden, Joe".</span><span class="sxs-lookup"><span data-stu-id="599b5-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599b5-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="599b5-136">See also</span></span>

- [<span data-ttu-id="599b5-137">Programmazione orientata a oggetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="599b5-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="599b5-138">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="599b5-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
