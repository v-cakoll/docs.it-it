---
title: 'Procedura: creare associazioni nel codice'
description: Informazioni su come creare un'associazione nel codice in un'applicazione Windows Presentation Foundation chiamando direttamente il metodo SetBinding.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165812"
---
# <a name="how-to-create-a-binding-in-code"></a>Procedura: creare associazioni nel codice
Questo esempio illustra come creare e impostare un oggetto <xref:System.Windows.Data.Binding> nel codice.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.FrameworkElement> classe e la <xref:System.Windows.FrameworkContentElement> classe espongono entrambi un `SetBinding` metodo. Se si associa un elemento che eredita una di queste classi, è possibile chiamare direttamente il <xref:System.Windows.FrameworkElement.SetBinding%2A> metodo.  
  
 Nell'esempio seguente viene creata una classe denominata, `MyData` , che contiene una proprietà denominata `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Nell'esempio seguente viene illustrato come creare un oggetto Binding per impostare l'origine dell'associazione.  Nell'esempio viene usato <xref:System.Windows.FrameworkElement.SetBinding%2A> per associare la <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà di `myText` , che è un <xref:System.Windows.Controls.TextBlock> controllo, a `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Per l'esempio di codice completo, vedere [esempio di associazione di solo codice](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Anziché chiamare <xref:System.Windows.FrameworkElement.SetBinding%2A> , è possibile usare il <xref:System.Windows.Data.BindingOperations.SetBinding%2A> metodo statico della <xref:System.Windows.Data.BindingOperations> classe. Nell'esempio seguente viene chiamato il comando <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anziché <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> per eseguire l'associazione `myText` a `myDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative](data-binding-how-to-topics.md)
