---
title: Modificare i bordi del modulo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 2c8eb25b44c7406e4312f432f2d69524346f94d6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739560"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Procedura: Modificare i bordi di Windows Form
Quando si stabiliscono l'aspetto e il comportamento di Windows Form, è possibile scegliere tra diversi stili bordo. Modificando la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A>, è possibile controllare il comportamento di ridimensionamento del form. Inoltre, l'impostazione di <xref:System.Windows.Forms.Form.FormBorderStyle%2A> influisce sul modo in cui la barra del titolo viene visualizzata e su quali pulsanti possono apparire sulla barra stessa. Per altre informazioni, vedere <xref:System.Windows.Forms.FormBorderStyle>.  
  
 In Visual Studio è disponibile supporto completo per questa attività.  
  
 Vedere anche [procedura: modificare i bordi di Windows Forms usando la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Per impostare lo stile bordo di Windows Form a livello di codice  
  
- Impostare la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A> sullo stile desiderato. Nell'esempio di codice seguente viene impostato lo stile del bordo del form `DlgBx1` su <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
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
  
     Vedere anche [procedura: creare finestre di dialogo in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).  
  
     Inoltre, se si è scelto uno stile del bordo per il form che fornisce pulsanti facoltativi di **riduzione a icona** e **Ingrandisci** , è possibile specificare se si desidera che uno o entrambi i pulsanti siano funzionanti. Questi pulsanti sono utili quando si desidera controllare da vicino l'esperienza utente. I pulsanti **Riduci a icona** e **Ingrandisci** sono abilitati per impostazione predefinita e la relativa funzionalità viene modificata tramite la finestra **proprietà** .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [Guida introduttiva a Windows Form](getting-started-with-windows-forms.md)
