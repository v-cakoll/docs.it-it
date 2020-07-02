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
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="6bc5e-103">Procedura: Implementare l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="6bc5e-103">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="6bc5e-104">Nell'esempio di codice riportato di seguito viene illustrato come implementare l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6bc5e-104">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="6bc5e-105">Implementare questa interfaccia negli oggetti business utilizzati in Windows Forms data binding.</span><span class="sxs-lookup"><span data-stu-id="6bc5e-105">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="6bc5e-106">Quando viene implementato, l'interfaccia comunica a un controllo associato la proprietà viene modificata in un oggetto business.</span><span class="sxs-lookup"><span data-stu-id="6bc5e-106">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bc5e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="6bc5e-107">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6bc5e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bc5e-108">See also</span></span>

- [<span data-ttu-id="6bc5e-109">Procedura: Applicare il modello PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="6bc5e-109">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="6bc5e-110">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6bc5e-110">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="6bc5e-111">Procedura: generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="6bc5e-111">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="6bc5e-112">Notifica delle modifiche nell'associazione dati dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="6bc5e-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
