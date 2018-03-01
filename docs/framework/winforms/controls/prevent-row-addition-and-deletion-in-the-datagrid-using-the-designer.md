---
title: 'Procedura: impedire l''aggiunta e l''eliminazione di righe nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 029eb160545164535b8b5ae058cdc7ad85d69ab9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="b094e-102">Procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="b094e-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="b094e-103">Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="b094e-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b094e-104">Le nuove righe vengono immessi nella riga speciale per i nuovi record nella parte inferiore del controllo.</span><span class="sxs-lookup"><span data-stu-id="b094e-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="b094e-105">Quando si disabilita l'aggiunta delle righe, la riga per nuovi record non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="b094e-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="b094e-106">È possibile rendere il controllo interamente di sola lettura disabilitando l'eliminazione di righe e la modifica della cella.</span><span class="sxs-lookup"><span data-stu-id="b094e-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>  
  
 <span data-ttu-id="b094e-107">La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="b094e-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b094e-108">Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b094e-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b094e-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="b094e-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b094e-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b094e-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b094e-111">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b094e-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="b094e-112">Per impedire l'eliminazione e aggiunta delle righe</span><span class="sxs-lookup"><span data-stu-id="b094e-112">To prevent row addition and deletion</span></span>  
  
-   <span data-ttu-id="b094e-113">Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllare e quindi deselezionare la **Abilita aggiunta** e **Abilita eliminazione** caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="b094e-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b094e-114">Per rendere il controllo interamente di sola lettura, deselezionare il **Abilita modifica** anche casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="b094e-114">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b094e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b094e-115">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b094e-116">Procedura: creare un progetto di applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="b094e-116">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="b094e-117">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b094e-117">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
