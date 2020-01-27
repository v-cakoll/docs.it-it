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
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Procedura: visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.DateTimePicker> offre la flessibilità necessaria per formattare la visualizzazione di date e ore nel controllo. La proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> consente di effettuare una selezione da formati predefiniti, elencati nel <xref:System.Windows.Forms.DateTimePickerFormat>. Se nessuno di questi è adatto ai propri scopi, è possibile creare uno stile di formato personalizzato utilizzando i caratteri di formato elencati in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Per visualizzare un formato personalizzato  
  
1. Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su `DateTimePickerFormat.Custom`.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> su una stringa di formato.  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a>Per aggiungere testo al valore formattato  
  
1. Utilizzare le virgolette singole per racchiudere qualsiasi carattere che non sia un carattere di formato quale "M" o un delimitatore come ":". La stringa di formato seguente, ad esempio, Visualizza la data corrente nel formato "Today is: 05:30:31 Friday March 02, 2012" nelle impostazioni cultura inglese (Stati Uniti).  
  
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
  
     A seconda delle impostazioni cultura, è possibile che eventuali caratteri non racchiusi tra virgolette singole vengano modificati. La stringa di formato precedente, ad esempio, Visualizza la data corrente nel formato "Today is: 05:30:31 Friday March 02, 2012" nelle impostazioni cultura inglese (Stati Uniti). Si noti che i primi due punti sono racchiusi tra virgolette singole, perché non è destinato a essere un carattere di delimitazione perché si trova in "HH: mm: SS". In altre impostazioni cultura, il formato potrebbe essere "Today is: 05.30.31 Friday March 02, 2012".  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DateTimePicker](datetimepicker-control-windows-forms.md)
- [Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Form](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
