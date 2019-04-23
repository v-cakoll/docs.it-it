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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225599"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="5abb6-102">Procedura: Implementare l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="5abb6-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="5abb6-103">Esempio di codice seguente viene illustrato come implementare il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5abb6-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="5abb6-104">Implementare questa interfaccia per gli oggetti business utilizzati nel data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="5abb6-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="5abb6-105">Quando implementato, l'interfaccia comunica a un controllo associato le modifiche alle proprietà in un oggetto business.</span><span class="sxs-lookup"><span data-stu-id="5abb6-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5abb6-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5abb6-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5abb6-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5abb6-107">See also</span></span>

- [<span data-ttu-id="5abb6-108">Procedura: Applicare il modello PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="5abb6-108">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="5abb6-109">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5abb6-109">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="5abb6-110">Procedura: Generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="5abb6-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="5abb6-111">Notifica delle modifiche nel data binding dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="5abb6-111">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
