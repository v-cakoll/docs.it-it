---
title: 'Procedura: Comporre numeri con modem collegati a porte seriali in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: db99f94d27235a7c9dca4fc5339854a39147b585
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490613"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="9d882-102">Procedura: Comporre numeri con modem collegati a porte seriali in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d882-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="9d882-103">Questo argomento descrive come usare `My.Computer.Ports` per comporre numeri con modem in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9d882-103">This topic describes how to use `My.Computer.Ports` to dial a modem in Visual Basic.</span></span>  
  
 <span data-ttu-id="9d882-104">In genere, il modem è collegato a una delle porte seriali del computer.</span><span class="sxs-lookup"><span data-stu-id="9d882-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="9d882-105">Affinché l'applicazione comunichi con il modem, è necessario inviare i comandi alla porta seriale appropriata.</span><span class="sxs-lookup"><span data-stu-id="9d882-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="9d882-106">Comporre numeri con modem</span><span class="sxs-lookup"><span data-stu-id="9d882-106">To dial a modem</span></span>  
  
1.  <span data-ttu-id="9d882-107">Determinare a quale porta seriale è connesso il modem.</span><span class="sxs-lookup"><span data-stu-id="9d882-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="9d882-108">Nell'esempio si presuppone che il modem sia collegato a COM1.</span><span class="sxs-lookup"><span data-stu-id="9d882-108">This example assumes the modem is on COM1.</span></span>  
  
2.  <span data-ttu-id="9d882-109">Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta.</span><span class="sxs-lookup"><span data-stu-id="9d882-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="9d882-110">Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d882-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="9d882-111">Il blocco `Using` consente all'applicazione di chiudere la porta seriale anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9d882-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="9d882-112">Tutto il codice relativo alla porta seriale deve essere all'interno di questo blocco o di un blocco `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="9d882-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]  
  
3.  <span data-ttu-id="9d882-113">Impostare la proprietà `DtrEnable` per indicare che il computer è pronto ad accettare una trasmissione in ingresso dal modem.</span><span class="sxs-lookup"><span data-stu-id="9d882-113">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]  
  
4.  <span data-ttu-id="9d882-114">Inviare il comando di connessione e il numero di telefono al modem attraverso la porta seriale usando il metodo <xref:System.IO.Ports.SerialPort.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d882-114">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="9d882-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d882-115">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]  
  
 <span data-ttu-id="9d882-116">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9d882-116">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="9d882-117">Nella selezione del frammento di codice si trova in **Connettività e rete**.</span><span class="sxs-lookup"><span data-stu-id="9d882-117">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="9d882-118">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="9d882-118">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d882-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9d882-119">Compiling the Code</span></span>  
 <span data-ttu-id="9d882-120">Nell'esempio è richiesto un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9d882-120">This example requires a reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9d882-121">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="9d882-121">Robust Programming</span></span>  
 <span data-ttu-id="9d882-122">Nell'esempio si presuppone che il modem sia collegato a COM1.</span><span class="sxs-lookup"><span data-stu-id="9d882-122">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="9d882-123">È consigliabile che il codice consenta all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili.</span><span class="sxs-lookup"><span data-stu-id="9d882-123">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="9d882-124">Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="9d882-124">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="9d882-125">Questo esempio usa un blocco `Using` per verificare che l'applicazione chiuda la porta anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9d882-125">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="9d882-126">Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9d882-126">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="9d882-127">In questo esempio, l'applicazione si disconnette dalla porta seriale dopo aver composto il numero con il modem.</span><span class="sxs-lookup"><span data-stu-id="9d882-127">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="9d882-128">In uno scenario reale, l'utente vuole trasferire i dati da e verso il modem.</span><span class="sxs-lookup"><span data-stu-id="9d882-128">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="9d882-129">Per altre informazioni, vedere [Procedura: Ricevere stringhe da porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="9d882-129">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d882-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d882-130">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="9d882-131">Procedura: Inviare stringhe a porte seriali</span><span class="sxs-lookup"><span data-stu-id="9d882-131">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="9d882-132">Procedura: Ricevere stringhe da porte seriali</span><span class="sxs-lookup"><span data-stu-id="9d882-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
- [<span data-ttu-id="9d882-133">Procedura: Mostrare le porte seriali disponibili</span><span class="sxs-lookup"><span data-stu-id="9d882-133">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
