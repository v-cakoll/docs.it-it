---
title: 'Procedura: visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form'
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
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b92fec7565aad2a881f714f9232eae10bf7633c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Procedura: visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form
Windows Form <xref:System.Windows.Forms.DateTimePicker> controllo offre flessibilità nella formattazione la visualizzazione di date e ore nel controllo. Il <xref:System.Windows.Forms.DateTimePicker.Format%2A> proprietà consente di selezionare uno dei formati predefiniti elencati nella <xref:System.Windows.Forms.DateTimePickerFormat>. Se nessuna di esse soddisfa le proprie esigenze, è possibile creare un formato personalizzato utilizzando i caratteri di formato elencati <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Per visualizzare un formato personalizzato  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su `DateTimePickerFormat.Custom`.  
  
2.  Impostare il <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> proprietà in una stringa di formato.  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a>Per aggiungere testo del valore formattato  
  
1.  Utilizzare virgolette per racchiudere i caratteri che non sono un carattere di formato come "M" o un delimitatore come ":". Ad esempio, la stringa di formato riportato di seguito visualizza la data corrente con il formato "oggi: 05:30:31 venerdì 02 marzo 2012" in inglese (Stati Uniti) delle impostazioni cultura.  
  
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
  
     A seconda delle impostazioni cultura, qualsiasi carattere non racchiusi tra virgolette può essere modificato. Ad esempio, la stringa di formato precedente consente di visualizzare la data corrente con il formato "oggi: 05:30:31 venerdì 02 marzo 2012" in inglese (Stati Uniti) delle impostazioni cultura. Si noti che i primi due punti sono racchiuso tra virgolette singole, poiché non è progettato per essere un carattere di delimitazione, come in "hh". In un'altra lingua, il formato potrebbe essere visualizzato come "oggi: 05.30.31 venerdì 02 marzo 2012".  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
