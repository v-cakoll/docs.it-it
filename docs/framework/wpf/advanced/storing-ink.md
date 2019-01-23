---
title: Memorizzazione dell'input penna
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: c115e31b73afc1532973be3db8e3e184e9a4253b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492888"
---
# <a name="storing-ink"></a>Memorizzazione dell'input penna
Il <xref:System.Windows.Ink.StrokeCollection.Save%2A> metodi forniscono supporto per l'archiviazione dell'input penna in formato ISF (Ink Serialized Format). I costruttori per la <xref:System.Windows.Ink.StrokeCollection> classi forniscono supporto per la lettura dei dati di input penna.  
  
## <a name="ink-storage-and-retrieval"></a>Archiviazione dell'input penna e il recupero  
 Questa sezione illustra come archiviare e recuperare l'input penna nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] piattaforma.  
  
 L'esempio seguente implementa un gestore eventi clic del pulsante che presenta all'utente una finestra di dialogo Salva File e Salva l'input penna da un <xref:System.Windows.Controls.InkCanvas> out in un file.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 L'esempio seguente implementa un gestore eventi clic del pulsante che presenta all'utente una finestra di dialogo Apri File e legge l'input penna dal file in un <xref:System.Windows.Controls.InkCanvas> elemento.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.InkCanvas>
- [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)
