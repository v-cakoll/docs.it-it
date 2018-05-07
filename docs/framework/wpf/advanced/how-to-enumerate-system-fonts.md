---
title: 'Procedura: enumerare i caratteri del sistema'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7fc996a2d3ba7042fce70afc20be5d64042c2b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-system-fonts"></a>Procedura: enumerare i caratteri del sistema
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come enumerare i tipi di carattere nell'insieme di tipi di carattere di sistema. Il nome della famiglia di ogni <xref:System.Windows.Media.FontFamily> all'interno di <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> viene aggiunto come un elemento in una casella combinata.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Se più versioni della stessa famiglia risiedono nella stessa directory, il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enumerazione carattere restituisce la versione più recente del tipo di carattere. Se le informazioni sulla versione non fornire la risoluzione, viene restituito il tipo di carattere con il timestamp più recente. Se le informazioni sul timestamp è equivalente, viene restituito il tipo di carattere che è il primo in ordine alfabetico.
