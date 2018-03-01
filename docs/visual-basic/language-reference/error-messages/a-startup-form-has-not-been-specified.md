---
title: "Non è stato specificato un form di avvio"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdffc182ee66497d68aafb7dc37cfef75b4d2e9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="3ced7-102">Non è stato specificato un form di avvio</span><span class="sxs-lookup"><span data-stu-id="3ced7-102">A startup form has not been specified</span></span>
<span data-ttu-id="3ced7-103">L'applicazione utilizza la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe ma non specifica il form di avvio.</span><span class="sxs-lookup"><span data-stu-id="3ced7-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="3ced7-104">Ciò può verificarsi se il **Attiva framework applicazione** casella di controllo è selezionata nella finestra di progettazione di progetto, ma il **form di avvio** non è specificato.</span><span class="sxs-lookup"><span data-stu-id="3ced7-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="3ced7-105">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3ced7-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3ced7-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3ced7-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="3ced7-107">Specificare un oggetto di avvio per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ced7-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="3ced7-108">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3ced7-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="3ced7-109">Eseguire l'override di <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> per impostare il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> proprietà al form di avvio.</span><span class="sxs-lookup"><span data-stu-id="3ced7-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ced7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ced7-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [<span data-ttu-id="3ced7-111">Cenni preliminari sul modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3ced7-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
