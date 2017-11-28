---
title: 'Procedura: creare tasti di scelta per i controlli Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af4cbcc5dacc4f9a0b5312b67838479bf6817228
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="7c265-102">Procedura: creare tasti di scelta per i controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="7c265-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="7c265-103">Un *chiave di accesso* è un carattere di sottolineato nel testo dell'etichetta di un controllo, ad esempio un pulsante, voce di menu o un menu.</span><span class="sxs-lookup"><span data-stu-id="7c265-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="7c265-104">Con una chiave di accesso, l'utente può "fare clic su" un pulsante da premendo il tasto ALT in combinazione con la chiave di accesso predefinito.</span><span class="sxs-lookup"><span data-stu-id="7c265-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="7c265-105">Ad esempio, se un pulsante viene eseguita una procedura per stampare un form e pertanto il relativo `Text` proprietà è impostata su "Print", aggiungendo una e commerciale prima della lettera "P", la lettera "P" essere sottolineati nel testo del pulsante in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7c265-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="7c265-106">L'utente può eseguire il comando associato al pulsante premendo ALT + P.</span><span class="sxs-lookup"><span data-stu-id="7c265-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="7c265-107">È possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="7c265-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="7c265-108">Per creare una chiave di accesso per un controllo</span><span class="sxs-lookup"><span data-stu-id="7c265-108">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="7c265-109">Impostare il `Text` proprietà in una stringa che include una e commerciale (&) prima della lettera che sarà il collegamento.</span><span class="sxs-lookup"><span data-stu-id="7c265-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="7c265-110">Per includere una e commerciale in una didascalia senza creare una chiave di accesso, inserire due caratteri e commerciale (& &).</span><span class="sxs-lookup"><span data-stu-id="7c265-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="7c265-111">Una singola e commerciale viene visualizzata nella barra del titolo e nessun carattere sottolineato.</span><span class="sxs-lookup"><span data-stu-id="7c265-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c265-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c265-112">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="7c265-113">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7c265-113">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="7c265-114">Procedura: Impostare il testo visualizzato da un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="7c265-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="7c265-115">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="7c265-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
