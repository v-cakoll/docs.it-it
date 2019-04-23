---
title: 'Procedura: Rimuovere uno strumento decorativo da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212401"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>Procedura: Rimuovere uno strumento decorativo da un elemento
In questo esempio viene illustrato come rimuovere a livello di codice un adorner specifico da un oggetto specificato <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Esempio  
 In questo esempio di codice piuttosto prolisso rimuove il primo strumento decorativo nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  Questo esempio vengono recuperati gli strumenti decorativi in una <xref:System.Windows.UIElement> denominate *myTextBox*.  Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di alcun gli strumenti decorativi, `null` viene restituito.  Questo codice verifica la presenza di una matrice null in modo esplicito ed è ideale per le applicazioni in una matrice null deve essere abbastanza comune.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza. Questo codice non verificano in modo esplicito per una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> eccezione potrebbe essere generata.  Questo codice è ideale per le applicazioni in cui è prevista una matrice null sono rare.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sugli strumenti decorativi](adorners-overview.md)
