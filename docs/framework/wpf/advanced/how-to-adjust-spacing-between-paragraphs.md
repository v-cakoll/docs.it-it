---
title: 'Procedura: Regolare la spaziatura tra paragrafi'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367479"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Procedura: Regolare la spaziatura tra paragrafi
In questo esempio viene illustrato come modificare o eliminare la spaziatura tra paragrafi nel contenuto dinamico.  
  
 Nel contenuto dinamico, lo spazio aggiuntivo che viene visualizzato tra i paragrafi è il risultato dei margini impostati per queste paragrafi. di conseguenza, la spaziatura tra paragrafi può essere controllata regolando i margini in paragrafi.  Per eliminare completamente la spaziatura aggiuntiva tra due paragrafi, impostare i margini di paragrafi vengano **0**.  Per ottenere la spaziatura uniforme tra i paragrafi di un intero <xref:System.Windows.Documents.FlowDocument>, applicare uno stile per impostare un valore di un margine uniforme per tutti i paragrafi di <xref:System.Windows.Documents.FlowDocument>.  
  
 È importante notare che i margini per due paragrafi adiacenti "comprimerà" per il valore più grande tra i due margini, anziché raddoppiati. Pertanto, se due paragrafi adiacenti presentano il margine di 20 e 40 pixel rispettivamente, lo spazio tra i paragrafi 40 pixel, il più elevato tra i valori per i due margini.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa lo stile per impostare il margine per tutti <xref:System.Windows.Documents.Paragraph> elementi in un <xref:System.Windows.Documents.FlowDocument> al **0**, che elimina in modo efficace la spaziatura tra paragrafi nel <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
