---
title: 'Procedura: implementare notifiche di modifiche alle proprietà'
description: Abilitare le proprietà per notificare automaticamente un'origine di binding quando il valore della proprietà viene modificato in Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: 6c298930b7b1f812e94ea6add8f53c67d3453530
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620781"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="fb8c9-103">Procedura: implementare notifiche di modifiche alle proprietà</span><span class="sxs-lookup"><span data-stu-id="fb8c9-103">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="fb8c9-104">Per supportare <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> associare per consentire alle proprietà della destinazione del binding di riflettere automaticamente le modifiche dinamiche dell'origine del binding, ad esempio per fare in modo che il riquadro di anteprima venga aggiornato automaticamente quando l'utente modifica un modulo, la classe deve fornire le notifiche appropriate per la modifica delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-104">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="fb8c9-105">Questo esempio illustra come creare una classe che implementa <xref:System.ComponentModel.INotifyPropertyChanged> .</span><span class="sxs-lookup"><span data-stu-id="fb8c9-105">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb8c9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb8c9-106">Example</span></span>  
 <span data-ttu-id="fb8c9-107">Per implementare <xref:System.ComponentModel.INotifyPropertyChanged> è necessario dichiarare l' <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> evento e creare il `OnPropertyChanged` metodo.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-107">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="fb8c9-108">Quindi, per ogni proprietà per cui si desidera ricevere notifiche per le modifiche, chiamare `OnPropertyChanged` ogni volta che la proprietà viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-108">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="fb8c9-109">Per un esempio di come `Person` è possibile usare la classe per supportare l' <xref:System.Windows.Data.BindingMode.TwoWay> associazione, vedere [controllo quando il testo della casella di testo aggiorna l'origine](how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="fb8c9-109">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb8c9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb8c9-110">See also</span></span>

- [<span data-ttu-id="fb8c9-111">Cenni preliminari sulle origini del binding</span><span class="sxs-lookup"><span data-stu-id="fb8c9-111">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="fb8c9-112">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="fb8c9-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="fb8c9-113">Procedure</span><span class="sxs-lookup"><span data-stu-id="fb8c9-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
