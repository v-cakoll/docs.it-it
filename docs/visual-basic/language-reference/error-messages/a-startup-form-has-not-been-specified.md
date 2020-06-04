---
title: Non è stato specificato un form di avvio
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 058deb1378ed9218274ae20c8340178f7c8fa58c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409907"
---
# <a name="a-startup-form-has-not-been-specified"></a>Non è stato specificato un form di avvio

L'applicazione usa la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe ma non specifica il modulo di avvio.  
  
 Questa situazione può verificarsi se la casella di controllo **Abilita framework applicazione** è selezionata in Progettazione progetti, ma il **modulo di avvio** non è specificato. Per altre informazioni, vedere [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Specificare un oggetto di avvio per l'applicazione.  
  
     Per altre informazioni, vedere [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2. Eseguire l'override del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> metodo per impostare la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> proprietà sul form di avvio.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Cenni preliminari sul modello di applicazione Visual Basic](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
