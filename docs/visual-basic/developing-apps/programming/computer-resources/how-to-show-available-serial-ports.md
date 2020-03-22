---
title: 'Procedura: mostrare le porte seriali disponibili'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
ms.openlocfilehash: c7e5f797c1d098a3b2d01745b949ed50375ea7e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345567"
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a><span data-ttu-id="ec7aa-102">Procedura: mostrare le porte seriali disponibili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec7aa-102">How to: Show Available Serial Ports in Visual Basic</span></span>

<span data-ttu-id="ec7aa-103">Questo argomento descrive come usare `My.Computer.Ports` per visualizzare le porte seriali disponibili del computer in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-103">This topic describes how to use `My.Computer.Ports` to show the available serial ports of the computer in Visual Basic.</span></span>  
  
 <span data-ttu-id="ec7aa-104">I nomi delle porte seriali sono disponibili in un controllo <xref:System.Windows.Forms.ListBox> per consentire agli utenti di selezionare la porta da usare.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-104">To allow a user to select which port to use, the names of the serial ports are placed in a <xref:System.Windows.Forms.ListBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec7aa-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec7aa-105">Example</span></span>  

 <span data-ttu-id="ec7aa-106">Questo esempio esegue il ciclo attraverso tutte le stringhe restituite dalla proprietà `My.Computer.Ports.SerialPortNames`.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-106">This example loops over all the strings that the `My.Computer.Ports.SerialPortNames` property returns.</span></span> <span data-ttu-id="ec7aa-107">Queste stringhe rappresentano i nomi delle porte seriali disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-107">These strings are the names of the available serial ports on the computer.</span></span>  
  
 <span data-ttu-id="ec7aa-108">In genere, gli utenti selezionano la porta seriale che l'applicazione deve usare dall'elenco delle porte disponibili.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-108">Typically, a user selects which serial port the application should use from the list of available ports.</span></span> <span data-ttu-id="ec7aa-109">In questo esempio i nomi delle porte seriali sono archiviati un controllo <xref:System.Windows.Forms.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-109">In this example, the serial port names are stored in a <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="ec7aa-110">Per altre informazioni, vedere [Controllo ListBox](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ec7aa-110">For more information, see [ListBox Control](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span></span>  
  
 [!code-vb[VbVbalrMyComputer#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#45)]  
  
 <span data-ttu-id="ec7aa-111">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ec7aa-112">Nella selezione del frammento di codice si trova in **Connettività e rete**.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-112">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="ec7aa-113">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="ec7aa-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ec7aa-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ec7aa-114">Compiling the Code</span></span>  

 <span data-ttu-id="ec7aa-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec7aa-115">This example requires:</span></span>  
  
- <span data-ttu-id="ec7aa-116">Un riferimento del progetto a System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-116">A project reference to System.Windows.Forms.dll.</span></span>  
  
- <span data-ttu-id="ec7aa-117">Accedere ai membri dello spazio dei nomi <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-117">Access to the members of the <xref:System.Windows.Forms> namespace.</span></span> <span data-ttu-id="ec7aa-118">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="ec7aa-119">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="ec7aa-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
- <span data-ttu-id="ec7aa-120">Presenza all'interno del modulo di un controllo <xref:System.Windows.Forms.ListBox> denominato `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-120">That your form have a <xref:System.Windows.Forms.ListBox> control named `ListBox1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ec7aa-121">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ec7aa-121">Robust Programming</span></span>  

 <span data-ttu-id="ec7aa-122">Non è necessario usare il controllo <xref:System.Windows.Forms.ListBox> per visualizzare i nomi delle porte seriali disponibili.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-122">You do not have to use the <xref:System.Windows.Forms.ListBox> control to display the available serial port names.</span></span> <span data-ttu-id="ec7aa-123">In alternativa, è possibile usare un controllo <xref:System.Windows.Forms.ComboBox> o un altro controllo.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-123">Instead, you can use a <xref:System.Windows.Forms.ComboBox> or other control.</span></span> <span data-ttu-id="ec7aa-124">Se l'applicazione non richiede una risposta da parte dell'utente, è possibile usare un controllo <xref:System.Windows.Forms.TextBox> per visualizzare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-124">If the application does not need a response from the user, you can use a <xref:System.Windows.Forms.TextBox> control to display the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec7aa-125">I nomi delle porte restituiti da `My.Computer.Ports.SerialPortNames` potrebbero non essere corretti se l'applicazione viene eseguita con Windows 98.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-125">The port names returned by `My.Computer.Ports.SerialPortNames` may be incorrect when run on Windows 98.</span></span> <span data-ttu-id="ec7aa-126">Per evitare errori dell'applicazione, usare la funzione di gestione delle eccezioni, ad esempio l'istruzione `Try...Catch...Finally` o `Using`, quando per aprire le porte si usano i nomi delle porte stesse.</span><span class="sxs-lookup"><span data-stu-id="ec7aa-126">To prevent application errors, use exception handling, such as the `Try...Catch...Finally` statement or the `Using` statement, when using the port names to open ports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7aa-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec7aa-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [<span data-ttu-id="ec7aa-128">Procedura: comporre numeri con modem collegati a porte seriali</span><span class="sxs-lookup"><span data-stu-id="ec7aa-128">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="ec7aa-129">Procedura: inviare stringhe a porte seriali</span><span class="sxs-lookup"><span data-stu-id="ec7aa-129">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="ec7aa-130">Procedura: ricevere stringhe da porte seriali</span><span class="sxs-lookup"><span data-stu-id="ec7aa-130">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
