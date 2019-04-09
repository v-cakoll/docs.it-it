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
ms.openlocfilehash: 0c454580c6f3aa1fadb6e98d2ee715da948364b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192992"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.DateTimePicker> controllo ti offre flessibilità nella formattazione la visualizzazione di date e ore nel controllo. Il <xref:System.Windows.Forms.DateTimePicker.Format%2A> proprietà consente di selezionare uno dei formati predefiniti elencati nella <xref:System.Windows.Forms.DateTimePickerFormat>. Se nessuna di esse è adeguata alle proprie esigenze, è possibile creare il proprio stile di formattazione usando caratteri di formattazione elencati nella <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Per visualizzare un formato personalizzato  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su `DateTimePickerFormat.Custom`.  
  
2.  Impostare il <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> proprietà da una stringa di formato.  
  
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
  
1.  Usare virgolette singole per racchiudere i caratteri che non sono un carattere di formato, ad esempio "M" o un delimitatore, ad esempio ":". Ad esempio, la stringa di formato riportato di seguito visualizza la data corrente nel formato "oggi è: 05:30:31 marzo venerdì 02, 2012" nelle impostazioni cultura inglese (Stati Uniti).  
  
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
  
     A seconda dell'impostazione cultura, i caratteri non racchiusi tra virgolette singole possono essere modificati. Ad esempio, la stringa di formato precedente visualizza la data corrente nel formato "oggi è: 05:30:31 marzo venerdì 02, 2012" nelle impostazioni cultura inglese (Stati Uniti). Si noti che i primi due punti sono racchiuso tra virgolette singole, poiché non è destinato a essere un carattere di delimitazione perché è "hh". In un'altra lingua, il formato potrebbe essere visualizzato come "oggi è: 05.30.31 venerdì marzo 2012" 02,.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DateTimePicker](datetimepicker-control-windows-forms.md)
- [Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
