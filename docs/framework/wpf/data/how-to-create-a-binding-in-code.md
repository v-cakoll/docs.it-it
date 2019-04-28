---
title: 'Procedura: Creare un binding nel codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 57ec845c5c9a5bddb801428b9ecde035a97cf447
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931625"
---
# <a name="how-to-create-a-binding-in-code"></a>Procedura: Creare un binding nel codice
Questo esempio illustra come creare e impostare un <xref:System.Windows.Data.Binding> nel codice.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.FrameworkElement> classe e il <xref:System.Windows.FrameworkContentElement> classe espongono entrambi una `SetBinding` (metodo). Se si associa un elemento che eredita da una di queste classi, è possibile chiamare il <xref:System.Windows.FrameworkElement.SetBinding%2A> direttamente al metodo.  
  
 L'esempio seguente crea una classe denominata `MyData`, che contiene una proprietà denominata `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Nell'esempio seguente viene illustrato come creare un oggetto di associazione per impostare l'origine dell'associazione.  Nell'esempio viene usato <xref:System.Windows.FrameworkElement.SetBinding%2A> per associare il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà di `myText`, che è un <xref:System.Windows.Controls.TextBlock> a controllare `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Per l'esempio di codice completo, vedere [esempio di associazione di solo codice](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Invece di chiamare <xref:System.Windows.FrameworkElement.SetBinding%2A>, è possibile usare il <xref:System.Windows.Data.BindingOperations.SetBinding%2A> metodo statico del <xref:System.Windows.Data.BindingOperations> classe. L'esempio seguente, le chiamate <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> invece di <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> associare `myText` a `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
