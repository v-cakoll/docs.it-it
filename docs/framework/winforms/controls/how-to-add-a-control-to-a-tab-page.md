---
title: 'Procedura: Aggiungere un controllo a una scheda'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: b42845ab996c0985fe6a48ac588e6d706905faac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195852"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Procedura: Aggiungere un controllo a una scheda
È possibile usare i moduli di Windows <xref:System.Windows.Forms.TabControl> per visualizzare altri controlli in modo organizzato. La procedura seguente viene illustrato come aggiungere un pulsante alla prima scheda. Per informazioni sull'aggiunta di un'icona di parte dell'etichetta di una pagina della scheda, vedere [come: Modificare l'aspetto del controllo TabControl Windows Form](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Per aggiungere un controllo a livello di codice  
  
1.  Usare la <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> della raccolta restituita dal metodo di <xref:System.Windows.Forms.Control.Controls%2A> proprietà di <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TabControl](tabcontrol-control-windows-forms.md)
- [Panoramica del controllo TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedura: Modificare l'aspetto di TabControl di Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [Procedura: Disabilitare le schede](how-to-disable-tab-pages.md)
- [Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
