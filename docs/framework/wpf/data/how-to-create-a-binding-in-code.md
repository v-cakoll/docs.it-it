---
title: 'Procedura: creare associazioni nel codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458854"
---
# <a name="how-to-create-a-binding-in-code"></a>Procedura: creare associazioni nel codice
Questo esempio illustra come creare e impostare un <xref:System.Windows.Data.Binding> nel codice.  
  
## <a name="example"></a>Esempio  
 La classe <xref:System.Windows.FrameworkElement> e la classe <xref:System.Windows.FrameworkContentElement> espongono entrambi un metodo di `SetBinding`. Se si associa un elemento che eredita una di queste classi, è possibile chiamare direttamente il metodo <xref:System.Windows.FrameworkElement.SetBinding%2A>.  
  
 Nell'esempio seguente viene creata una classe denominata, `MyData`, che contiene una proprietà denominata `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Nell'esempio seguente viene illustrato come creare un oggetto Binding per impostare l'origine dell'associazione.  Nell'esempio viene usato <xref:System.Windows.FrameworkElement.SetBinding%2A> per associare la proprietà <xref:System.Windows.Controls.TextBlock.Text%2A> di `myText`, ovvero un controllo <xref:System.Windows.Controls.TextBlock>, per `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Per l'esempio di codice completo, vedere [esempio di associazione di solo codice](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Anziché chiamare <xref:System.Windows.FrameworkElement.SetBinding%2A>, è possibile usare il metodo statico <xref:System.Windows.Data.BindingOperations.SetBinding%2A> della classe <xref:System.Windows.Data.BindingOperations>. Nell'esempio seguente viene chiamato <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anziché <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> per associare `myText` a `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
