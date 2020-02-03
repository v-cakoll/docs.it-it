---
title: Creare chiavi di accesso con controlli Label
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
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731055"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="d35f8-102">Procedura: creare tasti di scelta con i controlli Label di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d35f8-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="d35f8-103">È possibile utilizzare i controlli <xref:System.Windows.Forms.Label> Windows Forms per definire le chiavi di accesso per altri controlli.</span><span class="sxs-lookup"><span data-stu-id="d35f8-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="d35f8-104">Quando si definisce una chiave di accesso in un controllo etichetta, l'utente può premere il tasto ALT più il carattere designato per spostare lo stato attivo sul controllo che lo segue nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="d35f8-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="d35f8-105">Poiché le etichette non possono ricevere lo stato attivo, lo stato attivo passa automaticamente al controllo successivo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="d35f8-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="d35f8-106">Usare questa tecnica per assegnare chiavi di accesso a caselle di testo, caselle combinate, caselle di riepilogo e griglie di dati.</span><span class="sxs-lookup"><span data-stu-id="d35f8-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="d35f8-107">Per assegnare una chiave di accesso a un controllo con un'etichetta</span><span class="sxs-lookup"><span data-stu-id="d35f8-107">To assign an access key to a control with a label</span></span>  
  
1. <span data-ttu-id="d35f8-108">Creare prima l'etichetta, quindi creare l'altro controllo.</span><span class="sxs-lookup"><span data-stu-id="d35f8-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="d35f8-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d35f8-109">-or-</span></span>  
  
     <span data-ttu-id="d35f8-110">È possibile creare i controlli in qualsiasi ordine e impostare la proprietà <xref:System.Windows.Forms.Control.TabIndex%2A> dell'etichetta su uno minore dell'altro controllo.</span><span class="sxs-lookup"><span data-stu-id="d35f8-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2. <span data-ttu-id="d35f8-111">Impostare la proprietà <xref:System.Windows.Forms.Label.UseMnemonic%2A> dell'etichetta su `true`.</span><span class="sxs-lookup"><span data-stu-id="d35f8-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="d35f8-112">Usare una e commerciale (&) nella proprietà <xref:System.Windows.Forms.Label.Text%2A> dell'etichetta per assegnare la chiave di accesso per l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="d35f8-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="d35f8-113">Per ulteriori informazioni, vedere [creazione di chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d35f8-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d35f8-114">È possibile che si desideri visualizzare le e commerciali in un controllo etichetta, anziché usarle per creare chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="d35f8-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="d35f8-115">Questo problema può verificarsi se si associa un controllo Label a un campo in un recordset in cui i dati includono le e commerciali.</span><span class="sxs-lookup"><span data-stu-id="d35f8-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="d35f8-116">Per visualizzare le e commerciali in un controllo Label, impostare la proprietà <xref:System.Windows.Forms.Label.UseMnemonic%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="d35f8-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="d35f8-117">Se si desidera visualizzare le e commerciali e avere anche una chiave di accesso, impostare la proprietà <xref:System.Windows.Forms.Label.UseMnemonic%2A> su `true` e indicare la chiave di accesso con una e commerciale (&) e la e commerciale da visualizzare con due e commerciale.</span><span class="sxs-lookup"><span data-stu-id="d35f8-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d35f8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d35f8-118">See also</span></span>

- [<span data-ttu-id="d35f8-119">Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="d35f8-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="d35f8-120">Panoramica sul controllo Label</span><span class="sxs-lookup"><span data-stu-id="d35f8-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="d35f8-121">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="d35f8-121">Label Control</span></span>](label-control-windows-forms.md)
