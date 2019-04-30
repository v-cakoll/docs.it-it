---
title: 'Procedura: Enumerare i tipi di carattere del sistema'
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
ms.openlocfilehash: c7e81b5d1b70ba911a0b505219f7977e019038cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001598"
---
# <a name="how-to-enumerate-system-fonts"></a>Procedura: Enumerare i tipi di carattere del sistema
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come enumerare i tipi di carattere nella raccolta del tipo di carattere del sistema. Il nome della famiglia della ognuno <xref:System.Windows.Media.FontFamily> all'interno di <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> viene aggiunto come un elemento a una casella combinata.  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Se più versioni della stessa famiglia di caratteri si trovano nella stessa directory, il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enumerazione del tipo di carattere restituisce la versione più recente del tipo di carattere. Se le informazioni sulla versione non fornisce la risoluzione, viene restituito il tipo di carattere con timestamp più recente. Se le informazioni relative al timestamp sono equivalente, viene restituito il file del tipo di carattere che compare per primo in ordine alfabetico.
