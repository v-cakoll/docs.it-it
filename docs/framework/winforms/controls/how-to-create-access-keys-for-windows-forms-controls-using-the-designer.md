---
title: 'Procedura: creare tasti di scelta per i controlli di Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 023973e7fa4ab1e8b802d8c7cd8abef8201ed720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532551"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="5b540-102">Procedura: creare tasti di scelta per i controlli di Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="5b540-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="5b540-103">Un *chiave di accesso* è un carattere di sottolineato nel testo dell'etichetta di un controllo, ad esempio un pulsante, voce di menu o un menu.</span><span class="sxs-lookup"><span data-stu-id="5b540-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="5b540-104">Consente all'utente di "fare clic su" un pulsante da premendo il tasto ALT in combinazione con la chiave di accesso predefinito.</span><span class="sxs-lookup"><span data-stu-id="5b540-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="5b540-105">Ad esempio, se un pulsante viene eseguita una procedura per stampare un form e pertanto il relativo `Text` proprietà è impostata su "Stampa", aggiungendo una e commerciale (&) prima della lettera "P", la lettera "P" essere sottolineati nel testo del pulsante in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5b540-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="5b540-106">L'utente può eseguire il comando associato al pulsante premendo ALT + P.</span><span class="sxs-lookup"><span data-stu-id="5b540-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="5b540-107">È possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="5b540-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b540-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="5b540-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5b540-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="5b540-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5b540-110">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5b540-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="5b540-111">Per creare una chiave di accesso per un controllo</span><span class="sxs-lookup"><span data-stu-id="5b540-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="5b540-112">Nel **proprietà** finestra, impostare il `Text` proprietà in una stringa che include una e commerciale (&) prima della lettera che verrà utilizzato come chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="5b540-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="5b540-113">Ad esempio, per impostare la lettera "P" come tasto di scelta rapida, digitare **& stampa** nella griglia.</span><span class="sxs-lookup"><span data-stu-id="5b540-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b540-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b540-114">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="5b540-115">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b540-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="5b540-116">Procedura: Impostare il testo visualizzato da un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b540-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="5b540-117">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="5b540-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
