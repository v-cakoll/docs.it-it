---
title: 'Procedura: regolare la spaziatura tra paragrafi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b2d02e1513a0d8a3c31e4a13c9599666a4122a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Procedura: regolare la spaziatura tra paragrafi
In questo esempio viene illustrato come modificare o eliminare la spaziatura tra i paragrafi nel contenuto del flusso.  
  
 Nel contenuto del flusso, lo spazio aggiuntivo che viene visualizzato tra i paragrafi è il risultato dei margini impostati per tali paragrafi. di conseguenza, è possibile controllare la spaziatura tra i paragrafi regolando i margini su paragrafi.  Per eliminare completamente la spaziatura tra i due paragrafi, impostare i margini per i paragrafi a **0**.  Per ottenere una spaziatura uniforme tra i paragrafi di un intero <xref:System.Windows.Documents.FlowDocument>, applicare uno stile per impostare un valore di un margine uniforme per tutti i paragrafi di <xref:System.Windows.Documents.FlowDocument>.  
  
 È importante notare che i margini per due paragrafi adiacenti "compressi" per il più elevato tra i due margini, anziché raddoppiati. Pertanto, se due paragrafi adiacenti hanno rispettivamente i margini di 20 e 40 pixel, lo spazio tra i paragrafi 40 pixel, il più elevato tra i valori dei margini di due.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato lo stile per impostare il margine per tutti <xref:System.Windows.Documents.Paragraph> elementi in un <xref:System.Windows.Documents.FlowDocument> a **0**, eliminando effettivamente la spaziatura tra i paragrafi di <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
