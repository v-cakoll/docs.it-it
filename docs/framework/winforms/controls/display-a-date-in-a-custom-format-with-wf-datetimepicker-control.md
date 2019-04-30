---
title: 'Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: 08d5a505229cd434dbf82e8ae4624bb418efd379
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972165"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="189fd-102">Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="189fd-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="189fd-103">I moduli di Windows <xref:System.Windows.Forms.DateTimePicker> controllo ti offre flessibilità nella formattazione la visualizzazione di date e ore nel controllo.</span><span class="sxs-lookup"><span data-stu-id="189fd-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="189fd-104">Il <xref:System.Windows.Forms.DateTimePicker.Format%2A> proprietà consente di selezionare uno dei formati predefiniti elencati nella <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="189fd-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="189fd-105">Se nessuna di esse è adeguata alle proprie esigenze, è possibile creare il proprio stile di formattazione usando caratteri di formattazione elencati nella <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="189fd-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="189fd-106">Per visualizzare un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="189fd-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="189fd-107">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="189fd-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="189fd-108">Impostare il <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> proprietà da una stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="189fd-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="189fd-109">Per aggiungere testo al valore formattato</span><span class="sxs-lookup"><span data-stu-id="189fd-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="189fd-110">Usare virgolette singole per racchiudere i caratteri che non sono un carattere di formato, ad esempio "M" o un delimitatore, ad esempio ":".</span><span class="sxs-lookup"><span data-stu-id="189fd-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="189fd-111">Ad esempio, la stringa di formato riportato di seguito visualizza la data corrente nel formato "oggi è: 05:30:31 marzo venerdì 02, 2012" nelle impostazioni cultura inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="189fd-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="189fd-112">A seconda dell'impostazione cultura, i caratteri non racchiusi tra virgolette singole possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="189fd-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="189fd-113">Ad esempio, la stringa di formato precedente visualizza la data corrente nel formato "oggi è: 05:30:31 marzo venerdì 02, 2012" nelle impostazioni cultura inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="189fd-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="189fd-114">Si noti che i primi due punti sono racchiuso tra virgolette singole, poiché non è destinato a essere un carattere di delimitazione perché è "hh".</span><span class="sxs-lookup"><span data-stu-id="189fd-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="189fd-115">In un'altra lingua, il formato potrebbe essere visualizzato come "oggi è: 05.30.31 venerdì marzo 2012" 02,.</span><span class="sxs-lookup"><span data-stu-id="189fd-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189fd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="189fd-116">See also</span></span>

- [<span data-ttu-id="189fd-117">Controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="189fd-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="189fd-118">Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Form</span><span class="sxs-lookup"><span data-stu-id="189fd-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
