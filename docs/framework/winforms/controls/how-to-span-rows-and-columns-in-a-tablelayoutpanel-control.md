---
title: 'Procedura: inserire righe e colonne in un controllo TableLayoutPanel'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 24b281e6e1ab56e2c7387435bf2429e7e107c4b8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Procedura: inserire righe e colonne in un controllo TableLayoutPanel
Controlli in un <xref:System.Windows.Forms.TableLayoutPanel> controllo può estendersi su righe e colonne adiacenti.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-span-columns-and-rows"></a>Per inserire righe e colonne  
  
1.  Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.  
  
2.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
3.  Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e la seconda colonna.  
  
4.  Impostare il <xref:System.Windows.Forms.Button> del controllo **RowSpan** proprietà **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda riga.  
  
5.  Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **1**. Si noti che il <xref:System.Windows.Forms.Button> controllo si sposta nella prima colonna e inserisce le righe del prima e seconda.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
