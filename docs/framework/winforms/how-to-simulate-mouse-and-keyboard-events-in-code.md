---
title: 'Procedura: Simulare eventi di mouse e tastiera nel codice'
description: Informazioni su come usare le opzioni fornite da Windows Forms per simulare gli input del mouse e della tastiera a livello di codice.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: 3c60533479352151ac4f28690413ebc7d8e5879d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619247"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="6e4eb-103">Procedura: Simulare eventi di mouse e tastiera nel codice</span><span class="sxs-lookup"><span data-stu-id="6e4eb-103">How to: Simulate Mouse and Keyboard Events in Code</span></span>

<span data-ttu-id="6e4eb-104">Windows Form include diverse opzioni per simulare a livello di codice l'input del mouse e della tastiera.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-104">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="6e4eb-105">In questo argomento viene fornita una panoramica di queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-105">This topic provides an overview of these options.</span></span>

## <a name="simulating-mouse-input"></a><span data-ttu-id="6e4eb-106">Simulazione dell'input del mouse</span><span class="sxs-lookup"><span data-stu-id="6e4eb-106">Simulating Mouse Input</span></span>

<span data-ttu-id="6e4eb-107">Il modo migliore per simulare eventi del mouse consiste nel chiamare il metodo `On`*NomeEvento* che genera l'evento del mouse che si vuole simulare.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-107">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="6e4eb-108">Questa opzione è generalmente possibile solo all'interno di controlli e form personalizzati, perché i metodi che generano eventi sono protetti e non sono accessibili all'esterno del controllo o del form.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-108">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="6e4eb-109">Ad esempio, i passaggi seguenti illustrano come simulare il clic con il pulsante destro del mouse nel codice.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-109">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>

#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="6e4eb-110">Per fare clic con il pulsante destro del mouse a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6e4eb-110">To programmatically click the right mouse button</span></span>

1. <span data-ttu-id="6e4eb-111">Creare un oggetto <xref:System.Windows.Forms.MouseEventArgs> con la proprietà <xref:System.Windows.Forms.MouseEventArgs.Button%2A> impostata sul valore <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6e4eb-111">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>

2. <span data-ttu-id="6e4eb-112">Chiamare il metodo <xref:System.Windows.Forms.Control.OnMouseClick%2A> con <xref:System.Windows.Forms.MouseEventArgs> come argomento.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-112">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>

<span data-ttu-id="6e4eb-113">Per altre informazioni sui controlli personalizzati, vedere [Sviluppo di controlli Windows Form in fase di progettazione](./controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="6e4eb-113">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](./controls/developing-windows-forms-controls-at-design-time.md).</span></span>

<span data-ttu-id="6e4eb-114">Esistono altri modi per simulare l'input del mouse.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-114">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="6e4eb-115">Ad esempio, è possibile impostare a livello di codice una proprietà di un controllo che rappresenta uno stato normalmente impostato tramite l'input del mouse (come la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> del controllo <xref:System.Windows.Forms.CheckBox> ) oppure è possibile chiamare direttamente il delegato associato all'evento che si vuole simulare.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-115">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>

## <a name="simulating-keyboard-input"></a><span data-ttu-id="6e4eb-116">Simulazione dell'input da tastiera</span><span class="sxs-lookup"><span data-stu-id="6e4eb-116">Simulating Keyboard Input</span></span>

<span data-ttu-id="6e4eb-117">Anche se è possibile simulare l'input da tastiera usando le strategie descritte sopra per l'input del mouse, Windows Forms include anche la classe <xref:System.Windows.Forms.SendKeys> per inviare le pressioni di tasto all'applicazione attiva.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-117">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>

