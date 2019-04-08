---
title: 'Procedura: Inviare stringhe a porte seriali in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: e1f0c9d5ba428f5379f8025c0e733cdbeb5204e0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822857"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="03847-102">Procedura: Inviare stringhe a porte seriali in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="03847-102">How to: Send Strings to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="03847-103">Questo argomento descrive come usare `My.Computer.Ports` per inviare stringhe alle porte seriali del computer in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="03847-103">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in Visual Basic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03847-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="03847-104">Example</span></span>  
 <span data-ttu-id="03847-105">In questo esempio si invia una stringa alla porta seriale COM1.</span><span class="sxs-lookup"><span data-stu-id="03847-105">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="03847-106">Potrebbe essere necessario usare un'altra porta seriale nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="03847-106">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="03847-107">Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta.</span><span class="sxs-lookup"><span data-stu-id="03847-107">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="03847-108">Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="03847-108">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="03847-109">Il blocco `Using` consente all'applicazione di chiudere la porta seriale anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03847-109">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="03847-110">Tutto il codice relativo alla porta seriale deve essere all'interno di questo blocco o di un blocco `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="03847-110">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="03847-111">Il metodo <xref:System.IO.Ports.SerialPort.WriteLine%2A> invia i dati alla porta seriale.</span><span class="sxs-lookup"><span data-stu-id="03847-111">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03847-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="03847-112">Compiling the Code</span></span>  
  
-   <span data-ttu-id="03847-113">Questo esempio presuppone l'uso della porta `COM1`.</span><span class="sxs-lookup"><span data-stu-id="03847-113">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="03847-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="03847-114">Robust Programming</span></span>  
 <span data-ttu-id="03847-115">Questo esempio presuppone che il computer usi la porta `COM1`; per una maggiore flessibilità, il codice deve consentire all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili.</span><span class="sxs-lookup"><span data-stu-id="03847-115">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="03847-116">Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="03847-116">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="03847-117">Questo esempio usa un blocco `Using` per verificare che l'applicazione chiuda la porta anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03847-117">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="03847-118">Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03847-118">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03847-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03847-119">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="03847-120">Procedura: Comporre numeri con modem collegati a porte seriali</span><span class="sxs-lookup"><span data-stu-id="03847-120">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="03847-121">Procedura: Mostrare le porte seriali disponibili</span><span class="sxs-lookup"><span data-stu-id="03847-121">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
