---
title: 'Procedura dettagliata: copiare e incollare un controllo ElementHost in Windows Form separati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 65882925c6fbe3e9b393b139a937bc9a1f95ed04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="42eb4-102">Procedura dettagliata: copiare e incollare un controllo ElementHost in Windows Form separati</span><span class="sxs-lookup"><span data-stu-id="42eb4-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="42eb4-103">Questa procedura dettagliata mostra come copiare un controllo Windows Presentation Foundation (WPF) da un Windows Form a un altro.</span><span class="sxs-lookup"><span data-stu-id="42eb4-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="42eb4-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="42eb4-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="42eb4-105">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="42eb4-105">Create the project.</span></span>  
  
-   <span data-ttu-id="42eb4-106">Copiare un controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="42eb4-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42eb4-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="42eb4-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="42eb4-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="42eb4-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="42eb4-109">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="42eb4-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42eb4-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="42eb4-110">Prerequisites</span></span>  
 <span data-ttu-id="42eb4-111">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="42eb4-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="42eb4-112">.</span><span class="sxs-lookup"><span data-stu-id="42eb4-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="42eb4-113">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="42eb4-113">Creating the Project</span></span>  
 <span data-ttu-id="42eb4-114">Il primo passaggio consiste nella creazione del progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="42eb4-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42eb4-115">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="42eb4-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="42eb4-116">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="42eb4-116">To create the project</span></span>  
  
-   <span data-ttu-id="42eb4-117">Creare un nuovo progetto applicazione Windows Forms in Visual Basic o Visual c# denominato `CopyElementHost`.</span><span class="sxs-lookup"><span data-stu-id="42eb4-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="42eb4-118">Copia di un controllo WPF</span><span class="sxs-lookup"><span data-stu-id="42eb4-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="42eb4-119">Dopo aver aggiunto un controllo WPF al progetto, è possibile copiarlo in altri form del progetto.</span><span class="sxs-lookup"><span data-stu-id="42eb4-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="42eb4-120">Per copiare un controllo WPF</span><span class="sxs-lookup"><span data-stu-id="42eb4-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="42eb4-121">Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="42eb4-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="42eb4-122">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="42eb4-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="42eb4-123">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="42eb4-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="42eb4-124">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="42eb4-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="42eb4-125">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="42eb4-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="42eb4-126">Dal **della casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="42eb4-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="42eb4-127">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="42eb4-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="42eb4-128">Con `elementHost1` selezionato, premere CTRL+C per copiarlo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="42eb4-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="42eb4-129">Aggiungere un nuovo Windows Form al progetto.</span><span class="sxs-lookup"><span data-stu-id="42eb4-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="42eb4-130">Usare il nome predefinito per il tipo di form, `Form2`.</span><span class="sxs-lookup"><span data-stu-id="42eb4-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="42eb4-131">Con `Form2` aperto in Progettazione Windows Form, premere CTRL+V per incollare una copia di `elementHost1` nel form.</span><span class="sxs-lookup"><span data-stu-id="42eb4-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="42eb4-132">Anche il controllo copiato viene denominato `elementHost1`, perché è un campo privato della classe `Form2`.</span><span class="sxs-lookup"><span data-stu-id="42eb4-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="42eb4-133">Non esiste alcun conflitto di nomi con `elementHost1` della classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="42eb4-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42eb4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42eb4-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="42eb4-135">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="42eb4-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="42eb4-136">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="42eb4-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="42eb4-137">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="42eb4-137">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
