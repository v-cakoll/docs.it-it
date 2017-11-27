---
title: Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0acd6510e6349917b38e33e487123a118c2e653c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per inserire testo in una casella di testo a riga singola. Viene fornito un metodo alternativo per i controlli su più righe e rich text in cui [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è applicabile. Ai fini del confronto, nell'esempio viene inoltre illustrato come utilizzare i metodi Win32 per ottenere gli stessi risultati.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente in una sequenza di controlli di testo in un'applicazione di destinazione. Ogni controllo di testo viene testato per verificare se un <xref:System.Windows.Automation.ValuePattern> oggetto può essere ottenuto tramite il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> metodo. Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern>, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> metodo viene utilizzato per inserire una stringa definita dall'utente nel controllo di testo. In caso contrario, il <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> viene usato il metodo.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>Vedere anche  
 [TextPattern Insert Text Sample](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
