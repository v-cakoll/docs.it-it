---
title: 'Procedura: creare Windows Form ridimensionabile per immissione dati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 51e844dc49f75e2f27ad5bbaf9176e71f6e3388a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>Procedura: creare Windows Form ridimensionabile per immissione dati
Un layout appropriato risponde correttamente alle modifiche apportate alle dimensioni del form padre. È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per disporre il layout del form in modo che i controlli vengano ridimensionati e posizionati in maniera coerente quando cambiano le dimensioni del form. Il controllo <xref:System.Windows.Forms.TableLayoutPanel> è utile anche quando le modifiche del contenuto dei controlli generano modifiche nel layout. Il processo descritto in questa procedura può essere eseguito nell'ambiente di Visual Studio.  Vedere anche [Procedura dettagliata: creazione di un Windows Form ridimensionabile per l'inserimento di dati](http://msdn.microsoft.com/library/991eahec\(v=vs.110\)).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come usare un controllo <xref:System.Windows.Forms.TableLayoutPanel> per creare un layout che risponda correttamente quando l'utente ridimensiona il form. Illustra anche un layout che risponda correttamente alla localizzazione.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Procedura: Progettare un layout di Windows Form che risponda correttamente alla localizzazione](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers (Esperienza utente di Microsoft Windows, Linee guida ufficiali per analisti e sviluppatori dell'interfaccia utente). Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)
