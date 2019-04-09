---
title: Ottenere dettagli sugli attributi di testo misti utilizzando l'automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
ms.openlocfilehash: f52ff1b669f821d102a65888189d9bbf2c000da8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158483"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a>Ottenere dettagli sugli attributi di testo misti utilizzando l'automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento viene illustrato come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per ottenere dettagli sugli attributi di testo da un intervallo di testo che si estende su più valori di attributo. Un intervallo di testo può corrispondere alla posizione corrente del punto di inserimento (o selezione degenere) all'interno di un documento, una selezione contigua di testo, un insieme di selezioni di testo non contigue o l'intero contenuto testuale di un documento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come ottenere <xref:System.Windows.Automation.TextPattern.FontNameAttribute> da un intervallo di testo, dove <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> restituisce un oggetto <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> .  
  
[!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
[!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 Il pattern di controllo <xref:System.Windows.Automation.TextPattern> , in combinazione con la classe <xref:System.Windows.Automation.Text.TextPatternRange> , supporta gli attributi, le proprietà e i metodi di base del testo. Per la funzionalità specifica del controllo non supportata da <xref:System.Windows.Automation.TextPattern> o <xref:System.Windows.Automation.Text.TextPatternRange>, la classe <xref:System.Windows.Automation.AutomationElement> implementa metodi per un client di automazione interfaccia utente per accedere al corrispondente modello a oggetti nativo.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul modello TextPattern di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)
- [Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)
- [Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
- [Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Pattern di controllo di automazione interfaccia utente per i client](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Ottenere attributi di testo mediante l'automazione interfaccia utente](../../../docs/framework/ui-automation/obtain-text-attributes-using-ui-automation.md)
