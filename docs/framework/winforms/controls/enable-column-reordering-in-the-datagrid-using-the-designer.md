---
title: Abilitare il riordinamento delle colonne nel controllo DataGridView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 823c0064b2710ab5dfd0f67edf95374590d4490b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745851"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="958f1-102">Procedura: abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="958f1-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="958f1-103">Quando si visualizzano i dati visualizzati in un controllo <xref:System.Windows.Forms.DataGridView> di Windows Forms, gli utenti talvolta desiderano confrontare i valori in colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="958f1-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="958f1-104">Questo può risultare scomodo se le colonne sono ampiamente separate nel controllo, soprattutto se gli utenti devono scorrere orizzontalmente per visualizzare tutte le colonne di interesse.</span><span class="sxs-lookup"><span data-stu-id="958f1-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="958f1-105">È possibile semplificare l'attività di confronto dei valori di colonna consentendo agli utenti di riordinare le colonne.</span><span class="sxs-lookup"><span data-stu-id="958f1-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="958f1-106">Quando si Abilita il riordinamento delle colonne, gli utenti possono spostare una colonna in una nuova posizione trascinando l'intestazione di colonna con il mouse.</span><span class="sxs-lookup"><span data-stu-id="958f1-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="958f1-107">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="958f1-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="958f1-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="958f1-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="958f1-109">Per abilitare il riordinamento delle colonne</span><span class="sxs-lookup"><span data-stu-id="958f1-109">To enable column reordering</span></span>

- <span data-ttu-id="958f1-110">Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **Abilita riordinamento colonne**.</span><span class="sxs-lookup"><span data-stu-id="958f1-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="958f1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="958f1-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="958f1-112">Procedura: Bloccare le colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="958f1-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="958f1-113">Procedura: creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="958f1-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="958f1-114">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="958f1-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
