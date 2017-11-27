---
title: Cenni preliminari sul componente ColorDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f3a25c601e46c18a30755a15131bba03669a2ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="3d61d-102">Cenni preliminari sul componente ColorDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="3d61d-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="3d61d-103">Windows Form <xref:System.Windows.Forms.ColorDialog> componente è una finestra di dialogo preconfigurata che consente all'utente di selezionare un colore dalla tavolozza e di aggiungere colori personalizzati alla tavolozza.</span><span class="sxs-lookup"><span data-stu-id="3d61d-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="3d61d-104">È la stessa finestra di dialogo visualizzata in altre applicazioni basate su Windows per selezionare i colori.</span><span class="sxs-lookup"><span data-stu-id="3d61d-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="3d61d-105">e costituisce una semplice soluzione, utilizzabile nell'applicazione basata su Windows creata, per evitare di configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3d61d-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="3d61d-106">Il colore selezionato nella finestra di dialogo viene restituito nel <xref:System.Windows.Forms.ColorDialog.Color%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d61d-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="3d61d-107">Se il <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> è impostata su `false`, il pulsante "Definisci colori personalizzati" è disabilitato e l'utente è limitato per i colori predefiniti nella tavolozza.</span><span class="sxs-lookup"><span data-stu-id="3d61d-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="3d61d-108">Se il <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> è impostata su `true`, l'utente non è possibile selezionare i colori con dithering.</span><span class="sxs-lookup"><span data-stu-id="3d61d-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="3d61d-109">Per visualizzare la finestra di dialogo, è necessario chiamare il relativo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="3d61d-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d61d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d61d-110">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="3d61d-111">Componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="3d61d-111">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [<span data-ttu-id="3d61d-112">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="3d61d-112">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [<span data-ttu-id="3d61d-113">Procedura: Modificare l'aspetto del componente ColorDialog di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3d61d-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
