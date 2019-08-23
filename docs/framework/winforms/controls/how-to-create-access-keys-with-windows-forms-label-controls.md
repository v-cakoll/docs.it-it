---
title: 'Procedura: Creare tasti di scelta con i controlli Label di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: dd7f238f8c20ba990158f23344e36376d3b1cb7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950530"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="9e272-102">Procedura: Creare tasti di scelta con i controlli Label di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e272-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="9e272-103">È <xref:System.Windows.Forms.Label> possibile utilizzare i controlli Windows Forms per definire le chiavi di accesso per altri controlli.</span><span class="sxs-lookup"><span data-stu-id="9e272-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="9e272-104">Quando si definisce una chiave di accesso in un controllo etichetta, l'utente può premere il tasto ALT più il carattere designato per spostare lo stato attivo sul controllo che lo segue nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="9e272-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="9e272-105">Poiché le etichette non possono ricevere lo stato attivo, lo stato attivo passa automaticamente al controllo successivo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="9e272-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="9e272-106">Usare questa tecnica per assegnare chiavi di accesso a caselle di testo, caselle combinate, caselle di riepilogo e griglie di dati.</span><span class="sxs-lookup"><span data-stu-id="9e272-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="9e272-107">Per assegnare una chiave di accesso a un controllo con un'etichetta</span><span class="sxs-lookup"><span data-stu-id="9e272-107">To assign an access key to a control with a label</span></span>  
  
1. <span data-ttu-id="9e272-108">Creare prima l'etichetta, quindi creare l'altro controllo.</span><span class="sxs-lookup"><span data-stu-id="9e272-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="9e272-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="9e272-109">-or-</span></span>  
  
     <span data-ttu-id="9e272-110">Creare i controlli in qualsiasi ordine e impostare la <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà dell'etichetta su uno minore dell'altro controllo.</span><span class="sxs-lookup"><span data-stu-id="9e272-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2. <span data-ttu-id="9e272-111">Impostare la <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà dell'etichetta su `true`.</span><span class="sxs-lookup"><span data-stu-id="9e272-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="9e272-112">Usare una e commerciale (&) nella <xref:System.Windows.Forms.Label.Text%2A> proprietà dell'etichetta per assegnare la chiave di accesso per l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="9e272-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="9e272-113">Per ulteriori informazioni, vedere [creazione di chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="9e272-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9e272-114">È possibile che si desideri visualizzare le e commerciali in un controllo etichetta, anziché usarle per creare chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="9e272-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="9e272-115">Questo problema può verificarsi se si associa un controllo Label a un campo in un recordset in cui i dati includono le e commerciali.</span><span class="sxs-lookup"><span data-stu-id="9e272-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="9e272-116">Per visualizzare le e commerciali in un controllo Label, impostare <xref:System.Windows.Forms.Label.UseMnemonic%2A> la proprietà `false`su.</span><span class="sxs-lookup"><span data-stu-id="9e272-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="9e272-117">Se si desidera visualizzare le e commerciali e avere anche una chiave di accesso, impostare <xref:System.Windows.Forms.Label.UseMnemonic%2A> la proprietà `true` su e indicare la chiave di accesso con una e commerciale (&) e la e commerciale da visualizzare con due e commerciali.</span><span class="sxs-lookup"><span data-stu-id="9e272-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9e272-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e272-118">See also</span></span>

- [<span data-ttu-id="9e272-119">Procedura: Ridimensionare un controllo etichetta Windows Forms per adattarne il contenuto</span><span class="sxs-lookup"><span data-stu-id="9e272-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="9e272-120">Panoramica sul controllo Label</span><span class="sxs-lookup"><span data-stu-id="9e272-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="9e272-121">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="9e272-121">Label Control</span></span>](label-control-windows-forms.md)
