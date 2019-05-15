---
title: 'Procedura: Progettare un layout di Windows Forms che risponda correttamente alla localizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 642eea482c875e9754352aca142db0f0fc87c7b2
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591898"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="418e1-102">Procedura: Progettare un layout di Windows Forms che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="418e1-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="418e1-103">La creazione di form pronti per la localizzazione accelera notevolmente lo sviluppo per i mercati internazionali.</span><span class="sxs-lookup"><span data-stu-id="418e1-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="418e1-104">È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per implementare layout che rispondano correttamente man mano che i controlli vengono ridimensionati in seguito alle modifiche dei valori della proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="418e1-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="418e1-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="418e1-105">Example</span></span>  
 <span data-ttu-id="418e1-106">In questo form viene illustrato come creare un layout che viene modificato proporzionalmente quando si traducono i valori stringa visualizzati in altre lingue.</span><span class="sxs-lookup"><span data-stu-id="418e1-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="418e1-107">Questo processo di traduzione è denominato *localizzazione*.</span><span class="sxs-lookup"><span data-stu-id="418e1-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="418e1-108">Per altre informazioni, vedere [Localizzazione](../../../standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="418e1-108">For more information, see [Localization](../../../standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="418e1-109">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="418e1-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="418e1-110">Vedere anche [procedura dettagliata: Creazione di un Layout dalle proporzioni adattabili per la localizzazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="418e1-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a><span data-ttu-id="418e1-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="418e1-111">Additional resources</span></span>
1. [<span data-ttu-id="418e1-112">Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="418e1-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="418e1-113">Procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="418e1-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [<span data-ttu-id="418e1-114">Procedura: Inserire righe e colonne in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="418e1-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="418e1-115">Procedura: Modificare colonne e righe in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="418e1-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [<span data-ttu-id="418e1-116">Procedura dettagliata: Esecuzione di attività comuni usando gli Smart tag nei Windows Form controlli</span><span class="sxs-lookup"><span data-stu-id="418e1-116">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [<span data-ttu-id="418e1-117">Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="418e1-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [<span data-ttu-id="418e1-118">Procedura dettagliata: Definire il layout dei Windows Form usando spaziatura, margini e la proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="418e1-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)  
  
8. <span data-ttu-id="418e1-119">[Procedura: Supportare la localizzazione in Windows Form usando AutoSize e il controllo TableLayoutPanel](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="418e1-119">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span></span>  
  
9. <span data-ttu-id="418e1-120">[Procedura dettagliata: Creazione di un Form Windows ridimensionabile per immissione dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="418e1-120">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="418e1-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="418e1-121">Compiling the Code</span></span>  
 <span data-ttu-id="418e1-122">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="418e1-122">This example requires:</span></span>  
  
- <span data-ttu-id="418e1-123">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="418e1-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418e1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="418e1-124">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="418e1-125">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="418e1-125">Localization</span></span>](../../../standard/globalization-localization/localization.md)
