---
title: "Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: cf2ddc93a7c46ee6956d2731a786289f64086360
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976429"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata
Questo esempio illustra come ottenere l'oggetto di binding da una proprietà di destinazione associata a dati.

## <a name="example"></a>Esempio
 Per ottenere l'oggetto <xref:System.Windows.Data.Binding>, è possibile eseguire le operazioni seguenti:

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> È necessario specificare la proprietà di dipendenza per il binding desiderato, poiché è possibile che il data binding sia usato da più di una proprietà dell'oggetto di destinazione.

 In alternativa, è possibile ottenere il <xref:System.Windows.Data.BindingExpression> e quindi ottenere il valore della proprietà <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>.

 Per l'esempio completo, vedere [Binding Validation Sample (Esempio di convalida binding)](https://go.microsoft.com/fwlink/?LinkID=159972).

> [!NOTE]
> Se l'associazione è una <xref:System.Windows.Data.MultiBinding>, utilizzare <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>. Se si tratta di una <xref:System.Windows.Data.PriorityBinding>, utilizzare <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>. Se non si è certi che la proprietà di destinazione sia associata utilizzando un <xref:System.Windows.Data.Binding>, un <xref:System.Windows.Data.MultiBinding>o un <xref:System.Windows.Data.PriorityBinding>, è possibile utilizzare <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- [Creare un'associazione nel codice](how-to-create-a-binding-in-code.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
