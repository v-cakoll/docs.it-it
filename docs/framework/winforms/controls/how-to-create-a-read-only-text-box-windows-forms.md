---
title: 'Procedura: creare una casella di testo in sola lettura'
description: Informazioni sulla trasformazione di una casella di testo Windows Forms modificabile in una casella di testo Windows Forms di sola lettura.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619364"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="4d694-103">Procedura: creare una casella di testo in sola lettura (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="4d694-103">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="4d694-104">È possibile trasformare una casella di testo Windows Forms modificabile in un controllo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4d694-104">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="4d694-105">Ad esempio, nella casella di testo può essere visualizzato un valore che in genere è stato modificato, ma che potrebbe non essere attualmente, a causa dello stato dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d694-105">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="4d694-106">Per creare una casella di testo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="4d694-106">To create a read-only text box</span></span>

1. <span data-ttu-id="4d694-107">Impostare la <xref:System.Windows.Forms.TextBox> proprietà del controllo <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> su `true` .</span><span class="sxs-lookup"><span data-stu-id="4d694-107">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="4d694-108">Con la proprietà impostata su `true` , gli utenti possono ancora scorrere ed evidenziare il testo in una casella di testo senza consentire le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4d694-108">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="4d694-109">Un comando **Copy** è funzionante in una casella di testo, ma i comandi **taglia** e **Incolla** non lo sono.</span><span class="sxs-lookup"><span data-stu-id="4d694-109">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4d694-110">La <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà influiscono solo sull'interazione dell'utente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4d694-110">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="4d694-111">È comunque possibile modificare il contenuto della casella di testo a livello di codice in fase di esecuzione modificando la <xref:System.Windows.Forms.TextBox.Text%2A> proprietà della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="4d694-111">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d694-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d694-112">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4d694-113">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="4d694-113">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4d694-114">Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="4d694-114">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d694-115">Procedura: creare una casella di testo Password con il controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="4d694-115">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d694-116">Procedura: inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="4d694-116">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4d694-117">Procedura: selezionare testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="4d694-117">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d694-118">Procedura: visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="4d694-118">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d694-119">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="4d694-119">TextBox Control</span></span>](textbox-control-windows-forms.md)
