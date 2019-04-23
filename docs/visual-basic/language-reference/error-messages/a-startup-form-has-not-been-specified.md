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
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="d373f-102">Non è stato specificato un form di avvio</span><span class="sxs-lookup"><span data-stu-id="d373f-102">A startup form has not been specified</span></span>
<span data-ttu-id="d373f-103">L'applicazione usa il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe ma non specificano il form di avvio.</span><span class="sxs-lookup"><span data-stu-id="d373f-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="d373f-104">Ciò può verificarsi se il **Abilita framework applicazione** casella di controllo è selezionata in Creazione progetti, ma il **form di avvio** non è specificato.</span><span class="sxs-lookup"><span data-stu-id="d373f-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="d373f-105">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d373f-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d373f-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d373f-106">To correct this error</span></span>  
  
1. <span data-ttu-id="d373f-107">Specificare un oggetto di avvio per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d373f-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="d373f-108">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d373f-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="d373f-109">Eseguire l'override di <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> per impostare il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> proprietà al form di avvio.</span><span class="sxs-lookup"><span data-stu-id="d373f-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d373f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d373f-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="d373f-111">Cenni preliminari sul modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d373f-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
