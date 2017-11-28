---
title: 'Procedura: creare associazioni semplici'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a61844f917539f5d5e7c99299c8a33f4aa18450f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-binding"></a>Procedura: creare associazioni semplici
In questo esempio viene illustrato come creare un semplice <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Esempio  
 In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`. Il `Person` oggetto viene definito nello spazio dei nomi denominato `SDKSample`.  
  
 Nell'esempio seguente viene creata un'istanza di `Person` dell'oggetto con un `PersonName` valore della proprietà `Joe`. Questa operazione viene eseguita `Resources` sezione e assegnare un `x:Key`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xaml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 Per associare il `PersonName` è necessario effettuare le seguenti proprietà:  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
