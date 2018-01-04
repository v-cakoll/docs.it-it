---
title: 'Procedura: impostare la maschera di input'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.MaskPropertyEditor
helpviewer_keywords: MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 68bfe46462a374899a0782903804edea0e93f161
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-input-mask"></a>Procedura: impostare la maschera di input
Il controllo casella di testo mascherata è un controllo casella di testo avanzato che supporta una sintassi dichiarativa per accettare o rifiutare l'input dell'utente. Impostando la proprietà maschera, è possibile specificare l'input dell'utente consentito senza scrivere una logica di convalida personalizzato nell'applicazione. Per ulteriori informazioni, vedere la sezione Note della <xref:System.Windows.Forms.MaskedTextBox> classe.  
  
## <a name="setting-the-mask-property-manually"></a>Impostare la proprietà maschera manualmente  
 Se si ha familiarità con i caratteri che supporta la proprietà maschera, è possibile immettere manualmente. Per un riepilogo dei caratteri che supporta la proprietà maschera, vedere la sezione Note della <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
#### <a name="to-set-the-mask-property-manually"></a>Impostare la proprietà maschera manualmente  
  
1.  In **progettazione** visualizzazione, selezionare un <xref:System.Windows.Forms.MaskedTextBox>.  
  
2.  Nel **proprietà** finestra, individuare il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
3.  Digitare la maschera che si desidera. Ad esempio, digitare `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Nella finestra di dialogo maschera di Input  
 La finestra di dialogo maschera di Input fornisce alcune maschere di input predefinite. È inoltre possibile modificare le maschere predefinite o immettere manualmente la propria mask.  
  
#### <a name="to-open-the-input-mask-dialog-box"></a>Per aprire la finestra di dialogo maschera di Input  
  
1.  In **progettazione** visualizzazione, selezionare un <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1.  Fare clic sullo smart tag per aprire la **attività MaskedTextBox** pannello.  
  
    2.  Fare clic su **Imposta maschera**.  
  
     \- oppure -  
  
    1.  Nel **proprietà** finestra, seleziona il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
    2.  Fare clic sul pulsante con puntini di sospensione nella colonna valore della proprietà.  
  
     Il **maschera di Input** viene visualizzata la finestra di dialogo.  
  
#### <a name="to-use-the-input-mask-dialog-box"></a>Utilizzare la finestra di dialogo maschera di Input  
  
1.  (Facoltativo) Fare clic su una delle maschere predefinite nell'elenco.  
  
2.  (Facoltativo) Modificare la maschera predefinita nel **Mask** casella.  
  
3.  (Facoltativo) Digitare una nuova maschera nel **Mask** casella. Vale a dire, non è necessario utilizzare una delle maschere predefinite.  
  
    > [!NOTE]
    >  Finestra di anteprima vengono visualizzati i caratteri che l'utente visualizza nel <xref:System.Windows.Forms.MaskedTextBox>. Questi caratteri sono una Guida per consentire all'utente di immettere correttamente i dati.  
  
4.  Selezionare o deselezionare il **utilizza ValidatingType** casella di controllo. Il **utilizza ValidatingType** casella di controllo specifica se un tipo di dati viene utilizzato per verificare l'input di dati dall'utente. Per altre informazioni, vedere la proprietà <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.  
  
5.  Fare clic su **OK**.  
  
     La maschera viene immessa nel **Mask** proprietà il **proprietà** finestra.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: Utilizzo del controllo MaskedTextBox](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
