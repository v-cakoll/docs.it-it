---
title: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker
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
ms.openlocfilehash: a27dbe737b81af86c0ac50b791bcd87bafe05b4f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745942"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="2fd3c-102">Procedura: visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2fd3c-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="2fd3c-103">Il controllo Windows Forms <xref:System.Windows.Forms.DateTimePicker> offre la flessibilità necessaria per formattare la visualizzazione di date e ore nel controllo.</span><span class="sxs-lookup"><span data-stu-id="2fd3c-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="2fd3c-104">La proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> consente di effettuare una selezione da formati predefiniti, elencati nel <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="2fd3c-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="2fd3c-105">Se nessuno di questi è adatto ai propri scopi, è possibile creare uno stile di formato personalizzato utilizzando i caratteri di formato elencati in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fd3c-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="2fd3c-106">Per visualizzare un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="2fd3c-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="2fd3c-107">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="2fd3c-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="2fd3c-108">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> su una stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="2fd3c-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="2fd3c-109">Per aggiungere testo al valore formattato</span><span class="sxs-lookup"><span data-stu-id="2fd3c-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="2fd3c-110">Utilizzare le virgolette singole per racchiudere qualsiasi carattere che non sia un carattere di formato quale "M" o un delimitatore come ":".</span><span class="sxs-lookup"><span data-stu-id="2fd3c-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="2fd3c-111">La stringa di formato seguente, ad esempio, Visualizza la data corrente nel formato "Today is: 05:30:31 Friday March 02, 2012" nelle impostazioni cultura inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="2fd3c-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="2fd3c-112">A seconda delle impostazioni cultura, è possibile che eventuali caratteri non racchiusi tra virgolette singole vengano modificati.</span><span class="sxs-lookup"><span data-stu-id="2fd3c-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="2fd3c-113">La stringa di formato precedente, ad esempio, Visualizza la data corrente nel formato "Today is: 05:30:31 Friday March 02, 2012" nelle impostazioni cultura inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="2fd3c-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="2fd3c-114">Si noti che i primi due punti sono racchiusi tra virgolette singole, perché non è destinato a essere un carattere di delimitazione perché si trova in "HH: mm: SS".</span><span class="sxs-lookup"><span data-stu-id="2fd3c-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="2fd3c-115">In altre impostazioni cultura, il formato potrebbe essere "Today is: 05.30.31 Friday March 02, 2012".</span><span class="sxs-lookup"><span data-stu-id="2fd3c-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd3c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fd3c-116">See also</span></span>

- [<span data-ttu-id="2fd3c-117">Controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="2fd3c-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="2fd3c-118">Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2fd3c-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
