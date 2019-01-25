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
ms.openlocfilehash: e2caf421e25dff3300b3d799582f4260d0aab320
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586657"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="44260-102">Procedura: Determinare quale tasto di modifica è stato premuto</span><span class="sxs-lookup"><span data-stu-id="44260-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="44260-103">Quando si crea un'applicazione che accetta le sequenze di tasti dell'utente, è anche possibile monitorare i tasti di modifica, ad esempio i tasti MAIUSC, ALT e CTRL.</span><span class="sxs-lookup"><span data-stu-id="44260-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="44260-104">Quando viene premuto un tasto modificatore in combinazione con altre chiavi, o con clic del mouse, l'applicazione può rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="44260-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="44260-105">Ad esempio, se si preme la lettera S, ciò può comportare semplicemente una "s" venga visualizzato sullo schermo, ma se vengono premuti i tasti CTRL + S, può essere salvato nel documento corrente.</span><span class="sxs-lookup"><span data-stu-id="44260-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="44260-106">Se si gestisce il <xref:System.Windows.Forms.Control.KeyDown> evento, il <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> proprietà del <xref:System.Windows.Forms.KeyEventArgs> ricevuto dall'evento gestore specifica vengono premuti i tasti di modifica.</span><span class="sxs-lookup"><span data-stu-id="44260-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="44260-107">In alternativa, il <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> proprietà di <xref:System.Windows.Forms.KeyEventArgs> specifica il carattere che è stato premuto anche come tasti di modifica combinati con un OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="44260-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="44260-108">Tuttavia, se si sta gestendo il <xref:System.Windows.Forms.Control.KeyPress> un evento o un mouse, il gestore dell'evento non riceve queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="44260-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="44260-109">In questo caso, è necessario usare il <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà del <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="44260-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="44260-110">In entrambi i casi, è necessario eseguire un'operazione con AND bit per bit di appropriato <xref:System.Windows.Forms.Keys> valore e il valore si sta testando.</span><span class="sxs-lookup"><span data-stu-id="44260-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="44260-111">Il <xref:System.Windows.Forms.Keys> enumerazione offre varianti di ogni chiave di modificatore, pertanto è importante eseguire bit per bit e con il valore corretto.</span><span class="sxs-lookup"><span data-stu-id="44260-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="44260-112">Ad esempio, il tasto MAIUSC è rappresentato da <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> e <xref:System.Windows.Forms.Keys.LShiftKey> il valore corretto per eseguire il test MAIUSC come chiave di modificatore <xref:System.Windows.Forms.Keys.Shift>.</span><span class="sxs-lookup"><span data-stu-id="44260-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="44260-113">Analogamente, per verificare di tasti CTRL e ALT come modificatori è necessario utilizzare il <xref:System.Windows.Forms.Keys.Control> e <xref:System.Windows.Forms.Keys.Alt> rispettivamente i valori.</span><span class="sxs-lookup"><span data-stu-id="44260-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44260-114">I programmatori Visual Basic possono inoltre accedere a informazioni chiave attraverso il <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> proprietà</span><span class="sxs-lookup"><span data-stu-id="44260-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="44260-115">Per determinare quale tasto di modifica premuto</span><span class="sxs-lookup"><span data-stu-id="44260-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="44260-116">Usare bit per bit `AND` operatore con il <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà e il valore di <xref:System.Windows.Forms.Keys> enumerazione per determinare se viene premuto un tasto di modifica specifico.</span><span class="sxs-lookup"><span data-stu-id="44260-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="44260-117">Esempio di codice seguente viene illustrato come determinare se il tasto MAIUSC è premuto all'interno di un <xref:System.Windows.Forms.Control.KeyPress> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="44260-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="44260-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44260-118">See also</span></span>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="44260-119">Input da tastiera in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44260-119">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="44260-120">Procedura: Determinare che se BLOC MAIUSC è attivo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44260-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](https://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)
