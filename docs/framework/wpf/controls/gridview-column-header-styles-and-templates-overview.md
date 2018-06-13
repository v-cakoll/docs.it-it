---
title: Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView
ms.date: 03/30/2017
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
ms.openlocfilehash: 28b4a64a6c79b226b1ff4b3bfcbf9a55b6d8df78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553871"
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView
Questa panoramica illustra l'ordine di precedenza per le proprietà che consentono di personalizzare in un'intestazione di colonna il <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>Personalizzazione di un'intestazione di colonna in un controllo GridView.  
 Le proprietà che definiscono il contenuto, layout e lo stile di un'intestazione di colonna in un <xref:System.Windows.Controls.GridView> sono disponibili in molte classi correlate. Alcune di queste proprietà presentano funzionalità simili o uguali.  
  
 Le righe nella tabella seguente mostrano i gruppi di proprietà che eseguono la stessa funzione. È possibile utilizzare queste proprietà per personalizzare le intestazioni di colonna in un <xref:System.Windows.Controls.GridView>. L'ordine di precedenza per le proprietà correlate è da destra a sinistra, in cui la proprietà nella colonna all'estrema destra ha la precedenza più alta. Ad esempio, se un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> è impostato sul <xref:System.Windows.Controls.GridViewColumnHeader> oggetto e <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> è impostata sull'oggetto associato <xref:System.Windows.Controls.GridViewColumn>, il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> ha la precedenza. In questo scenario, il <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> non ha alcun effetto.  
  
 **Proprietà correlate per le intestazioni di colonna in un controllo GridView.**  
  
|||||  
|-|-|-|-|  
|**Classi**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Proprietà di menu di scelta rapida**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|Non applicabile|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **Proprietà**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|Non applicabile|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Modello di intestazione**<br /><br /> **Proprietà**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Proprietà di stile**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>per **proprietà modello di intestazione**, se è impostato sia il modello e le proprietà di selettore di modello, la proprietà di modello ha la precedenza. Ad esempio, se si impostano entrambe le <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> e <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> proprietà, il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà ha la precedenza.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
