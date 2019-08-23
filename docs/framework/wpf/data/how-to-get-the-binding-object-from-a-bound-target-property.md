---
title: "Procedura: Ottenere l'oggetto di binding da una proprietà di destinazione associata"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c7aacc2145ffe98ec7b58afb3b2e3dca151ef0ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965428"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Procedura: Ottenere l'oggetto di binding da una proprietà di destinazione associata
Questo esempio illustra come ottenere l'oggetto di binding da una proprietà di destinazione associata a dati.  
  
## <a name="example"></a>Esempio  
 Per ottenere l' <xref:System.Windows.Data.Binding> oggetto, è possibile eseguire le operazioni seguenti:  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
> È necessario specificare la proprietà di dipendenza per il binding desiderato, poiché è possibile che il data binding sia usato da più di una proprietà dell'oggetto di destinazione.  
  
 In alternativa, è possibile ottenere <xref:System.Windows.Data.BindingExpression> e quindi ottenere il valore <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> della proprietà.  
  
 Per l'esempio completo, vedere [Binding Validation Sample (Esempio di convalida binding)](https://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
> Se l'associazione è un <xref:System.Windows.Data.MultiBinding>, utilizzare <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A> Se è <xref:System.Windows.Data.BindingOperations>, usare.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A> <xref:System.Windows.Data.PriorityBinding> Se non si è certi se la proprietà di destinazione è associata usando <xref:System.Windows.Data.Binding> <xref:System.Windows.Data.MultiBinding>, o <xref:System.Windows.Data.PriorityBinding>, è possibile usare.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A> <xref:System.Windows.Data.BindingOperations>  
  
## <a name="see-also"></a>Vedere anche

- [Creare un'associazione nel codice](how-to-create-a-binding-in-code.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
