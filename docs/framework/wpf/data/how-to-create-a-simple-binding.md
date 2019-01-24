---
title: "Procedura: Creare un'associazione semplice"
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 3e38fa5fd1c7d0a635efd93de6ebe551f1eb1b82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594837"
---
# <a name="how-to-create-a-simple-binding"></a>Procedura: Creare un'associazione semplice
In questo esempio illustra come creare una semplice <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Esempio  
 In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`. Il `Person` oggetto viene definito nello spazio dei nomi denominato `SDKSample`.  
  
 La riga evidenziata che contiene il `<src>` elemento nell'esempio seguente crea un'istanza di `Person` dell'oggetto con un `PersonName` valore della proprietà `Joe`. Questa operazione viene eseguita `Resources` sezione e assegnare un `x:Key`.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La riga evidenziata che contiene il `<TextBlock>` elemento associa quindi il <xref:System.Windows.Controls.TextBlock> controllo il `PersonName` proprietà. Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
