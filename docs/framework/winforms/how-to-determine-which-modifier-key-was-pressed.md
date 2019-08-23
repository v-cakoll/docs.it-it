---
title: 'Procedura: Determinare quale tasto di modifica è stato premuto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 37fa897f5a2e1c65cbd5db9189f1500e3427c920
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964318"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="36a84-102">Procedura: Determinare quale tasto di modifica è stato premuto</span><span class="sxs-lookup"><span data-stu-id="36a84-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="36a84-103">Quando si crea un'applicazione che accetta le sequenze di tasti dell'utente, può essere utile monitorare anche i tasti di modifica, ad esempio i tasti MAIUSC, ALT e CTRL.</span><span class="sxs-lookup"><span data-stu-id="36a84-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="36a84-104">Quando si preme un tasto di modifica in combinazione con altre chiavi o con clic del mouse, l'applicazione può rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="36a84-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="36a84-105">Se, ad esempio, si preme la lettera S, è possibile che venga visualizzato uno "s" sullo schermo, ma se vengono premuti i tasti CTRL + S, è possibile salvare il documento corrente.</span><span class="sxs-lookup"><span data-stu-id="36a84-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="36a84-106">Se si gestisce l' <xref:System.Windows.Forms.Control.KeyDown> evento, la <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> proprietà dell'oggetto <xref:System.Windows.Forms.KeyEventArgs> ricevuto dal gestore eventi specifica i tasti di modifica che vengono premuti.</span><span class="sxs-lookup"><span data-stu-id="36a84-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="36a84-107">In alternativa, la <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> proprietà di <xref:System.Windows.Forms.KeyEventArgs> specifica il carattere premuto e tutti i tasti di modifica combinati con un OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="36a84-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="36a84-108">Tuttavia, se si gestisce l' <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, il gestore eventi non riceve queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="36a84-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="36a84-109">In questo caso, è necessario usare la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà <xref:System.Windows.Forms.Control> della classe.</span><span class="sxs-lookup"><span data-stu-id="36a84-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="36a84-110">In entrambi i casi, è necessario eseguire un operatore and bit per <xref:System.Windows.Forms.Keys> bit del valore appropriato e il valore che si sta testando.</span><span class="sxs-lookup"><span data-stu-id="36a84-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="36a84-111">L' <xref:System.Windows.Forms.Keys> enumerazione offre varianti di ogni tasto di modifica, quindi è importante eseguire l'operatore and bit per bit con il valore corretto.</span><span class="sxs-lookup"><span data-stu-id="36a84-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="36a84-112">Ad esempio, il tasto MAIUSC è rappresentato da <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.RShiftKey> , <xref:System.Windows.Forms.Keys.ShiftKey>e <xref:System.Windows.Forms.Keys.LShiftKey> il valore corretto per testare lo spostamento come un tasto di modifica <xref:System.Windows.Forms.Keys.Shift>è.</span><span class="sxs-lookup"><span data-stu-id="36a84-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="36a84-113">Analogamente, per verificare la presenza di tasti CTRL e ALT come modificatori <xref:System.Windows.Forms.Keys.Control> , <xref:System.Windows.Forms.Keys.Alt> è necessario usare rispettivamente i valori e.</span><span class="sxs-lookup"><span data-stu-id="36a84-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36a84-114">I programmatori Visual Basic possono anche accedere alle informazioni chiave <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> tramite la proprietà</span><span class="sxs-lookup"><span data-stu-id="36a84-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="36a84-115">Per determinare quale tasto di modifica è stato premuto</span><span class="sxs-lookup"><span data-stu-id="36a84-115">To determine which modifier key was pressed</span></span>  
  
- <span data-ttu-id="36a84-116">Usare l'operatore `AND` bit per bit <xref:System.Windows.Forms.Control.ModifierKeys%2A> con la proprietà <xref:System.Windows.Forms.Keys> e un valore dell'enumerazione per determinare se viene premuto un particolare tasto di modifica.</span><span class="sxs-lookup"><span data-stu-id="36a84-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="36a84-117">Nell'esempio di codice seguente viene illustrato come determinare se il tasto MAIUSC è premuto in <xref:System.Windows.Forms.Control.KeyPress> un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="36a84-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="36a84-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36a84-118">See also</span></span>

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="36a84-119">Input da tastiera in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36a84-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- <span data-ttu-id="36a84-120">[Procedura: Determinare se CapsLock è on in Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="36a84-120">[How to: Determine If CapsLock is On in Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span></span>
