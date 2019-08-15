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
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039514"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="12e7f-102">Procedura: Creare tasti di scelta per i controlli Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="12e7f-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="12e7f-103">Una *chiave di accesso* è un carattere sottolineato nel testo di un menu, di una voce di menu o dell'etichetta di un controllo, ad esempio un pulsante.</span><span class="sxs-lookup"><span data-stu-id="12e7f-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="12e7f-104">Consente all'utente di fare clic su un pulsante premendo ALT in combinazione con il tasto di accesso predefinito.</span><span class="sxs-lookup"><span data-stu-id="12e7f-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="12e7f-105">Se, ad esempio, un pulsante esegue una procedura per stampare un form e pertanto la `Text` relativa proprietà è impostata su "stampa", l'aggiunta di una e commerciale (&) prima della lettera "p" causa la sottolineatura della lettera "p" nel testo del pulsante in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12e7f-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="12e7f-106">L'utente può eseguire il comando associato al pulsante premendo ALT + P.</span><span class="sxs-lookup"><span data-stu-id="12e7f-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="12e7f-107">Non è possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="12e7f-107">You cannot have an access key for a control that cannot receive focus.</span></span>

## <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="12e7f-108">Per creare una chiave di accesso per un controllo</span><span class="sxs-lookup"><span data-stu-id="12e7f-108">To create an access key for a control</span></span>

1. <span data-ttu-id="12e7f-109">Nella finestra **Proprietà** impostare la `Text` proprietà su una stringa che include una e commerciale (&) prima della lettera che sarà il tasto di accesso.</span><span class="sxs-lookup"><span data-stu-id="12e7f-109">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="12e7f-110">Per impostare, ad esempio, la lettera "P" come chiave di accesso, digitare **& stampa** nella griglia.</span><span class="sxs-lookup"><span data-stu-id="12e7f-110">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>

## <a name="see-also"></a><span data-ttu-id="12e7f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12e7f-111">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="12e7f-112">Procedura: Rispondi a Windows Forms clic sui pulsanti</span><span class="sxs-lookup"><span data-stu-id="12e7f-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="12e7f-113">Procedura: Imposta il testo visualizzato da un controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12e7f-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="12e7f-114">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="12e7f-114">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
