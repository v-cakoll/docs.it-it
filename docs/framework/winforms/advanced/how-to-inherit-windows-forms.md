---
title: 'Procedura: ereditare Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 275ae52a36ed9766e2569bd6c8ecdea78ea56e0b
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255082"
---
# <a name="how-to-inherit-windows-forms"></a>Procedura: ereditare Windows Form
La creazione di nuovi Windows Form mediante l'ereditarietà da form di base è un modo semplice di duplicare ciò che è stato creato senza ripetere ogni volta il medesimo processo di creazione di un form.  
  
 Per altre informazioni sull'ereditarietà di form in fase di progettazione tramite la finestra di dialogo **Selezione ereditarietà** e su come distinguere visivamente i livelli di sicurezza dei controlli ereditati, vedere [Procedura: Ereditare form tramite la finestra di dialogo Selezione ereditarietà](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Nota** per ereditare da un modulo, il file o lo spazio dei nomi contenente tale form deve essere incorporato in un file eseguibile o DLL. Per compilare il progetto, scegliere **Compila** dal menu **Compila**. È necessario aggiungere un riferimento allo spazio dei nomi anche alla classe che eredita il form. Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-inherit-a-form-programmatically"></a>Per ereditare un form a livello di codice  
  
1.  All'interno della classe aggiungere un riferimento allo spazio dei nomi che contiene il form da cui si vuole ereditare.  
  
2.  Nella definizione della classe aggiungere un riferimento al form da cui ereditare. Il riferimento deve includere lo spazio dei nomi che contiene il form, seguito da un punto, quindi il nome del form di base.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 Quando si ereditano i form, tenere presente che possono insorgere problemi relativi alla doppia chiamata a gestori eventi, perché ogni evento viene gestito sia dalla classe di base che dalla classe ereditata. Per informazioni su come evitare questo problema, vedere [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Inherits](~/docs/visual-basic/language-reference/statements/inherits-statement.md)  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [using](~/docs/csharp/language-reference/keywords/using.md)  
 [Effetti della modifica dell'aspetto di un modulo di base](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 [Ereditarietà visiva di Windows Form](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