> [!CAUTION]
> <span data-ttu-id="6e4eb-118">Se l'applicazione verrà usata a livello internazionale con un'ampia gamma di tastiere, è opportuno evitare l'uso di <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> perché potrebbe generare risultati imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-118">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4eb-119">La classe <xref:System.Windows.Forms.SendKeys> è stata aggiornata per .NET Framework 3.0 per consentirne l'uso in applicazioni eseguite in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-119">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="6e4eb-120">La sicurezza avanzata di Windows Vista (nota come Controllo dell'account utente) impedisce alla precedente implementazione di funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-120">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>
>
> <span data-ttu-id="6e4eb-121">La classe <xref:System.Windows.Forms.SendKeys> è soggetta a problemi di temporizzazione, che alcuni sviluppatori hanno dovuto risolvere.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-121">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="6e4eb-122">L'implementazione aggiornata è ancora soggetta a problemi di temporizzazione, ma è leggermente più veloce e può richiedere modifiche alle soluzioni alternative.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-122">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="6e4eb-123">La classe <xref:System.Windows.Forms.SendKeys> cerca di usare prima l'implementazione precedente e, se il tentativo non riesce, usa la nuova implementazione.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-123">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="6e4eb-124">Di conseguenza, il comportamento della classe <xref:System.Windows.Forms.SendKeys> potrebbe essere diverso a seconda del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-124">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="6e4eb-125">Inoltre, quando la classe <xref:System.Windows.Forms.SendKeys> usa la nuova implementazione, il metodo <xref:System.Windows.Forms.SendKeys.SendWait%2A> non attenderà che i messaggi siano elaborati quando vengono inviati a un altro processo.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-125">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>
>
> <span data-ttu-id="6e4eb-126">Se l'applicazione si basa su un comportamento coerente indipendentemente dal sistema operativo, è possibile forzare la classe <xref:System.Windows.Forms.SendKeys> a usare la nuova implementazione aggiungendo la seguente impostazione applicazione al file app.config.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-126">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="6e4eb-127">Per forzare la classe <xref:System.Windows.Forms.SendKeys> a usare l'implementazione precedente, usare invece il valore `"JournalHook"` .</span><span class="sxs-lookup"><span data-stu-id="6e4eb-127">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>

#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="6e4eb-128">Per inviare una pressione di tasto alla stessa applicazione</span><span class="sxs-lookup"><span data-stu-id="6e4eb-128">To send a keystroke to the same application</span></span>

1. <span data-ttu-id="6e4eb-129">Chiamare il metodo <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> della classe <xref:System.Windows.Forms.SendKeys> .</span><span class="sxs-lookup"><span data-stu-id="6e4eb-129">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="6e4eb-130">Le pressioni di tasti specificate verranno ricevute dal controllo attivo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-130">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="6e4eb-131">Il seguente esempio di codice usa <xref:System.Windows.Forms.SendKeys.Send%2A> per simulare la pressione del tasto INVIO quando l'utente fa doppio clic sulla superficie del form.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-131">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="6e4eb-132">Questo esempio presuppone un <xref:System.Windows.Forms.Form> con un solo controllo <xref:System.Windows.Forms.Button> con un indice di tabulazione 0.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-132">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="6e4eb-133">Per inviare una pressione di tasto a un'applicazione diversa</span><span class="sxs-lookup"><span data-stu-id="6e4eb-133">To send a keystroke to a different application</span></span>

1. <span data-ttu-id="6e4eb-134">Attivare la finestra dell'applicazione che riceverà le pressioni di tasto e quindi chiamare il metodo <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> .</span><span class="sxs-lookup"><span data-stu-id="6e4eb-134">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="6e4eb-135">Poiché non esiste alcun metodo gestito per attivare un'altra applicazione, è necessario usare i metodi Windows nativi per forzare lo stato attivo su altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-135">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="6e4eb-136">Il seguente esempio di codice usa platform invoke per chiamare i metodi `FindWindow` e `SetForegroundWindow` per attivare la finestra dell'applicazione Calculator e quindi chiama <xref:System.Windows.Forms.SendKeys.SendWait%2A> per inviare una serie di calcoli all'applicazione Calculator.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-136">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e4eb-137">I parametri corretti della chiamata a `FindWindow` che trova l'applicazione Calculator dipendono dalla versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-137">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="6e4eb-138">Il codice seguente trova l'applicazione Calculator in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-138">The following code finds the Calculator application on Windows 7.</span></span> <span data-ttu-id="6e4eb-139">In Windows Vista modificare il primo parametro in "SciCalc".</span><span class="sxs-lookup"><span data-stu-id="6e4eb-139">On Windows Vista, change the first parameter to "SciCalc".</span></span> <span data-ttu-id="6e4eb-140">È possibile usare lo strumento Spy++, incluso in Visual Studio, per determinare i parametri corretti.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-140">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a><span data-ttu-id="6e4eb-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e4eb-141">Example</span></span>

<span data-ttu-id="6e4eb-142">L'esempio di codice seguente è l'applicazione completa degli esempi di codice precedenti.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-142">The following code example is the complete application for the previous code examples.</span></span>

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="6e4eb-143">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6e4eb-143">Compiling the Code</span></span>

<span data-ttu-id="6e4eb-144">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e4eb-144">This example requires:</span></span>

- <span data-ttu-id="6e4eb-145">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="6e4eb-145">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e4eb-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e4eb-146">See also</span></span>

- [<span data-ttu-id="6e4eb-147">Input dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6e4eb-147">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
