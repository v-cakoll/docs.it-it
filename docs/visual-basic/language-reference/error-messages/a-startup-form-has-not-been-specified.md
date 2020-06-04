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
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="c2ce3-102">Non è stato specificato un form di avvio</span><span class="sxs-lookup"><span data-stu-id="c2ce3-102">A startup form has not been specified</span></span>

<span data-ttu-id="c2ce3-103">L'applicazione usa la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe ma non specifica il modulo di avvio.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="c2ce3-104">Questa situazione può verificarsi se la casella di controllo **Abilita framework applicazione** è selezionata in Progettazione progetti, ma il **modulo di avvio** non è specificato.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="c2ce3-105">Per altre informazioni, vedere [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c2ce3-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2ce3-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c2ce3-106">To correct this error</span></span>  
  
1. <span data-ttu-id="c2ce3-107">Specificare un oggetto di avvio per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="c2ce3-108">Per altre informazioni, vedere [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c2ce3-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="c2ce3-109">Eseguire l'override del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> metodo per impostare la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> proprietà sul form di avvio.</span><span class="sxs-lookup"><span data-stu-id="c2ce3-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ce3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2ce3-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="c2ce3-111">Cenni preliminari sul modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2ce3-111">Overview of the Visual Basic Application Model</span></span>](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
