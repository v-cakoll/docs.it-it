---
title: Comportamento di AutoSize nel controllo TableLayoutPanel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d4813b7bd37c0c5bd9b04b37cb825067b35ce3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>Comportamento di AutoSize nel controllo TableLayoutPanel
## <a name="distinct-autosize-behaviors"></a>Diversi comportamenti di AutoSize  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo supporta il ridimensionamento automatico nei modi seguenti:  
  
-   Tramite il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.  
  
-   Tramite il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà il <xref:System.Windows.Forms.TableLayoutPanel> stili per riga e colonna del controllo.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>La proprietà AutoSize con stili di colonna e riga  
 Nella tabella seguente viene descritta l'interazione tra il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e <xref:System.Windows.Forms.TableLayoutPanel> stili per riga e colonna del controllo.  
  
|Impostazione di AutoSize|Interazione di stile|  
|----------------------|-----------------------|  
|`false`|Il <xref:System.Windows.Forms.TableLayoutPanel> controllo procede da sinistra a destra e consente di allocare spazio per la colonna o riga o nell'ordine seguente.<br /><br /> 1.  Se il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> è impostata su <xref:System.Windows.Forms.SizeType.Absolute>, il numero di pixel specificato da <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> viene allocato.<br />2.  Se il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> è impostata su <xref:System.Windows.Forms.SizeType.AutoSize>, il numero di pixel come risultato del controllo figlio <xref:System.Windows.Forms.Control.GetPreferredSize%2A> (metodo) viene allocato.<br />3.  Spazio per tutte <xref:System.Windows.Forms.SizeType.Absolute> e <xref:System.Windows.Forms.SizeType.AutoSize> colonne o righe viene allocato, le eventuali colonne o righe con <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> impostato su <xref:System.Windows.Forms.SizeType.Percent> vengono utilizzati per allocare in proporzione lo spazio libero rimanente|  
|`true`|Simile all'interazione precedente, con l'eccezione che <xref:System.Windows.Forms.SizeType.Percent> colonne o righe vengono ridimensionate automaticamente di acquisizione.<br /><br /> Il <xref:System.Windows.Forms.TableLayoutPanel> controllo espande la colonna o riga per creare lo spazio libero, in modo che nessuna colonna o riga con <xref:System.Windows.Forms.SizeType.Percent> troncare il contenuto. Il <xref:System.Windows.Forms.TableLayoutPanel> controllo alloca in modo proporzionale in base al nuovo spazio di <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> proprietà.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Panoramica del controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
