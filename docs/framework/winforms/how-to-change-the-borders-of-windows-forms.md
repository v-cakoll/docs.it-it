---
title: 'Procedura: modificare i bordi di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: e04234b4f2f18738567c3f9846d8ae0c94780fcb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535881"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Procedura: modificare i bordi di Windows Form
Quando si stabiliscono l'aspetto e il comportamento di Windows Form, è possibile scegliere tra diversi stili bordo. Modificando la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A>, è possibile controllare il comportamento di ridimensionamento del form. Inoltre, l'impostazione di <xref:System.Windows.Forms.Form.FormBorderStyle%2A> influisce sul modo in cui la barra del titolo viene visualizzata e su quali pulsanti possono apparire sulla barra stessa. Per altre informazioni, vedere <xref:System.Windows.Forms.FormBorderStyle>.  
  
 In Visual Studio è disponibile supporto completo per questa attività.  
  
 Vedere anche [procedura: modificare i bordi di Windows Form usando la finestra di progettazione](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Per impostare lo stile bordo di Windows Form a livello di codice  
  
-   Impostare la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A> sullo stile desiderato. Esempio di codice seguente imposta lo stile del bordo del form `DlgBx1` a <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     Vedere anche [procedura: creare finestre di dialogo in fase di progettazione](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).  
  
     Inoltre, se si è scelto un stile del bordo per il modulo che fornisce facoltativo **Riduci a icona** e **Ingrandisci** pulsanti, è possibile specificare se si desidera che uno o entrambi i pulsanti debbano essere funzionali. Questi pulsanti sono utili quando si desidera controllare da vicino l'esperienza utente. Il **Riduci a icona** e **Ingrandisci** pulsanti sono abilitati per impostazione predefinita e le relative funzionalità viene modificato tramite il **proprietà** finestra.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [Guida introduttiva a Windows Form](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
