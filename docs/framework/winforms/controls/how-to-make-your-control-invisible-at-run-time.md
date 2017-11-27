---
title: 'Procedura: rendere invisibile il controllo in fase di esecuzione'
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
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 310750df0786eb07158909eb5e322369d157d1cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Procedura: rendere invisibile il controllo in fase di esecuzione
Vi sono casi quando si potrebbe desiderare di creare un controllo utente che non è visibile in fase di esecuzione. Ad esempio, potrebbe essere invisibile tranne quando l'avviso è stato emissione di un controllo che una sveglia. A tal fine, impostare il <xref:System.Windows.Forms.Control.Visible%2A> proprietà. Se il <xref:System.Windows.Forms.Control.Visible%2A> proprietà `true`, il controllo verrà visualizzato come di consueto. Se `false`, il controllo verrà nascosto. Anche se il controllo del codice può comunque eseguire invisibili, non sarà in grado di interagire con il controllo tramite l'interfaccia utente. Se si desidera creare un controllo invisibile in grado di rispondere all'input (ad esempio, clic del mouse) dell'utente, è necessario creare un controllo trasparente. Per ulteriori informazioni, vedere [assegnazione di uno sfondo trasparente al controllo](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).  
  
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
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [Sviluppo di controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Procedura: Assegnare uno sfondo trasparente al controllo](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
