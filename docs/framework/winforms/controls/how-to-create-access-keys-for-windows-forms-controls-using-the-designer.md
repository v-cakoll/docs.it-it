---
title: 'Procedura: Creare tasti di scelta per i controlli Windows Forms usando la finestra di progettazione'
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
ms.openlocfilehash: 410fc0134046c5fa7e05bfcd38ce6818244a0a54
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307873"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="1321f-102">Procedura: Creare tasti di scelta per i controlli Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1321f-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="1321f-103">Un' *chiave di accesso* è un carattere di sottolineato nel testo di un menu, voce di menu o l'etichetta di un controllo, ad esempio un pulsante.</span><span class="sxs-lookup"><span data-stu-id="1321f-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="1321f-104">Consente all'utente di "fare clic su" un pulsante premendo il tasto ALT in combinazione con la chiave di accesso predefinite.</span><span class="sxs-lookup"><span data-stu-id="1321f-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="1321f-105">Ad esempio, se un pulsante viene eseguita una procedura per stampare un form e pertanto relativo `Text` proprietà è impostata su "Stampa", aggiungendo una e commerciale (&) prima della lettera "P", la lettera "P" per essere sottolineati nel testo del pulsante in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1321f-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="1321f-106">L'utente può eseguire il comando associato al pulsante premendo ALT + P.</span><span class="sxs-lookup"><span data-stu-id="1321f-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="1321f-107">Non è possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="1321f-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1321f-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="1321f-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1321f-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="1321f-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1321f-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1321f-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="1321f-111">Per creare una chiave di accesso per un controllo</span><span class="sxs-lookup"><span data-stu-id="1321f-111">To create an access key for a control</span></span>  
  
1. <span data-ttu-id="1321f-112">Nel **delle proprietà** impostare nella finestra di `Text` proprietà in una stringa che include una e commerciale (&) alla lettera che sarà la chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="1321f-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="1321f-113">Ad esempio, per impostare la lettera "P" come chiave di accesso, digitare **conf** nella griglia.</span><span class="sxs-lookup"><span data-stu-id="1321f-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1321f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1321f-114">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="1321f-115">Procedura: Rispondere alla selezione dei pulsanti Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1321f-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="1321f-116">Procedura: Impostare il testo visualizzato da un controllo di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1321f-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="1321f-117">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="1321f-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
