---
title: "Procedura: Personalizzare l'aggiunta di elementi con BindingSource di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: 59522791408eb9c8cabf97a62be2049aeb17f864
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935355"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="2526c-102">Procedura: Personalizzare l'aggiunta di elementi con BindingSource di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2526c-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="2526c-103">Quando si usa un componente <xref:System.Windows.Forms.BindingSource> per associare un controllo Windows Form a un'origine dati, potrebbe essere necessario personalizzare la creazione di nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="2526c-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="2526c-104">Il componente <xref:System.Windows.Forms.BindingSource> semplifica questa attività per mezzo dell'evento <xref:System.Windows.Forms.BindingSource.AddingNew> , che di solito viene generato quando il controllo associato deve creare un nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="2526c-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="2526c-105">Il gestore eventi può fornire qualsiasi comportamento personalizzato sia necessario (ad esempio, la chiamata a un metodo su un servizio Web o l'acquisizione di un nuovo oggetto da una class factory).</span><span class="sxs-lookup"><span data-stu-id="2526c-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2526c-106">Quando un elemento viene aggiunto gestendo l'evento <xref:System.Windows.Forms.BindingSource.AddingNew> , l'aggiunta non può essere annullata.</span><span class="sxs-lookup"><span data-stu-id="2526c-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2526c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2526c-107">Example</span></span>  
 <span data-ttu-id="2526c-108">Il seguente esempio mostra come associare un controllo <xref:System.Windows.Forms.DataGridView> a una class factory usando un componente <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="2526c-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="2526c-109">Quando l'utente fa clic sulla nuova riga del controllo <xref:System.Windows.Forms.DataGridView> , viene generato l'evento <xref:System.Windows.Forms.BindingSource.AddingNew> .</span><span class="sxs-lookup"><span data-stu-id="2526c-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="2526c-110">Il gestore eventi crea un nuovo oggetto `DemoCustomer`, che viene assegnato alla proprietà <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2526c-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2526c-111">In questo modo il nuovo oggetto `DemoCustomer` viene aggiunto all'elenco del componente <xref:System.Windows.Forms.BindingSource> e visualizzato nella nuova riga del controllo <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="2526c-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2526c-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2526c-112">Compiling the Code</span></span>  
 <span data-ttu-id="2526c-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2526c-113">This example requires:</span></span>  
  
- <span data-ttu-id="2526c-114">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2526c-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2526c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2526c-115">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="2526c-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="2526c-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="2526c-117">Procedura: Associare un controllo Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="2526c-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
