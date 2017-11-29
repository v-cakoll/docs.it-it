---
title: 'Procedura: progettare un layout di Windows Form che risponda correttamente alla localizzazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3584b1a5751257c558d5e000135478966605f9c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="1e7de-102">Procedura: progettare un layout di Windows Form che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="1e7de-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="1e7de-103">La creazione di form pronti per la localizzazione accelera notevolmente lo sviluppo per i mercati internazionali.</span><span class="sxs-lookup"><span data-stu-id="1e7de-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="1e7de-104">È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per implementare layout che rispondano correttamente man mano che i controlli vengono ridimensionati in seguito alle modifiche dei valori della proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7de-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e7de-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e7de-105">Example</span></span>  
 <span data-ttu-id="1e7de-106">In questo form viene illustrato come creare un layout che viene modificato proporzionalmente quando si traducono i valori stringa visualizzati in altre lingue.</span><span class="sxs-lookup"><span data-stu-id="1e7de-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="1e7de-107">Questo processo di traduzione è denominato *localizzazione*.</span><span class="sxs-lookup"><span data-stu-id="1e7de-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="1e7de-108">Per altre informazioni, vedere [Localizzazione](../../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-108">For more information, see [Localization](../../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="1e7de-109">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="1e7de-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="1e7de-110">Vedere anche [Procedura dettagliata: creazione di un layout dalle proporzioni adattabili per la localizzazione](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1e7de-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  <span data-ttu-id="1e7de-111">[Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-111">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="1e7de-112">[Procedura dettagliata: disposizione dei controlli in Windows Form usando FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-112">[Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="1e7de-113">[Procedura: Inserire righe e colonne in un controllo TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-113">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="1e7de-114">[Procedura: Modificare colonne e righe in un controllo TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-114">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
5.  <span data-ttu-id="1e7de-115">[Procedura dettagliata: esecuzione di attività comuni usando gli smart tag nei controlli Windows Form](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-115">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span></span>  
  
6.  <span data-ttu-id="1e7de-116">[Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-116">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
7.  <span data-ttu-id="1e7de-117">[Procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-117">[Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span></span>  
  
8.  <span data-ttu-id="1e7de-118">[Procedura: Supportare la localizzazione in Windows Form usando la proprietà AutoSize e il controllo TableLayoutPanel](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-118">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span></span>  
  
9. <span data-ttu-id="1e7de-119">[Procedura dettagliata: creazione di un Windows Form ridimensionabile per l'inserimento di dati](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1e7de-119">[Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1e7de-120">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1e7de-120">Compiling the Code</span></span>  
 <span data-ttu-id="1e7de-121">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e7de-121">This example requires:</span></span>  
  
-   <span data-ttu-id="1e7de-122">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1e7de-122">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1e7de-123">Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-123">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1e7de-124">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="1e7de-124">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="1e7de-125">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1e7de-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7de-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e7de-126">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [<span data-ttu-id="1e7de-127">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="1e7de-127">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)
