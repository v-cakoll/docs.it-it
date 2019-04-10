---
title: 'Procedura: Impostare la maschera di input'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06eaf68fef167d63e6f8404dd5049f5445881d24
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331468"
---
# <a name="how-to-set-the-input-mask"></a>Procedura: Impostare la maschera di input
Il controllo casella di testo mascherata è un controllo casella di testo avanzato che supporta una sintassi dichiarativa per accettare o rifiutare l'input dell'utente. Impostando la proprietà Mask, è possibile specificare l'input dell'utente consentita senza scrivere una logica di convalida personalizzato nell'applicazione. Per altre informazioni, vedere la sezione Osservazioni del <xref:System.Windows.Forms.MaskedTextBox> classe.  
  
## <a name="setting-the-mask-property-manually"></a>Impostare la proprietà Mask manualmente  
 Se si ha familiarità con i caratteri che supporta la proprietà Mask, è possibile immetterlo manualmente. Per un riepilogo dei caratteri che supporta la proprietà Mask, vedere la sezione Osservazioni del <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
#### <a name="to-set-the-mask-property-manually"></a>Per impostare la proprietà Mask manualmente  
  
1. Nelle **Design** visualizzazione, selezionare un <xref:System.Windows.Forms.MaskedTextBox>.  
  
2. Nel **delle proprietà** finestra, individuare il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
3. Tipo di maschera che si desidera. Ad esempio, digitare `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Nella finestra di dialogo maschera di Input  
 La finestra di dialogo di maschera di Input offre alcune maschere di input predefinite. È anche possibile modificare le maschere predefinite o immettere manualmente il proprio filtro.  
  
#### <a name="to-open-the-input-mask-dialog-box"></a>Per aprire la finestra di dialogo di maschera di Input  
  
1. Nelle **Design** visualizzazione, selezionare un <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1.  Clic sullo smart tag per aprire la **MaskedTextBox attività** pannello.  
  
    2.  Fare clic su **Imposta maschera**.  
  
     \- oppure -  
  
    1.  Nel **delle proprietà** finestra, seleziona il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
    2.  Fare clic sui puntini di sospensione nella colonna valore della proprietà.  
  
     Il **maschera di Input** verrà visualizzata la finestra di dialogo.  
  
#### <a name="to-use-the-input-mask-dialog-box"></a>Usare la finestra di dialogo di maschera di Input  
  
1. (Facoltativo) Fare clic su una delle maschere predefinite nell'elenco.  
  
2. (Facoltativo) Modificare la maschera predefinita in di **Mask** casella.  
  
3. (Facoltativo) Digitare una nuova maschera nel **Mask** casella. Vale a dire, non è necessario usare una delle maschere predefinite.  
  
    > [!NOTE]
    >  La finestra di anteprima vengono visualizzati i caratteri che l'utente vede nel <xref:System.Windows.Forms.MaskedTextBox>. Questi caratteri sono una Guida che consente all'utente di immettere correttamente i dati.  
  
4. Selezionare o deselezionare i **utilizza ValidatingType** casella di controllo. Il **utilizza ValidatingType** casella di controllo specifica se un tipo di dati viene utilizzato per verificare l'input di dati dall'utente. Per altre informazioni, vedere la proprietà <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.  
  
5. Fare clic su **OK**.  
  
     La maschera viene immesso nel **maschera** proprietà nel **proprietà** finestra.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Uso del controllo MaskedTextBox](walkthrough-working-with-the-maskedtextbox-control.md)
