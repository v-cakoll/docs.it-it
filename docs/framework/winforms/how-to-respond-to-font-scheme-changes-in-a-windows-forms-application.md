---
title: Rispondere alle modifiche dello schema dei tipi di carattere in un'app Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739231"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="b8a3a-102">Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="b8a3a-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="b8a3a-103">Nei sistemi operativi Windows, un utente può modificare le impostazioni del tipo di carattere a livello di sistema in modo che il tipo di carattere predefinito risulti più grande o più piccolo.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="b8a3a-104">La modifica di queste impostazioni dei tipi di carattere è fondamentale per gli utenti che hanno un impatto visivo e richiedono un tipo più grande per leggere il testo sulle schermate.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="b8a3a-105">È possibile modificare le Windows Forms Application per rispondere a queste modifiche aumentando o diminuendo le dimensioni del form e tutto il testo contenuto ogni volta che lo schema del tipo di carattere viene modificato.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="b8a3a-106">Se si desidera che il form soddisfi le modifiche delle dimensioni dei tipi di carattere in modo dinamico, è possibile aggiungere codice al form.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="b8a3a-107">In genere, il tipo di carattere predefinito usato da Windows Forms è il tipo di carattere restituito dalla chiamata dello spazio dei nomi <xref:Microsoft.Win32> a `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="b8a3a-108">Il tipo di carattere restituito da questa chiamata viene modificato solo quando cambia la risoluzione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="b8a3a-109">Come illustrato nella procedura seguente, il codice deve modificare il tipo di carattere predefinito in <xref:System.Drawing.SystemFonts.IconTitleFont%2A> per rispondere alle modifiche apportate alle dimensioni del carattere.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="b8a3a-110">Per utilizzare il tipo di carattere desktop e rispondere alle modifiche dello schema del carattere</span><span class="sxs-lookup"><span data-stu-id="b8a3a-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="b8a3a-111">Creare il form e aggiungere i controlli desiderati.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="b8a3a-112">Per altre informazioni, vedere [procedura: creare un'applicazione Windows Forms dalla riga di comando](how-to-create-a-windows-forms-application-from-the-command-line.md) e [controlli da usare in Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b8a3a-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="b8a3a-113">Aggiungere un riferimento allo spazio dei nomi <xref:Microsoft.Win32> al codice.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="b8a3a-114">Aggiungere il codice seguente al costruttore del form per associare i gestori eventi obbligatori e per modificare il tipo di carattere predefinito in uso per il form.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="b8a3a-115">Implementare un gestore per l'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> che determina la scalabilità automatica del modulo quando cambia la categoria <xref:Microsoft.Win32.UserPreferenceCategory.Window>.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="b8a3a-116">Infine, implementare un gestore per l'evento <xref:System.Windows.Forms.Form.FormClosing> che scollega il gestore dell'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="b8a3a-117">La mancata inclusione di questo codice causerà la perdita di memoria da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="b8a3a-118">Compilare ed eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="b8a3a-119">Per modificare manualmente lo schema dei tipi di carattere in Windows XP</span><span class="sxs-lookup"><span data-stu-id="b8a3a-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="b8a3a-120">Mentre il Windows Forms Application è in esecuzione, fare clic con il pulsante destro del mouse sul desktop di Windows e scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="b8a3a-121">Nella finestra di dialogo **proprietà di visualizzazione** fare clic sulla scheda **aspetto** .</span><span class="sxs-lookup"><span data-stu-id="b8a3a-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="b8a3a-122">Nella casella di riepilogo a discesa **dimensioni carattere** selezionare una nuova dimensione del carattere.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="b8a3a-123">Si noterà che il modulo ora reagisce alle modifiche della fase di esecuzione nello schema del tipo di carattere del desktop.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="b8a3a-124">Quando l'utente passa da un tipo di carattere **normale**a un carattere di **grandi dimensioni**e da **caratteri molto grandi**, il form modifica il tipo di carattere e ridimensiona correttamente.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8a3a-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8a3a-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="b8a3a-126">Il costruttore in questo esempio di codice contiene una chiamata a `InitializeComponent`, che viene definita quando si crea un nuovo progetto di Windows Forms in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-126">The constructor in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="b8a3a-127">Rimuovere questa riga di codice se si compila l'applicazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b8a3a-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a3a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8a3a-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="b8a3a-129">Ridimensionamento automatico in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b8a3a-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
