---
title: 'Procedura: implementare notifiche di modifiche alle proprietà'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: a9c0fb433e2fa65e28db3b793e038b49f9d6353b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555990"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="f85bc-102">Procedura: implementare notifiche di modifiche alle proprietà</span><span class="sxs-lookup"><span data-stu-id="f85bc-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="f85bc-103">Per supportare <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> binding per abilitare le proprietà di destinazione di associazione in modo da riflettere automaticamente le modifiche dinamiche dell'origine di associazione (ad esempio, per il riquadro di anteprima aggiornata automaticamente quando l'utente modifica un form), la classe deve fornire le notifiche di modifica delle proprietà appropriata.</span><span class="sxs-lookup"><span data-stu-id="f85bc-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="f85bc-104">In questo esempio viene illustrato come creare una classe che implementa <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="f85bc-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f85bc-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f85bc-105">Example</span></span>  
 <span data-ttu-id="f85bc-106">Per implementare <xref:System.ComponentModel.INotifyPropertyChanged> è necessario dichiarare il <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> evento e creare il `OnPropertyChanged` metodo.</span><span class="sxs-lookup"><span data-stu-id="f85bc-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="f85bc-107">Quindi, per ogni proprietà per cui si desidera ricevere notifiche per le modifiche, chiamare `OnPropertyChanged` ogni volta che la proprietà viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="f85bc-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="f85bc-108">Per vedere un esempio di utilizzo del `Person` classe può essere utilizzata per supportare <xref:System.Windows.Data.BindingMode.TwoWay> binding, vedere [controllare quando il testo della casella di testo Aggiorna l'origine](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="f85bc-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85bc-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f85bc-109">See Also</span></span>  
 [<span data-ttu-id="f85bc-110">Panoramica delle origini di associazione</span><span class="sxs-lookup"><span data-stu-id="f85bc-110">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="f85bc-111">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="f85bc-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f85bc-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="f85bc-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
