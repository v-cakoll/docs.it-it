---
title: 'Procedura: Rimuovere tutti gli strumenti decorativi da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116794"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>Procedura: Rimuovere tutti gli strumenti decorativi da un elemento
Questo esempio viene illustrato come rimuovere tutti gli strumenti decorativi da un oggetto specificato a livello <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Esempio  
 In questo esempio di codice piuttosto prolisso rimuove tutti gli strumenti decorativi nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  Questo esempio vengono recuperati gli strumenti decorativi in una <xref:System.Windows.UIElement> denominate *myTextBox*.  Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di alcun gli strumenti decorativi, `null` viene restituito.  Questo codice verifica la presenza di una matrice null in modo esplicito ed è ideale per le applicazioni in una matrice null deve essere abbastanza comune.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>Esempio  
 Questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza. Questo codice non verificano in modo esplicito per una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> eccezione potrebbe essere generata.  Questo codice è ideale per le applicazioni in cui è prevista una matrice null sono rare.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sugli strumenti decorativi](adorners-overview.md)
