---
title: 'Procedura: modificare il tipo di una colonna DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 020eca128300f964614423e3ce371c00cb437ffb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="0c2f5-102">Procedura: modificare il tipo di una colonna DataGridView di Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0c2f5-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="0c2f5-103">In alcuni casi è possibile modificare il tipo di una colonna che è già stato aggiunto a un Windows Form <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0c2f5-104">Potrebbe ad esempio, si desidera modificare i tipi di alcune delle colonne che vengono generate automaticamente quando si associa il controllo a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="0c2f5-105">Ciò è utile quando la tabella visualizzata contiene le colonne che contengono chiavi esterne alle righe in una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="0c2f5-106">In questo caso, è consigliabile sostituire le colonne della casella di testo che consentono di visualizzare le chiavi esterne con le colonne di casella combinata che visualizza valori più significativi della tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="0c2f5-107">La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0c2f5-108">Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0c2f5-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c2f5-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0c2f5-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="0c2f5-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0c2f5-111">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0c2f5-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="0c2f5-112">Per modificare il tipo di una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0c2f5-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="0c2f5-113">Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="0c2f5-114">Selezionare una colonna dal **colonne selezionate** elenco.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="0c2f5-115">Nel **proprietà colonna** griglia, impostare il `ColumnType` proprietà per il nuovo tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c2f5-116">Il `ColumnType` proprietà è una proprietà solo nella fase di progettazione che indica la classe che rappresenta il tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="0c2f5-117">Non è una proprietà effettiva, definita in una classe di colonna.</span><span class="sxs-lookup"><span data-stu-id="0c2f5-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c2f5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c2f5-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="0c2f5-119">Procedura: creare un progetto di applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="0c2f5-119">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="0c2f5-120">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c2f5-120">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
