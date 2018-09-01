---
title: "Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: 7cebaf1077fb66420d77d656db32f444dd932b85
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388104"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata
Questo esempio illustra come ottenere l'oggetto di binding da una proprietà di destinazione associata a dati.  
  
## <a name="example"></a>Esempio  
 È possibile eseguire il comando seguente per ottenere il <xref:System.Windows.Data.Binding> oggetto:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  È necessario specificare la proprietà di dipendenza per il binding desiderato, poiché è possibile che il data binding sia usato da più di una proprietà dell'oggetto di destinazione.  
  
 In alternativa, è possibile ottenere il <xref:System.Windows.Data.BindingExpression> e quindi ottenere il valore della <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> proprietà.  
  
 Per l'esempio completo, vedere [Binding Validation Sample (Esempio di convalida binding)](https://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Se il binding è un <xref:System.Windows.Data.MultiBinding>, usare <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>. Se si tratta di un <xref:System.Windows.Data.PriorityBinding>, usare <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>. Se si è sicuri se la proprietà di destinazione sia associata utilizzando un <xref:System.Windows.Data.Binding>, una <xref:System.Windows.Data.MultiBinding>, o una <xref:System.Windows.Data.PriorityBinding>, è possibile usare <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Creare un'associazione nel codice](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
