---
title: 'Procedura: Impostare la maschera di input'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949140"
---
# <a name="how-to-set-the-input-mask"></a>Procedura: Impostare la maschera di input
Il controllo casella di testo mascherato è un controllo casella di testo avanzato che supporta una sintassi dichiarativa per accettare o rifiutare l'input dell'utente. Impostando la proprietà Mask, è possibile specificare l'input dell'utente consentito senza scrivere alcuna logica di convalida personalizzata nell'applicazione. Per ulteriori informazioni, vedere la sezione Osservazioni della <xref:System.Windows.Forms.MaskedTextBox> classe.  
  
## <a name="setting-the-mask-property-manually"></a>Impostazione manuale della proprietà Mask  
 Se si ha familiarità con i caratteri supportati dalla proprietà Mask, è possibile immetterla manualmente. Per un riepilogo dei caratteri supportati dalla proprietà Mask, vedere la sezione Osservazioni della <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
### <a name="to-set-the-mask-property-manually"></a>Per impostare manualmente la proprietà Mask  
  
1. In visualizzazione **progettazione** selezionare un <xref:System.Windows.Forms.MaskedTextBox>.  
  
2. Nella finestra **Proprietà** individuare la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
3. Digitare la maschera desiderata. Ad esempio, digitare `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Uso della finestra di dialogo Maschera di input  
 La finestra di dialogo Maschera di input fornisce alcune maschere di input predefinite. È anche possibile modificare le maschere predefinite o immettere manualmente la propria maschera.  
  
### <a name="to-open-the-input-mask-dialog-box"></a>Per aprire la finestra di dialogo Maschera di input  
  
1. In visualizzazione **progettazione** selezionare un <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1. Fare clic sullo smart tag per aprire il pannello **attività di MaskedTextBox** .  
  
    2. Fare clic su **Imposta maschera**.  
  
     \- oppure -  
  
    1. Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
    2. Fare clic sul pulsante con i puntini di sospensione nella colonna valore proprietà.  
  
     Verrà visualizzata la finestra di dialogo **maschera di input** .  
  
### <a name="to-use-the-input-mask-dialog-box"></a>Per utilizzare la finestra di dialogo Maschera di input  
  
1. Opzionale Fare clic su una delle maschere predefinite nell'elenco.  
  
2. Opzionale Modificare la maschera predefinita nella casella **maschera** .  
  
3. Opzionale Digitare una nuova maschera nella casella **maschera** . Ovvero, non è necessario utilizzare una delle maschere predefinite.  
  
    > [!NOTE]
    > Nella casella Anteprima vengono visualizzati i caratteri visualizzati dall'utente in <xref:System.Windows.Forms.MaskedTextBox>. Questi caratteri sono una guida che consente all'utente di immettere correttamente i dati.  
  
4. Selezionare o deselezionare la casella di controllo **USA ValidatingType** . La casella di controllo **use ValidatingType** specifica se un tipo di dati viene utilizzato per verificare l'input dei dati da parte dell'utente. Per altre informazioni, vedere la proprietà <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.  
  
5. Fare clic su **OK**.  
  
     La maschera viene immessa nella proprietà **mask** nella finestra **Proprietà** .  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Utilizzo del controllo MaskedTextBox](walkthrough-working-with-the-maskedtextbox-control.md)
