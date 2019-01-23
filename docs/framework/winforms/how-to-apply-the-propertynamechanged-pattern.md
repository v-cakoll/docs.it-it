---
title: 'Procedura: Applicare il modello PropertyNameChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 82856405ab3c9581b398f358e5bf9ecf989ce193
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539766"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Procedura: Applicare il modello PropertyNameChanged
Esempio di codice seguente viene illustrato come applicare la *PropertyName*Changed pattern a un controllo personalizzato. Applicare questo modello quando si implementano controlli personalizzati che vengono usati con il motore di data binding di Windows Form.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare l'esempio di codice precedente:  
  
-   Incollare il codice in un file di codice vuoto. È necessario usare il controllo personalizzato in un Form Windows che contiene un `Main` (metodo).  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Implementare l'interfaccia INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)
- [Notifica delle modifiche nel data binding dei Windows Form](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
- [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)
