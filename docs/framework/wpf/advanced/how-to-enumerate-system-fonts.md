---
title: 'Procedura: enumerare i caratteri del sistema'
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
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ae03cbd8828f61011f8d806be32b5827d77b22a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enumerate-system-fonts"></a>Procedura: enumerare i caratteri del sistema
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come enumerare i tipi di carattere nell'insieme di tipi di carattere di sistema. Il nome della famiglia di ogni <xref:System.Windows.Media.FontFamily> all'interno di <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> viene aggiunto come un elemento in una casella combinata.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Se più versioni della stessa famiglia risiedono nella stessa directory, il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enumerazione carattere restituisce la versione più recente del tipo di carattere. Se le informazioni sulla versione non fornire la risoluzione, viene restituito il tipo di carattere con il timestamp più recente. Se le informazioni sul timestamp è equivalente, viene restituito il tipo di carattere che è il primo in ordine alfabetico.
