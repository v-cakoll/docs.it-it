---
title: 'Procedura: aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form utilizzando Progettazione Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fdb57cf2134ee4f221a26db61cfdcc48dc92548
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="11fcf-102">Procedura: aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form utilizzando Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="11fcf-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="11fcf-103">Windows Form <xref:System.Windows.Forms.DataGridView> controllo deve contenere colonne per visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="11fcf-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="11fcf-104">Se si prevede di popolare il controllo manualmente, è necessario aggiungere le colonne.</span><span class="sxs-lookup"><span data-stu-id="11fcf-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="11fcf-105">In alternativa, è possibile associare il controllo a un'origine dati, che genera l'errore e popola le colonne automaticamente.</span><span class="sxs-lookup"><span data-stu-id="11fcf-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="11fcf-106">Se l'origine dati contiene più colonne che si desidera visualizzare, è possibile rimuovere le colonne non desiderate.</span><span class="sxs-lookup"><span data-stu-id="11fcf-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="11fcf-107">Le procedure seguenti richiedono un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="11fcf-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="11fcf-108">Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="11fcf-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11fcf-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="11fcf-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="11fcf-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="11fcf-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="11fcf-111">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="11fcf-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="11fcf-112">Per aggiungere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="11fcf-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="11fcf-113">Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="11fcf-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="11fcf-114">Nel **Aggiungi colonna** finestra di dialogo scegliere la **colonna associata ai dati** opzione e selezionare una colonna dall'origine dati o scegliere il **colonna non associata** opzione e definire la colonna utilizzando gli appositi campi.</span><span class="sxs-lookup"><span data-stu-id="11fcf-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="11fcf-115">Fare clic su di **Aggiungi** pulsante per aggiungere la colonna, che viene visualizzata nella finestra di progettazione se le colonne esistenti non occupano già l'area di visualizzazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="11fcf-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11fcf-116">È possibile modificare le proprietà di colonna nel **Modifica colonne** nella finestra di dialogo è possibile accedere da smart tag del controllo.</span><span class="sxs-lookup"><span data-stu-id="11fcf-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="11fcf-117">Per rimuovere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="11fcf-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="11fcf-118">Scegliere **Modifica colonne** da smart tag del controllo.</span><span class="sxs-lookup"><span data-stu-id="11fcf-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="11fcf-119">Selezionare una colonna dal **colonne selezionate** elenco.</span><span class="sxs-lookup"><span data-stu-id="11fcf-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="11fcf-120">Fare clic su di **rimuovere** pulsante per eliminare la colonna dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="11fcf-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11fcf-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11fcf-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="11fcf-122">Procedura: creare un progetto di applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="11fcf-122">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="11fcf-123">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11fcf-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
