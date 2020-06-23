---
title: Ottenere dettagli sugli attributi di testo misti utilizzando l'automazione interfaccia utente
description: Ottenere i dettagli dell'attributo di testo misto usando le classi di automazione interfaccia utente gestita nello spazio dei nomi System. Windows. Automation dell'API .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
ms.openlocfilehash: 111d110be9365c4a58f2bd2b033c1ff4e3a6a95d
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903857"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a>Ottenere dettagli sugli attributi di testo misti utilizzando l'automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento viene illustrato come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per ottenere dettagli sugli attributi di testo da un intervallo di testo che si estende su più valori di attributo. Un intervallo di testo può corrispondere alla posizione corrente del punto di inserimento (o selezione degenere) all'interno di un documento, una selezione contigua di testo, un insieme di selezioni di testo non contigue o l'intero contenuto testuale di un documento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come ottenere <xref:System.Windows.Automation.TextPattern.FontNameAttribute> da un intervallo di testo, dove <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> restituisce un oggetto <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> .  
  
[!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
[!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 Il pattern di controllo <xref:System.Windows.Automation.TextPattern> , in combinazione con la classe <xref:System.Windows.Automation.Text.TextPatternRange> , supporta gli attributi, le proprietà e i metodi di base del testo. Per la funzionalità specifica del controllo non supportata da <xref:System.Windows.Automation.TextPattern> o <xref:System.Windows.Automation.Text.TextPatternRange>, la classe <xref:System.Windows.Automation.AutomationElement> implementa metodi per un client di automazione interfaccia utente per accedere al corrispondente modello a oggetti nativo.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul modello TextPattern di automazione interfaccia utente](ui-automation-textpattern-overview.md)
- [Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente](add-content-to-a-text-box-using-ui-automation.md)
- [Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente](find-and-highlight-text-using-ui-automation.md)
- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [Ottenere attributi di testo mediante l'automazione interfaccia utente](obtain-text-attributes-using-ui-automation.md)
