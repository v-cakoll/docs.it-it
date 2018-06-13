---
title: "Procedura: analizzare l'input penna con i suggerimenti dell'analisi"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: 74f8b3df5767888e8bca0d9f67e9c47630353fb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543602"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a>Procedura: analizzare l'input penna con i suggerimenti dell'analisi
Un [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) fornisce un hint per la [InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) a cui è collegata.  Si applica l'hint per l'area specificata dal [System.Windows.Ink.ContextNode.Location%2A](https://msdn.microsoft.com/library/system.windows.ink.contextnode.location(v=vs.100).aspx) proprietà del [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) e fornisce un contesto aggiuntivo all'analizzatore dell'input penna per migliorare l'accuratezza del riconoscimento. Il [InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) Applica queste informazioni di contesto quando analizza l'input penna ottenuto dall'interno dell'area del suggerimento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente è un'applicazione che utilizza più [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) oggetti in un form che accetta l'input penna. L'applicazione utilizza il [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode.factoid(v=vs.100)) proprietà per fornire informazioni di contesto per ogni voce del form.  L'applicazione utilizza l'analisi in background per analizzare l'input penna e cancella il modulo di input penna di cinque secondi dopo che l'utente interrompe l'aggiunta di input penna.  
  
 [!code-xaml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
