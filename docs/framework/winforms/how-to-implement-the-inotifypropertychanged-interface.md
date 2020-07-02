---
title: "Procedura: Implementare l'interfaccia INotifyPropertyChanged"
description: Informazioni su come implementare l'interfaccia INotifyPropertyChanged sugli oggetti business utilizzati in Windows Forms data binding.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 83d2ef32787d2dbcd877bc77dcede10111098f8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619268"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Procedura: Implementare l'interfaccia INotifyPropertyChanged
Nell'esempio di codice riportato di seguito viene illustrato come implementare l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia. Implementare questa interfaccia negli oggetti business utilizzati in Windows Forms data binding. Quando viene implementato, l'interfaccia comunica a un controllo associato la proprietà viene modificata in un oggetto business.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Applicare il modello PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)
- [Data binding di Windows Form](windows-forms-data-binding.md)
- [Procedura: generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md)
- [Notifica delle modifiche nell'associazione dati dei Windows Form](change-notification-in-windows-forms-data-binding.md)
