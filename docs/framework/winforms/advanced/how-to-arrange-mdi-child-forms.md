---
title: 'Procedura: disporre i form figlio MDI'
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
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a0a32f6a97e02db8e395db504f36bb5270b195c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-arrange-mdi-child-forms"></a>Procedura: disporre i form figlio MDI
Le applicazioni hanno spesso dei comandi di menu per azioni quali Affianca, Sovrapponi e Disponi che controllano il layout dei form figlio MDI aperti. È possibile usare il metodo <xref:System.Windows.Forms.Form.LayoutMdi%2A> con uno dei valori di enumerazione <xref:System.Windows.Forms.MdiLayout> per ridisporre i form figlio in un form padre MDI.  
  
 I valori di enumerazione <xref:System.Windows.Forms.MdiLayout> visualizzano i form figlio sovrapposti, affiancati orizzontalmente o verticalmente o sotto forma di icone disposte nella parte inferiore del form MDI. Questi valori hanno lo stesso effetto dei comandi di Windows **Sovrapponi finestre**, **Mostra le finestre affiancate**, **Mostra le finestre in pila**, e **Mostra il desktop** , rispettivamente.  
  
 Spesso questi metodi vengono usati come gestori eventi chiamati da un evento della voce di menu <xref:System.Windows.Forms.Control.Click>. In questo modo, una voce di menu con testo "Sovrapponi le finestre" può avere l'effetto desiderato sulle finestre figlio MDI.  
  
### <a name="to-arrange-child-forms"></a>Per disporre i form figlio  
  
1.  In un metodo usare il metodo <xref:System.Windows.Forms.Form.LayoutMdi%2A> per impostare l'enumerazione <xref:System.Windows.Forms.MdiLayout> per il form padre MDI. Nel seguente esempio viene usato il valore di enumerazione <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> per le finestre figlio del form padre MDI (`Form1`). L'enumerazione viene utilizzata nel codice durante il gestore eventi per il <xref:System.Windows.Forms.Control.Click> evento del **Sovrapponi le finestre** voce di menu.  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  È anche possibile affiancare le finestre e disporle sotto forma di icona modificando i valori di enumerazione <xref:System.Windows.Forms.MdiLayout> usati.  
  
2.  Se si usa Visual C#, inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Procedura: Creare form padre MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Procedura: Creare form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Procedura: Determinare il figlio MDI attivo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Procedura: Inviare dati al figlio MDI attivo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
