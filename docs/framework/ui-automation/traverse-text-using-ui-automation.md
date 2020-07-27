---
title: Scorrere il testo utilizzando automazione interfaccia utente
description: Vedere un esempio di come attraversare il contenuto di testo di un documento usando l'automazione interfaccia utente Microsoft, in incrementi di TextUnit.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
ms.openlocfilehash: 0b4269d043fd6cd0cc5da9825714aab4ead701f9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168097"
---
# <a name="traverse-text-using-ui-automation"></a>Scorrere il testo utilizzando automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento viene illustrato come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per scorrere il contenuto testuale di un documento in base a incrementi definiti da <xref:System.Windows.Automation.Text.TextUnit> .  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come scorrere il contenuto di un provider di testo di automazione interfaccia utente. Il metodo <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> sposta gli endpoint <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> e <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> di una classe <xref:System.Windows.Automation.Text.TextPatternRange>. Questo intervallo di testo è in genere un intervallo degenere che rappresenta il punto di inserimento.  
  
> [!NOTE]
> Poiché solo gli oggetti incorporati basati su testo sono considerati parte del flusso di testo, gli oggetti incorporati, ad esempio le immagini, non interessano `Move` o il relativo valore restituito.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 Qualsiasi metodo che usa <xref:System.Windows.Automation.Text.TextUnit> rinvia al successivo valore più grande di <xref:System.Windows.Automation.Text.TextUnit> supportato se il valore specificato di <xref:System.Windows.Automation.Text.TextUnit> non è supportato dal controllo.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul modello TextPattern di automazione interfaccia utente](ui-automation-textpattern-overview.md)
- [Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente](add-content-to-a-text-box-using-ui-automation.md)
- [Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente](find-and-highlight-text-using-ui-automation.md)
- [Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente](ui-automation-control-patterns-overview.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
