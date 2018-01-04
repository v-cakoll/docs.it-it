---
title: Cenni preliminari sul componente NotifyIcon (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c909537bd4c52a546faeb83c6e9291c4de76d76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="notifyicon-component-overview-windows-forms"></a>Cenni preliminari sul componente NotifyIcon (Windows Form)
Il componente <xref:System.Windows.Forms.NotifyIcon> di Windows Form viene in genere usato per la visualizzazione di icone per i processi eseguiti in background e, per la maggior parte del tempo, non presenta alcuna interfaccia utente. Un esempio può essere rappresentato da un programma di protezione dai virus, al quale è possibile accedere facendo clic su un'icona riportata nell'area di notifica dello stato della barra delle applicazioni.  
  
## <a name="key-properties-of-notifyicons"></a>Proprietà chiave di NotifyIcons  
 Ogni componente di <xref:System.Windows.Forms.NotifyIcon> visualizza una singola icona nell'area di stato. Se vengono eseguiti in background tre processi e si vuole visualizzare un'icona per ognuno di essi, è necessario aggiungere al form tre componenti <xref:System.Windows.Forms.NotifyIcon>. Le proprietà chiave del componente <xref:System.Windows.Forms.NotifyIcon> sono <xref:System.Windows.Forms.NotifyIcon.Icon%2A> e <xref:System.Windows.Forms.NotifyIcon.Visible%2A>. La proprietà <xref:System.Windows.Forms.NotifyIcon.Icon%2A> imposta l'icona visualizzata nell'area di notifica. Affinché l'icona venga visualizzata, è anche necessario impostare la proprietà <xref:System.Windows.Forms.NotifyIcon.Visible%2A> su `true`.  
  
 Se si usa [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], è disponibile un'ampia libreria di immagini standard da usare con il controllo <xref:System.Windows.Forms.NotifyIcon>.  
  
## <a name="notifyicons-options"></a>Opzioni di NotifyIcons  
 Al controllo <xref:System.Windows.Forms.NotifyIcon> è possibile associare suggerimenti, menu di scelta rapida e descrizioni comandi per assistere l'utente.  
  
 I suggerimenti possono essere inseriti in un controllo <xref:System.Windows.Forms.NotifyIcon> chiamando il metodo <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> e specificando l'intervallo di tempo per la visualizzazione del suggerimento. È anche possibile specificare il testo, l'icona e il titolo del suggerimento per le proprietà <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> e <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A> rispettivamente. Ai componenti <xref:System.Windows.Forms.NotifyIcon> è possibile anche associare descrizioni comandi e menu di scelta rapida. Per ulteriori informazioni, vedere [Cenni preliminari sul componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) e [Cenni preliminari sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.NotifyIcon>  
 [Componente NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)
