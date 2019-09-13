---
title: 'Procedura: Progettare un layout di Windows Forms che risponda correttamente alla localizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: c1aa62413e1c9cc29507b7b0ed5cbf1c5fcea26a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928561"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Procedura: Progettare un layout di Windows Forms che risponda correttamente alla localizzazione
La creazione di form pronti per la localizzazione accelera notevolmente lo sviluppo per i mercati internazionali. È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per implementare layout che rispondano correttamente man mano che i controlli vengono ridimensionati in seguito alle modifiche dei valori della proprietà <xref:System.Windows.Forms.Control.Text%2A>.  
  
## <a name="example"></a>Esempio  
 In questo form viene illustrato come creare un layout che viene modificato proporzionalmente quando si traducono i valori stringa visualizzati in altre lingue. Questo processo di traduzione è denominato *localizzazione*. Per altre informazioni, vedere [Localizzazione](../../../standard/globalization-localization/localization.md).  
  
 In Visual Studio è disponibile supporto completo per questa attività.  Vedere anche [procedura dettagliata: Creazione di un layout per la regolazione della proporzione per la localizzazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a>Risorse aggiuntive

1. [Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [Procedura dettagliata: Disposizione di controlli in Windows Forms tramite FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [Procedura: Estensione di righe e colonne in un controllo TableLayoutPanel](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [Procedura: Modificare colonne e righe in un controllo TableLayoutPanel](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [Procedura dettagliata: Esecuzione di attività comuni tramite smart tag sui controlli Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [Procedura dettagliata: Disposizione di controlli in Windows Forms tramite TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [Procedura dettagliata: Layout Windows Forms controlli con spaziatura interna, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)  
  
8. [Procedura: Supporto della localizzazione nei Windows Forms con AutoSize e il controllo TableLayoutPanel](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))  
  
9. [Procedura dettagliata: Creazione di un Windows Form ridimensionabile per l'immissione di dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Localizzazione](../../../standard/globalization-localization/localization.md)
