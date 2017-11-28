---
title: 'Procedura: eseguire l''associazione a un''enumerazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31fb9adbda47514e5405d465c0b5e2493b966d8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-enumeration"></a>Procedura: eseguire l'associazione a un'enumerazione
In questo esempio viene illustrato come associare a un'enumerazione tramite l'associazione al metodo GetValues dell'enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza un elenco di <xref:System.Windows.HorizontalAlignment> valori di enumerazione tramite l'associazione dati. Il <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.Button> associati in modo che sia possibile modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà il <xref:System.Windows.Controls.Button> selezionando un valore nel <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Vedere anche  
 [Eseguire l'associazione a un metodo](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
