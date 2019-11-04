---
title: 'Procedura: creare associazioni semplici'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453505"
---
# <a name="how-to-create-a-simple-binding"></a>Procedura: creare associazioni semplici
Questo esempio illustra come creare una semplice <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Esempio  
 In questo esempio è presente un oggetto `Person` con una proprietà stringa denominata `PersonName`. L'oggetto `Person` viene definito nello spazio dei nomi denominato `SDKSample`.  
  
 La riga evidenziata che contiene l'elemento `<src>` nell'esempio seguente crea un'istanza dell'oggetto `Person` con un valore della proprietà `PersonName` di `Joe`. Questa operazione viene eseguita nella sezione `Resources` e assegnata una `x:Key`.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La riga evidenziata che contiene l'elemento `<TextBlock>` associa quindi il controllo <xref:System.Windows.Controls.TextBlock> alla proprietà `PersonName`. Di conseguenza, il <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
