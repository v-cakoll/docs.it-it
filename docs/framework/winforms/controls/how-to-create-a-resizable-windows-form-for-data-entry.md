---
title: 'Procedura: creare Windows Form ridimensionabile per immissione dati'
ms.date: 03/30/2017
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
ms.openlocfilehash: aeab1b506b9ded4c3c2ab527f07a8655a44cad2b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396018"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>Procedura: creare Windows Form ridimensionabile per immissione dati
Un layout appropriato risponde correttamente alle modifiche apportate alle dimensioni del form padre. È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per disporre il layout del form in modo che i controlli vengano ridimensionati e posizionati in maniera coerente quando cambiano le dimensioni del form. Il controllo <xref:System.Windows.Forms.TableLayoutPanel> è utile anche quando le modifiche del contenuto dei controlli generano modifiche nel layout. Il processo descritto in questa procedura può essere eseguito nell'ambiente di Visual Studio.  Vedere anche [Procedura dettagliata: creazione di un Windows Form ridimensionabile per l'inserimento di dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come usare un controllo <xref:System.Windows.Forms.TableLayoutPanel> per creare un layout che risponda correttamente quando l'utente ridimensiona il form. Illustra anche un layout che risponda correttamente alla localizzazione.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Procedura: Progettare un layout di Windows Form che risponda correttamente alla localizzazione](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
