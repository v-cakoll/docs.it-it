---
title: "Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 498849cc0205775f88c21d90d12b45c6b71a5dec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata
Questo esempio illustra come ottenere l'oggetto di binding da una proprietà di destinazione associata a dati.  
  
## <a name="example"></a>Esempio  
 È possibile eseguire le operazioni seguenti per ottenere il <xref:System.Windows.Data.Binding> oggetto:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  È necessario specificare la proprietà di dipendenza per il binding desiderato, poiché è possibile che il data binding sia usato da più di una proprietà dell'oggetto di destinazione.  
  
 In alternativa, è possibile ottenere il <xref:System.Windows.Data.BindingExpression> e quindi ottenere il valore della <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> proprietà.  
  
 Per l'esempio completo, vedere [Binding Validation Sample (Esempio di convalida binding)](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Se l'associazione è un <xref:System.Windows.Data.MultiBinding>, utilizzare <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>. Se si tratta di un <xref:System.Windows.Data.PriorityBinding>, utilizzare <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>. Se si è sicuri se la proprietà di destinazione sia associata utilizzando un <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>, o un <xref:System.Windows.Data.PriorityBinding>, è possibile utilizzare <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Creare un'associazione nel codice](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
