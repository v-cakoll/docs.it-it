---
title: "Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 85770687ecfad690a251eafec9051c4c20f45dd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182104"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="3b1f6-102">Procedura: Rispondere a modifiche delle combinazioni dei tipi di carattere in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b1f6-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="3b1f6-103">Nei sistemi operativi Windows, un utente può modificare le impostazioni del tipo di carattere a livello di sistema per rendere il tipo di carattere predefinito superiore o inferiore.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="3b1f6-104">Modifica di queste impostazioni del tipo di carattere è fondamentale per gli utenti che hanno problemi di vista e richiedono il tipo più grande contenere il testo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="3b1f6-105">È possibile modificare l'applicazione Windows Forms per rispondere a queste modifiche, aumentando o riducendo le dimensioni del form e tutto il testo relativo a ogni volta che viene modificato lo schema del tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="3b1f6-106">Se si desidera che il form per supportare le modifiche nelle dimensioni dei caratteri in modo dinamico, è possibile aggiungere codice al form.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="3b1f6-107">In genere, il tipo di carattere predefinito utilizzato da Windows Form è il tipo di carattere restituito per il <xref:Microsoft.Win32> chiamata dello spazio dei nomi a `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="3b1f6-108">Il tipo di carattere restituito da questa chiamata cambia solo quando cambia la risoluzione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="3b1f6-109">Come illustrato nella procedura seguente, il codice necessario modificare il tipo di carattere predefinito <xref:System.Drawing.SystemFonts.IconTitleFont%2A> per rispondere alle modifiche nella dimensione del carattere.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="3b1f6-110">Usare il tipo di carattere del desktop e rispondere alle modifiche dello schema del tipo di carattere</span><span class="sxs-lookup"><span data-stu-id="3b1f6-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="3b1f6-111">Creare il form e aggiungervi i controlli desiderati.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="3b1f6-112">Per altre informazioni, vedere [Procedura: Creare un'applicazione di Windows Forms dalla riga di comando](how-to-create-a-windows-forms-application-from-the-command-line.md) e [controlli da usare in Windows Form](./controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3b1f6-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="3b1f6-113">Aggiungere un riferimento di <xref:Microsoft.Win32> dello spazio dei nomi al codice.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="3b1f6-114">Aggiungere il codice seguente al costruttore del form per associare i gestori di evento richiesto e per modificare il tipo di carattere predefinito in uso per il form.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="3b1f6-115">Implementare un gestore per il <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> evento che attiva il form per la scalabilità automatica quando il <xref:Microsoft.Win32.UserPreferenceCategory.Window> le modifiche della categoria.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="3b1f6-116">Infine, implementare un gestore per il <xref:System.Windows.Forms.Form.FormClosing> eventi che consente di scollegare il <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="3b1f6-117">Errore per includere questo codice causerà l'applicazione per determinare una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  <span data-ttu-id="3b1f6-118">Compilare ed eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="3b1f6-119">Per modificare manualmente lo schema del tipo di carattere in Windows XP</span><span class="sxs-lookup"><span data-stu-id="3b1f6-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="3b1f6-120">Durante l'esecuzione dell'applicazione Windows Form, fare doppio clic sul desktop di Windows e scegliere **proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="3b1f6-121">Nel **le proprietà di visualizzazione** finestra di dialogo, fare clic sul **aspetto** scheda.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="3b1f6-122">Dal **Font Size** elenco a discesa, selezionare una nuova dimensione del carattere.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="3b1f6-123">Si noterà che il form ora reagisce alle modifiche di runtime nello schema di carattere del desktop.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="3b1f6-124">Quando l'utente passa tra **Normal**, **caratteri grandi**, e **caratteri molto grandi**, il form Cambia tipo di carattere e ridimensiona in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b1f6-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b1f6-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="3b1f6-126">Il costruttore in questo esempio di codice contiene una chiamata a `InitializeComponent`, che viene definito quando si crea un nuovo progetto Windows Forms in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="3b1f6-127">Rimuovere questa riga di codice se si compila l'applicazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b1f6-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b1f6-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="3b1f6-129">Ridimensionamento automatico in Windows Form</span><span class="sxs-lookup"><span data-stu-id="3b1f6-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
