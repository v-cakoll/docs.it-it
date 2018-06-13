---
title: 'Procedura: associare un controllo ListBox ai dati'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 186d25750c5ce196a5e46c02f0f56e2440ea3a25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552831"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="c55ca-102">Procedura: associare un controllo ListBox ai dati</span><span class="sxs-lookup"><span data-stu-id="c55ca-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="c55ca-103">Uno sviluppatore di applicazioni può creare <xref:System.Windows.Controls.ListBox> controlli senza specificare il contenuto di ciascuna <xref:System.Windows.Controls.ListBoxItem> separatamente.</span><span class="sxs-lookup"><span data-stu-id="c55ca-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="c55ca-104">È possibile utilizzare l'associazione dati per associare i dati per i singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="c55ca-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="c55ca-105">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.ListBox> che popola la <xref:System.Windows.Controls.ListBoxItem> elementi utilizzando l'associazione dati a un'origine dati denominata *colori*.</span><span class="sxs-lookup"><span data-stu-id="c55ca-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="c55ca-106">In questo caso non è necessario utilizzare <xref:System.Windows.Controls.ListBoxItem> tag per specificare il contenuto di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="c55ca-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c55ca-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c55ca-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c55ca-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c55ca-108">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [<span data-ttu-id="c55ca-109">Controlli</span><span class="sxs-lookup"><span data-stu-id="c55ca-109">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
