---
title: Non è stato specificato un form di avvio
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 2bbae640ca65c95411cae24a9506fe2076b62cba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296472"
---
# <a name="a-startup-form-has-not-been-specified"></a>Non è stato specificato un form di avvio
L'applicazione usa il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe ma non specificano il form di avvio.  
  
 Ciò può verificarsi se il **Abilita framework applicazione** casella di controllo è selezionata in Creazione progetti, ma il **form di avvio** non è specificato. Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Specificare un oggetto di avvio per l'applicazione.  
  
     Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2. Eseguire l'override di <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> per impostare il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> proprietà al form di avvio.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Cenni preliminari sul modello di applicazione Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
