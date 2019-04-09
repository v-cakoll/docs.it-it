---
title: "Procedura: Gestire l'input da tastiera a livello di modulo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: fbb6587dde53592a94887c1ea19562e06c15afe3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135164"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="60102-102">Procedura: Gestire l'input da tastiera a livello di modulo</span><span class="sxs-lookup"><span data-stu-id="60102-102">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="60102-103">Windows Form consente di gestire i messaggi della tastiera a livello di form, prima che i messaggi raggiungano un controllo.</span><span class="sxs-lookup"><span data-stu-id="60102-103">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="60102-104">Questo argomento illustra come completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="60102-104">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="60102-105">Per gestire un messaggio della tastiera a livello di form</span><span class="sxs-lookup"><span data-stu-id="60102-105">To handle a keyboard message at the form level</span></span>  
  
-   <span data-ttu-id="60102-106">Gestire l'evento <xref:System.Windows.Forms.Control.KeyPress> o <xref:System.Windows.Forms.Control.KeyDown> del form di avvio e impostare la proprietà <xref:System.Windows.Forms.Form.KeyPreview%2A> del form su `true` in modo che i messaggi della tastiera vengano ricevuti dal form prima che raggiungano un controllo qualsiasi del form.</span><span class="sxs-lookup"><span data-stu-id="60102-106">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="60102-107">L'esempio di codice seguente gestisce l'evento <xref:System.Windows.Forms.Control.KeyPress> rilevando tutti i tasti numerici e usando "1", "4" e "7".</span><span class="sxs-lookup"><span data-stu-id="60102-107">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="60102-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="60102-108">Example</span></span>  
 <span data-ttu-id="60102-109">L'esempio di codice seguente è l'applicazione completa dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="60102-109">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="60102-110">L'applicazione include un oggetto <xref:System.Windows.Forms.TextBox> insieme a diversi altri controlli che consentono di spostare lo stato attivo da <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="60102-110">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="60102-111">L'evento <xref:System.Windows.Forms.Control.KeyPress> dell'oggetto <xref:System.Windows.Forms.Form> principale usa "1", "4" e "7" e l'evento <xref:System.Windows.Forms.Control.KeyPress> di <xref:System.Windows.Forms.TextBox> usa "2", "5" e "8" durante la visualizzazione dei tasti rimanenti.</span><span class="sxs-lookup"><span data-stu-id="60102-111">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="60102-112">Confrontare l'output di <xref:System.Windows.Forms.MessageBox> quando si preme un tasto numerico mentre lo stato attivo è su <xref:System.Windows.Forms.TextBox> con l'output di <xref:System.Windows.Forms.MessageBox> quando si preme un tasto numerico mentre lo stato attivo è su uno degli altri controlli.</span><span class="sxs-lookup"><span data-stu-id="60102-112">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="60102-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="60102-113">Compiling the Code</span></span>  
 <span data-ttu-id="60102-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="60102-114">This example requires:</span></span>  
  
-   <span data-ttu-id="60102-115">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="60102-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="60102-116">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="60102-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="60102-117">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="60102-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="60102-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60102-118">See also</span></span>

- [<span data-ttu-id="60102-119">Input da tastiera in un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="60102-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
