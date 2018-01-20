---
title: 'Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c6dd45d2070c77b34c66388b397bb784215654
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione
Windows Form <xref:System.Windows.Forms.Panel> controlli vengono utilizzati per raggruppare altri controlli. Vi sono tre motivi per i controlli di gruppo. Raggruppamento di elementi di form per un'interfaccia utente deselezionare; visivo un vantaggio è a livello di codice raggruppamento di pulsanti di opzione, ad esempio; l'ultimo si per spostare i controlli in un'unità in fase di progettazione.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-group-of-controls"></a>Per creare un gruppo di controlli  
  
1.  Trascinare un <xref:System.Windows.Forms.Panel> controllo il **Windows Form** della casella degli strumenti in un form.  
  
2.  Aggiungere altri controlli al pannello, creando ciascun all'interno del pannello.  
  
     Se si dispone di controlli esistenti che si desidera inserire in un pannello, è possibile selezionare tutti i controlli, li tagliare negli Appunti, selezionare il <xref:System.Windows.Forms.Panel> controllare e incollarli quindi nel pannello. È anche possibile trascinare i controlli nel pannello.  
  
3.  (Facoltativo) Se si desidera aggiungere un bordo a un pannello, impostare il relativo <xref:System.Windows.Forms.BorderStyle> proprietà. Sono disponibili tre opzioni: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, e <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panoramica sul controllo Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Procedura: Impostare lo sfondo di un controllo Panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
