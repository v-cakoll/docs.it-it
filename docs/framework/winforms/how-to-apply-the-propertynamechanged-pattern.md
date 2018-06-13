---
title: 'Procedura: applicare il modello PropertyNameChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 775a27b1b4ba8143e297a3c4d323356a304073a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536746"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Procedura: applicare il modello PropertyNameChanged
Esempio di codice seguente viene illustrato come applicare il *PropertyName*modello Changed a un controllo personalizzato. Applicare questo modello quando si implementano controlli personalizzati che vengono utilizzati con il motore di associazione di dati di Windows Form.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare l'esempio di codice precedente:  
  
-   Incollare il codice in un file di codice vuoto. È necessario utilizzare il controllo personalizzato in un Windows Form che contiene un `Main` metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Implementare l'interfaccia INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [Notifica delle modifiche nel data binding dei Windows Form](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)
