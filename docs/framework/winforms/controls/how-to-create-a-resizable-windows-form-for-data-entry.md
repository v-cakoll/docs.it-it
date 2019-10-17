---
title: 'Procedura: creare Windows Form ridimensionabile per immissione dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: aeab1b506b9ded4c3c2ab527f07a8655a44cad2b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396018"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="8202c-102">Procedura: creare Windows Form ridimensionabile per immissione dati</span><span class="sxs-lookup"><span data-stu-id="8202c-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="8202c-103">Un layout appropriato risponde correttamente alle modifiche apportate alle dimensioni del form padre.</span><span class="sxs-lookup"><span data-stu-id="8202c-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="8202c-104">È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per disporre il layout del form in modo che i controlli vengano ridimensionati e posizionati in maniera coerente quando cambiano le dimensioni del form.</span><span class="sxs-lookup"><span data-stu-id="8202c-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="8202c-105">Il controllo <xref:System.Windows.Forms.TableLayoutPanel> è utile anche quando le modifiche del contenuto dei controlli generano modifiche nel layout.</span><span class="sxs-lookup"><span data-stu-id="8202c-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="8202c-106">Il processo descritto in questa procedura può essere eseguito nell'ambiente di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8202c-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="8202c-107">Vedere anche [Procedura dettagliata: creazione di un Windows Form ridimensionabile per l'inserimento di dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8202c-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8202c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="8202c-108">Example</span></span>  
 <span data-ttu-id="8202c-109">L'esempio seguente illustra come usare un controllo <xref:System.Windows.Forms.TableLayoutPanel> per creare un layout che risponda correttamente quando l'utente ridimensiona il form.</span><span class="sxs-lookup"><span data-stu-id="8202c-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="8202c-110">Illustra anche un layout che risponda correttamente alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="8202c-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8202c-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8202c-111">Compiling the Code</span></span>  
 <span data-ttu-id="8202c-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8202c-112">This example requires:</span></span>  
  
- <span data-ttu-id="8202c-113">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8202c-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8202c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8202c-114">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="8202c-115">Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8202c-115">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="8202c-116">Procedura: Progettare un layout di Windows Form che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="8202c-116">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
