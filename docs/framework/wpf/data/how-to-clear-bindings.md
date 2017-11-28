---
title: 'Procedura: cancellare associazioni'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f8e009d00960f40abcd3c3913a15fa51f1be4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-clear-bindings"></a>Procedura: cancellare associazioni
Questo esempio illustra come cancellare le associazioni da un oggetto.  
  
## <a name="example"></a>Esempio  
 Per eliminare un'associazione da una singola proprietà in un oggetto, chiamare <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> come illustrato nell'esempio seguente. Nell'esempio seguente viene rimossa l'associazione dal <xref:System.Windows.Controls.TextBlock.TextProperty> di *mytext*, <xref:System.Windows.Controls.TextBlock> oggetto.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 La cancellazione rimuove l'associazione in modo che il valore della proprietà di dipendenza venga modificato in quello avrebbe assunto senza l'associazione. Questo valore potrebbe essere un valore predefinito, un valore ereditato o un valore ottenuto da un'associazione di modelli di dati.  
  
 Per cancellare le associazioni da tutte le possibili proprietà su un oggetto, utilizzare <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.BindingOperations>  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
