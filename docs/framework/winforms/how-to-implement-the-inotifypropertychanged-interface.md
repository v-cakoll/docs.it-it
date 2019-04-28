---
title: "Procedura: Implementare l'interfaccia INotifyPropertyChanged"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: cfdfb22fd854a8f630243e0f612761c71cb778d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802037"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Procedura: Implementare l'interfaccia INotifyPropertyChanged
Esempio di codice seguente viene illustrato come implementare il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia. Implementare questa interfaccia per gli oggetti business utilizzati nel data binding in Windows Form. Quando implementato, l'interfaccia comunica a un controllo associato le modifiche alle proprietà in un oggetto business.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Applicare il modello PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)
- [Data binding in Windows Form](windows-forms-data-binding.md)
- [Procedura: Generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md)
- [Notifica delle modifiche nel data binding dei Windows Form](change-notification-in-windows-forms-data-binding.md)
