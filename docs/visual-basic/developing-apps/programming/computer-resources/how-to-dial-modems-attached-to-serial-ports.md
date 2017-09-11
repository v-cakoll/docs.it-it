---
title: 'Procedura: comporre numeri con modem collegati a porte seriali in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- modems, dialing
- serial ports, dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0daaf35cdebac3d69ddc536124d4c86b96955b11
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="e893d-102">Procedura: comporre numeri con modem collegati a porte seriali in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e893d-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="e893d-103">In questo argomento viene descritto come usare `My.Computer.Ports` per comporre numeri con modem in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e893d-103">This topic describes how to use `My.Computer.Ports` to dial a modem in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="e893d-104">In genere, il modem è collegato a una delle porte seriali del computer.</span><span class="sxs-lookup"><span data-stu-id="e893d-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="e893d-105">Affinché l'applicazione comunichi con il modem, è necessario inviare i comandi alla porta seriale appropriata.</span><span class="sxs-lookup"><span data-stu-id="e893d-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="e893d-106">Comporre numeri con modem</span><span class="sxs-lookup"><span data-stu-id="e893d-106">To dial a modem</span></span>  
  
1.  <span data-ttu-id="e893d-107">Determinare a quale porta seriale è connesso il modem.</span><span class="sxs-lookup"><span data-stu-id="e893d-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="e893d-108">Nell'esempio si presuppone che il modem sia collegato a COM1.</span><span class="sxs-lookup"><span data-stu-id="e893d-108">This example assumes the modem is on COM1.</span></span>  
  
2.  <span data-ttu-id="e893d-109">Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta.</span><span class="sxs-lookup"><span data-stu-id="e893d-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="e893d-110">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="e893d-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="e893d-111">Il blocco `Using` consente all'applicazione di chiudere la porta seriale anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e893d-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="e893d-112">Tutto il codice relativo alla porta seriale deve essere all'interno di questo blocco o di un blocco `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="e893d-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     <span data-ttu-id="e893d-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e893d-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span></span>  
  
3.  <span data-ttu-id="e893d-114">Impostare la proprietà `DtrEnable` per indicare che il computer è pronto ad accettare una trasmissione in ingresso dal modem.</span><span class="sxs-lookup"><span data-stu-id="e893d-114">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     <span data-ttu-id="e893d-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e893d-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span></span>  
  
4.  <span data-ttu-id="e893d-116">Inviare il comando di connessione e il numero di telefono al modem attraverso la porta seriale usando il metodo <xref:System.IO.Ports.SerialPort.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="e893d-116">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     <span data-ttu-id="e893d-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e893d-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e893d-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e893d-118">Example</span></span>  
 <span data-ttu-id="e893d-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e893d-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span></span>  
  
 <span data-ttu-id="e893d-120">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e893d-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e893d-121">Nella selezione del frammento di codice si trova in **Connettività e rete**.</span><span class="sxs-lookup"><span data-stu-id="e893d-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="e893d-122">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="e893d-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e893d-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e893d-123">Compiling the Code</span></span>  
 <span data-ttu-id="e893d-124">Nell'esempio è richiesto un riferimento allo spazio dei nomi <xref:System?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e893d-124">This example requires a reference to the <xref:System?displayProperty=fullName> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e893d-125">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e893d-125">Robust Programming</span></span>  
 <span data-ttu-id="e893d-126">Nell'esempio si presuppone che il modem sia collegato a COM1.</span><span class="sxs-lookup"><span data-stu-id="e893d-126">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="e893d-127">È consigliabile che il codice consenta all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili.</span><span class="sxs-lookup"><span data-stu-id="e893d-127">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="e893d-128">Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="e893d-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="e893d-129">Questo esempio usa un blocco `Using` per verificare che l'applicazione chiuda la porta anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e893d-129">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="e893d-130">Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e893d-130">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="e893d-131">In questo esempio, l'applicazione si disconnette dalla porta seriale dopo aver composto il numero con il modem.</span><span class="sxs-lookup"><span data-stu-id="e893d-131">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="e893d-132">In uno scenario reale, l'utente vuole trasferire i dati da e verso il modem.</span><span class="sxs-lookup"><span data-stu-id="e893d-132">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="e893d-133">Per altre informazioni, vedere [Procedura: Ricevere stringhe da porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="e893d-133">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e893d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e893d-134">See Also</span></span>  
 <span data-ttu-id="e893d-135"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="e893d-135"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="e893d-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e893d-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="e893d-137">[Procedura: Inviare stringhe a porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="e893d-137">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 <span data-ttu-id="e893d-138">[Procedura: Ricevere stringhe da porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="e893d-138">[How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span></span>  
 [<span data-ttu-id="e893d-139">Procedura: Mostrare le porte seriali disponibili</span><span class="sxs-lookup"><span data-stu-id="e893d-139">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

