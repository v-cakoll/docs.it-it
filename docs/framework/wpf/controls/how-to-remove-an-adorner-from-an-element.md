---
title: 'Procedura: rimuovere uno strumento decorativo da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: a3e1b08a9ec5e2cd60c063ced5e5f0d5874f8184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551843"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>Procedura: rimuovere uno strumento decorativo da un elemento
In questo esempio viene illustrato come rimuovere a livello di codice un adorner specifico da un oggetto specificato <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice dettagliato rimuove il primo strumento decorativo nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  Questo esempio vengono recuperati gli strumenti decorativi su un <xref:System.Windows.UIElement> denominato *myTextBox*.  Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> senza strumenti decorativi visuali, `null` viene restituito.  Questo codice verifica la presenza di una matrice null, in modo esplicito ed è più adatto per le applicazioni in una matrice null deve essere abbastanza comune.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>Esempio  
 In questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza. Questo codice non controllano in modo esplicito una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> può essere generata l'eccezione.  Questo codice è più adatto per le applicazioni in cui in cui è prevista una matrice null rari.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sugli strumenti decorativi](../../../../docs/framework/wpf/controls/adorners-overview.md)
