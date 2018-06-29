---
title: "Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 2451885c673515eb6690b0784fd5bd22de629209
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071146"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="92d27-102">Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="92d27-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="92d27-103">Nei sistemi operativi Windows, un utente può modificare le impostazioni a livello di sistema per rendere il tipo di carattere predefinito più piccole o grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="92d27-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="92d27-104">Modifica di queste impostazioni del tipo di carattere è fondamentale per gli utenti che sono vedenti e richiedono un tipo più grande contenere il testo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="92d27-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="92d27-105">È possibile modificare l'applicazione Windows Form da reagire a queste modifiche aumentando o riducendo le dimensioni del form e tutto il testo ogni volta che viene modificato lo schema del tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="92d27-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="92d27-106">Se si desidera un modulo per supportare le modifiche nelle dimensioni del carattere in modo dinamico, è possibile aggiungere codice al form.</span><span class="sxs-lookup"><span data-stu-id="92d27-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="92d27-107">In genere, il tipo di carattere predefinito utilizzato da Windows Form viene usato il carattere restituito dal <xref:Microsoft.Win32> chiamata dello spazio dei nomi a `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="92d27-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="92d27-108">Il tipo di carattere restituito da questa chiamata cambia solo quando cambia la risoluzione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="92d27-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="92d27-109">Come illustrato nella procedura seguente, il codice necessario modificare il tipo di carattere predefinito <xref:System.Drawing.SystemFonts.IconTitleFont%2A> per rispondere alle modifiche apportate alle dimensioni del carattere.</span><span class="sxs-lookup"><span data-stu-id="92d27-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="92d27-110">Per utilizzare il tipo di carattere desktop e rispondere alle modifiche delle combinazioni di carattere</span><span class="sxs-lookup"><span data-stu-id="92d27-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="92d27-111">Creare il form e aggiungere i controlli desiderati.</span><span class="sxs-lookup"><span data-stu-id="92d27-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="92d27-112">Per altre informazioni, vedere [procedura: creare un'applicazione Windows Forms dalla riga di comando](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) e [controlli da usare in Windows Form](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="92d27-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="92d27-113">Aggiungere un riferimento al <xref:Microsoft.Win32> dello spazio dei nomi al codice.</span><span class="sxs-lookup"><span data-stu-id="92d27-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="92d27-114">Aggiungere il codice seguente al costruttore del form per associare i gestori di eventi necessarie e per modificare il tipo di carattere predefinito in uso per il form.</span><span class="sxs-lookup"><span data-stu-id="92d27-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="92d27-115">Implementare un gestore per il <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> evento che attiva il form per ridimensionare automaticamente quando il <xref:Microsoft.Win32.UserPreferenceCategory.Window> le modifiche della categoria.</span><span class="sxs-lookup"><span data-stu-id="92d27-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="92d27-116">Infine, implementare un gestore per il <xref:System.Windows.Forms.Form.FormClosing> evento che consente di scollegare il <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="92d27-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="92d27-117">L'errore per includere questo codice imposterà l'applicazione per determinare una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="92d27-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  <span data-ttu-id="92d27-118">Compilare ed eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="92d27-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="92d27-119">Per modificare manualmente la combinazione di tipi di carattere in Windows XP</span><span class="sxs-lookup"><span data-stu-id="92d27-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="92d27-120">Durante l'esecuzione di un'applicazione Windows Form destro del mouse sul desktop di Windows e scegliere **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="92d27-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="92d27-121">Nel **delle proprietà di visualizzazione** finestra di dialogo, fare clic sul **aspetto** scheda.</span><span class="sxs-lookup"><span data-stu-id="92d27-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="92d27-122">Dal **Font Size** elenco a discesa, selezionare una nuova dimensione del carattere.</span><span class="sxs-lookup"><span data-stu-id="92d27-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="92d27-123">Si noterà che il modulo reagisce ora per le modifiche in fase di esecuzione nello schema di carattere del desktop.</span><span class="sxs-lookup"><span data-stu-id="92d27-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="92d27-124">Quando l'utente modifica tra **normale**, **caratteri grandi**, e **caratteri molto grandi**, il modulo cambia tipo di carattere e la scala correttamente.</span><span class="sxs-lookup"><span data-stu-id="92d27-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92d27-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="92d27-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="92d27-126">Il costruttore in questo esempio di codice contiene una chiamata a `InitializeComponent`, che viene definito quando si crea un nuovo progetto Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="92d27-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="92d27-127">Rimuovere questa riga di codice se si compila l'applicazione nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="92d27-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d27-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92d27-128">See Also</span></span>  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [<span data-ttu-id="92d27-129">Ridimensionamento automatico in Windows Form</span><span class="sxs-lookup"><span data-stu-id="92d27-129">Automatic Scaling in Windows Forms</span></span>](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
