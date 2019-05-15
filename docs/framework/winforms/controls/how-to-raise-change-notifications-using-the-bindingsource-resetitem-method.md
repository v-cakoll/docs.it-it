---
title: 'Procedura: Generare notifiche di modifica usando il metodo ResetItem di BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: 39beb5c7162fb01a51360330216687c158ff433c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583706"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="e4b2d-102">Procedura: Generare notifiche di modifica usando il metodo ResetItem di BindingSource</span><span class="sxs-lookup"><span data-stu-id="e4b2d-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="e4b2d-103">Alcune origini dati dei controlli non generano notifiche di modifica quando si verificano modifiche, aggiunte o eliminazioni di elementi.</span><span class="sxs-lookup"><span data-stu-id="e4b2d-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="e4b2d-104">Il componente <xref:System.Windows.Forms.BindingSource> consente di eseguire l'associazione a tali origini dati e di generare una notifica di modifica dal codice.</span><span class="sxs-lookup"><span data-stu-id="e4b2d-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4b2d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4b2d-105">Example</span></span>  
 <span data-ttu-id="e4b2d-106">Questo form illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per associare un elenco a un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e4b2d-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e4b2d-107">Poiché l'elenco non genera notifiche di modifica, quando un elemento dell'elenco subisce una modifica viene chiamato il metodo <xref:System.Windows.Forms.BindingSource.ResetItem%2A> dell'elemento <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="e4b2d-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="e4b2d-108">.</span><span class="sxs-lookup"><span data-stu-id="e4b2d-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4b2d-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e4b2d-109">Compiling the Code</span></span>  
 <span data-ttu-id="e4b2d-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4b2d-110">This example requires:</span></span>  
  
- <span data-ttu-id="e4b2d-111">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e4b2d-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b2d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4b2d-112">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="e4b2d-113">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="e4b2d-113">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="e4b2d-114">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="e4b2d-114">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
