---
title: Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente
description: Trovare ed evidenziare il testo usando l'automazione interfaccia utente. Un esempio cerca in modo sequenziale ed evidenzia ogni occorrenza di una stringa all'interno del contenuto del controllo di testo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: e4aca4b5ccdbc429a3d6267afc09b9f8b99cd7e9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164195"
---
# <a name="find-and-highlight-text-using-ui-automation"></a>Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento viene illustrato come eseguire una ricerca sequenziale ed evidenziare ogni occorrenza di una stringa all'interno del contenuto di un controllo di testo utilizzando [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene ottenuto un <xref:System.Windows.Automation.TextPattern> oggetto da un controllo di testo. Un <xref:System.Windows.Automation.Text.TextPatternRange> oggetto che rappresenta il contenuto testuale dell'intero documento viene quindi creato utilizzando la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> proprietà dell'oggetto <xref:System.Windows.Automation.TextPattern> . <xref:System.Windows.Automation.Text.TextPatternRange>Vengono quindi creati due oggetti aggiuntivi per la funzionalità di ricerca sequenziale e di evidenziazione.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>Vedere anche

- [Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente](find-and-highlight-text-using-ui-automation.md)
