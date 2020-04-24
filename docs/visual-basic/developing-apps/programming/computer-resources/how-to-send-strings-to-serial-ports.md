---
title: 'Procedura: Inviare stringhe a porte seriali'
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: b2051451142a7818a3b7d1bc564c5ae36b2579fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345579"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="7145e-102">Procedura: inviare stringhe a porte seriali in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7145e-102">How to: Send Strings to Serial Ports in Visual Basic</span></span>

<span data-ttu-id="7145e-103">Questo argomento descrive come usare `My.Computer.Ports` per inviare stringhe alle porte seriali del computer in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7145e-103">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in Visual Basic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7145e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7145e-104">Example</span></span>  

 <span data-ttu-id="7145e-105">In questo esempio si invia una stringa alla porta seriale COM1.</span><span class="sxs-lookup"><span data-stu-id="7145e-105">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="7145e-106">Potrebbe essere necessario usare un'altra porta seriale nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="7145e-106">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="7145e-107">Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta.</span><span class="sxs-lookup"><span data-stu-id="7145e-107">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="7145e-108">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="7145e-108">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="7145e-109">Il blocco `Using` consente all'applicazione di chiudere la porta seriale, anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7145e-109">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="7145e-110">Tutto il codice relativo alla porta seriale deve essere all'interno di questo blocco o di un blocco `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="7145e-110">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="7145e-111">Il metodo <xref:System.IO.Ports.SerialPort.WriteLine%2A> invia i dati alla porta seriale.</span><span class="sxs-lookup"><span data-stu-id="7145e-111">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7145e-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7145e-112">Compiling the Code</span></span>  
  
- <span data-ttu-id="7145e-113">Questo esempio presuppone l'uso della porta `COM1`.</span><span class="sxs-lookup"><span data-stu-id="7145e-113">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7145e-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7145e-114">Robust Programming</span></span>  

 <span data-ttu-id="7145e-115">Questo esempio presuppone che il computer usi la porta `COM1`; per una maggiore flessibilità, il codice deve consentire all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili.</span><span class="sxs-lookup"><span data-stu-id="7145e-115">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="7145e-116">Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="7145e-116">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="7145e-117">Questo esempio usa un blocco `Using` per verificare che l'applicazione chiuda la porta anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7145e-117">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="7145e-118">Per ulteriori informazioni, vedere [istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7145e-118">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7145e-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7145e-119">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="7145e-120">Procedura: Comporre numeri con modem collegati a porte seriali</span><span class="sxs-lookup"><span data-stu-id="7145e-120">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="7145e-121">Procedura: Mostrare le porte seriali disponibili</span><span class="sxs-lookup"><span data-stu-id="7145e-121">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
