---
title: 'Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento'
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
helpviewer_keywords: adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e9b69b9150e8d2c2938c53fcd47e72b7fcb6d238
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento
In questo esempio viene illustrato come rimuovere a livello di codice tutti gli strumenti decorativi da un oggetto specificato <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice dettagliato rimuove tutti gli strumenti decorativi nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  Questo esempio vengono recuperati gli strumenti decorativi su un <xref:System.Windows.UIElement> denominato *myTextBox*.  Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> senza strumenti decorativi visuali, `null` viene restituito.  Questo codice verifica la presenza di una matrice null, in modo esplicito ed è più adatto per le applicazioni in una matrice null deve essere abbastanza comune.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>Esempio  
 In questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza. Questo codice non controllano in modo esplicito una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> può essere generata l'eccezione.  Questo codice è più adatto per le applicazioni in cui in cui è prevista una matrice null rari.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sugli strumenti decorativi](../../../../docs/framework/wpf/controls/adorners-overview.md)
