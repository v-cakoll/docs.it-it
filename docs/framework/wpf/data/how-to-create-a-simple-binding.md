---
title: 'Procedura: Creare un binding semplice'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: d617c8b97aa679398ed2d061a652f5164f1e499b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931566"
---
# <a name="how-to-create-a-simple-binding"></a>Procedura: Creare un binding semplice
In questo esempio illustra come creare una semplice <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Esempio  
 In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`. Il `Person` oggetto viene definito nello spazio dei nomi denominato `SDKSample`.  
  
 La riga evidenziata che contiene il `<src>` elemento nell'esempio seguente crea un'istanza di `Person` dell'oggetto con un `PersonName` valore della proprietà `Joe`. Questa operazione viene eseguita `Resources` sezione e assegnare un `x:Key`.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La riga evidenziata che contiene il `<TextBlock>` elemento associa quindi il <xref:System.Windows.Controls.TextBlock> controllo il `PersonName` proprietà. Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
