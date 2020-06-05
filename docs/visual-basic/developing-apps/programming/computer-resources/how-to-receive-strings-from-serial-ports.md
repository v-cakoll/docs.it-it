---
title: 'Procedura: Ricevere stringhe da porte seriali'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: 93b6b47d89d05331c85a6459bba7d6fd5e2e3377
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401836"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="cd085-102">Procedura: ricevere stringhe da porte seriali in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd085-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>

<span data-ttu-id="cd085-103">Questo argomento descrive come usare `My.Computer.Ports` per ricevere stringhe dalle porte seriali del computer in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cd085-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in Visual Basic.</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="cd085-104">Per ricevere stringhe dalla porta seriale</span><span class="sxs-lookup"><span data-stu-id="cd085-104">To receive strings from the serial port</span></span>  
  
1. <span data-ttu-id="cd085-105">Inizializzare la stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="cd085-105">Initialize the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. <span data-ttu-id="cd085-106">Determinare quale porta seriale deve fornire le stringhe.</span><span class="sxs-lookup"><span data-stu-id="cd085-106">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="cd085-107">In questo esempio si presuppone che sia `COM1`.</span><span class="sxs-lookup"><span data-stu-id="cd085-107">This example assumes it is `COM1`.</span></span>  
  
3. <span data-ttu-id="cd085-108">Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta.</span><span class="sxs-lookup"><span data-stu-id="cd085-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="cd085-109">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd085-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="cd085-110">Il blocco `Try...Catch...Finally` consente all'applicazione di chiudere la porta seriale, anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd085-110">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="cd085-111">Tutto il codice per la modifica della porta seriale deve essere contenuto all'interno di questo blocco.</span><span class="sxs-lookup"><span data-stu-id="cd085-111">All code that manipulates the serial port should appear within this block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. <span data-ttu-id="cd085-112">Creare un ciclo `Do` per leggere le righe di testo fino a quando non sono più disponibili righe.</span><span class="sxs-lookup"><span data-stu-id="cd085-112">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. <span data-ttu-id="cd085-113">Usare il metodo <xref:System.IO.Ports.SerialPort.ReadLine> per leggere la successiva riga di testo disponibile dalla porta seriale.</span><span class="sxs-lookup"><span data-stu-id="cd085-113">Use the <xref:System.IO.Ports.SerialPort.ReadLine> method to read the next available line of text from the serial port.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. <span data-ttu-id="cd085-114">Usare un'istruzione `If` per determinare se il metodo <xref:System.IO.Ports.SerialPort.ReadLine> restituisce `Nothing`, il che significa che non è più disponibile testo.</span><span class="sxs-lookup"><span data-stu-id="cd085-114">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="cd085-115">Se restituisce `Nothing`, uscire dal ciclo `Do`.</span><span class="sxs-lookup"><span data-stu-id="cd085-115">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. <span data-ttu-id="cd085-116">Aggiungere un blocco `Else` all'istruzione `If` per gestire la situazione se la stringa viene effettivamente letta.</span><span class="sxs-lookup"><span data-stu-id="cd085-116">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="cd085-117">Il blocco consente di aggiungere la stringa dalla porta seriale alla stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="cd085-117">The block appends the string from the serial port to the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. <span data-ttu-id="cd085-118">Restituire la stringa.</span><span class="sxs-lookup"><span data-stu-id="cd085-118">Return the string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a><span data-ttu-id="cd085-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd085-119">Example</span></span>  

 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 <span data-ttu-id="cd085-120">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="cd085-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="cd085-121">Nella selezione del frammento di codice si trova in **Connettività e rete**.</span><span class="sxs-lookup"><span data-stu-id="cd085-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="cd085-122">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="cd085-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd085-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="cd085-123">Compiling the Code</span></span>  

 <span data-ttu-id="cd085-124">Questo esempio presuppone l'uso della porta `COM1`.</span><span class="sxs-lookup"><span data-stu-id="cd085-124">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cd085-125">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="cd085-125">Robust Programming</span></span>  

 <span data-ttu-id="cd085-126">Questo esempio presuppone l'uso della porta `COM1`.</span><span class="sxs-lookup"><span data-stu-id="cd085-126">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="cd085-127">Per garantire una maggiore flessibilità, il codice deve consentire all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili.</span><span class="sxs-lookup"><span data-stu-id="cd085-127">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="cd085-128">Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="cd085-128">For more information, see [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="cd085-129">Questo esempio usa un blocco `Try...Catch...Finally` per verificare che l'applicazione chiuda la porta e per rilevare tutte le eccezioni di timeout.</span><span class="sxs-lookup"><span data-stu-id="cd085-129">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="cd085-130">Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cd085-130">For more information, see [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd085-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd085-131">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="cd085-132">Procedura: Comporre numeri con modem collegati a porte seriali</span><span class="sxs-lookup"><span data-stu-id="cd085-132">How to: Dial Modems Attached to Serial Ports</span></span>](how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="cd085-133">Procedura: Inviare stringhe a porte seriali</span><span class="sxs-lookup"><span data-stu-id="cd085-133">How to: Send Strings to Serial Ports</span></span>](how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="cd085-134">Procedura: Mostrare le porte seriali disponibili</span><span class="sxs-lookup"><span data-stu-id="cd085-134">How to: Show Available Serial Ports</span></span>](how-to-show-available-serial-ports.md)
