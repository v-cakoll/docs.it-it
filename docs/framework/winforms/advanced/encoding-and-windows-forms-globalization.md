---
title: Globalizzazione di Windows Form e codifica
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
ms.openlocfilehash: e610b4fc5506043835377bf9f5750550d8aec694
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="encoding-and-windows-forms-globalization"></a>Globalizzazione di Windows Form e codifica
Le applicazioni Windows Forms sono completamente compatibili con Unicode, vale a dire che ogni carattere è rappresentato da un numero univoco, indipendentemente dalla piattaforma, dal programma o dal linguaggio in uso. Per ulteriori informazioni su Unicode, vedere il [sito Web di Unicode consortium](http://www.unicode.org).  
  
## <a name="benefits-of-unicode"></a>Vantaggi di Unicode  
 I vantaggi dei form abilitati per Unicode includono la possibilità di lavorare con gli script solo Unicode, ad esempio l'Hindi. È anche possibile usare più lingue in un unico form. In Unicode tutti i caratteri sono lunghi due byte, quindi non occorrono operazioni complesse per rappresentare i caratteri DBCS. È anche possibile scrivere un singolo set di codice che funzionerà su tutte le piattaforme. Si tratta di una modifica rispetto alle versioni precedenti di Visual Basic, in cui era necessario scrivere codice diverso per piattaforme diverse, ad esempio Windows NT e [!INCLUDE[win98](../../../../includes/win98-md.md)].  
  
 Tuttavia, alcuni controlli non supportano Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] e Windows Millennium Edition. Questi controlli, tutti eredi del controllo comune, elaborano i dati con le tabelle codici di Windows, ad esempio [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)]. Questi controlli sono: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> e <xref:System.Windows.Forms.StatusBar>. Di conseguenza, non è possibile visualizzare i dati Unicode in questi controlli sulle piattaforme elencate. Ad esempio, non è possibile visualizzare caratteri giapponesi in un sistema operativo [!INCLUDE[win98](../../../../includes/win98-md.md)] in inglese.  
  
 Per alternative con supporto Unicode a <xref:System.Windows.Forms.ToolBar> e <xref:System.Windows.Forms.StatusBar>, usare i controlli <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip> che sostituiscono i controlli precedenti. Per mantenere un aspetto omogeneo tra gli elementi visivi nell'applicazione, usare il controllo <xref:System.Windows.Forms.MenuStrip> al posto di <xref:System.Windows.Forms.MainMenu> per il rendering dei menu. Come <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip>, anche <xref:System.Windows.Forms.MenuStrip> può elaborare e visualizzare i caratteri Unicode.  
  
## <a name="see-also"></a>Vedere anche  
 [Globalizzazione di Windows Form](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
