---
title: 'Procedura: Rendere invisibile il controllo in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: 06283a93c3b88d2febc1d64797139eee62661b42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201650"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Procedura: Rendere invisibile il controllo in fase di esecuzione
Vi sono casi quando si potrebbe voler creare un controllo utente che non è visibile in fase di esecuzione. Ad esempio, potrebbe essere invisibile tranne quando l'allarme è stato suona un controllo che una sveglia. Questo avviene facilmente impostando il <xref:System.Windows.Forms.Control.Visible%2A> proprietà. Se il <xref:System.Windows.Forms.Control.Visible%2A> è di proprietà `true`, il controllo verrà visualizzato come di consueto. Se `false`, il controllo sarà nascosto. Anche se nel controllo del codice può comunque eseguire nonostante sia invisibile, non sarà in grado di interagire con il controllo tramite l'interfaccia utente. Se si desidera creare un controllo invisibile in grado di rispondere all'input (ad esempio, clic del mouse) dell'utente, è necessario creare un controllo trasparente. Per altre informazioni, vedere [assegnazione di uno sfondo trasparente al controllo](how-to-give-your-control-a-transparent-background.md).  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>Per rendere invisibile il controllo in fase di esecuzione  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.Control.Visible%2A> su `false`.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Visible%2A>
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Procedura: Assegnare uno sfondo trasparente al controllo](how-to-give-your-control-a-transparent-background.md)
