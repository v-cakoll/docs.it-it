---
title: Comportamento di AutoSize nel controllo TableLayoutPanel
ms.date: 03/30/2017
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
ms.openlocfilehash: 1f349981125097af4a3ca8a1950b820a0334bd11
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621486"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>Comportamento di AutoSize nel controllo TableLayoutPanel
## <a name="distinct-autosize-behaviors"></a>Diversi comportamenti di AutoSize  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo supporta il ridimensionamento automatico nei modi seguenti:  
  
- Tramite il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.  
  
- Tramite il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà di <xref:System.Windows.Forms.TableLayoutPanel> stili di riga e colonna del controllo.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>La proprietà AutoSize con stili di colonna e riga  
 Nella tabella seguente viene descritta l'interazione tra il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e il <xref:System.Windows.Forms.TableLayoutPanel> stili di riga e colonna del controllo.  
  
|Impostazione di ridimensionamento automatico|Interazione di stile|  
|----------------------|-----------------------|  
|`false`|Il <xref:System.Windows.Forms.TableLayoutPanel> controllo procede da sinistra a destra e alloca spazio per la colonna o riga o nell'ordine seguente.<br /><br /> 1.  Se il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> è impostata su <xref:System.Windows.Forms.SizeType.Absolute>, il numero di pixel specificato da <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> viene allocato.<br />2.  Se il <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> è impostata su <xref:System.Windows.Forms.SizeType.AutoSize>, il numero di pixel come risultato del controllo figlio <xref:System.Windows.Forms.Control.GetPreferredSize%2A> viene allocato (metodo).<br />3.  Dopo lo spazio per tutti i <xref:System.Windows.Forms.SizeType.Absolute> e <xref:System.Windows.Forms.SizeType.AutoSize> colonne o righe viene allocato, le eventuali colonne o le righe contenenti <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> impostato su <xref:System.Windows.Forms.SizeType.Percent> servono ad assegnare in modo proporzionale lo spazio libero rimanente|  
|`true`|Simile all'interazione precedente, con l'eccezione che <xref:System.Windows.Forms.SizeType.Percent> colonne o righe acquisire un aspetto di ridimensionamento automatico.<br /><br /> Il <xref:System.Windows.Forms.TableLayoutPanel> controllo si espande la colonna o riga per creare spazio sufficiente, in modo che nessuna colonna o riga con <xref:System.Windows.Forms.SizeType.Percent> troncare il contenuto. Il <xref:System.Windows.Forms.TableLayoutPanel> controllo consente di allocare il nuovo spazio in modo proporzionale in base al <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> proprietà.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TableLayoutPanel>
- [Panoramica del controllo TableLayoutPanel](tablelayoutpanel-control-overview.md)
