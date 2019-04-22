---
title: Accesso ai form di un'applicazione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
ms.openlocfilehash: 85de915f4dc9a79e0161411951062afbeb764513
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821686"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="f66fb-102">Accesso ai form di un'applicazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f66fb-102">Accessing Application Forms (Visual Basic)</span></span>
<span data-ttu-id="f66fb-103">L'oggetto `My.Forms` rappresenta un modo semplice di accedere a un'istanza di ogni Windows Form dichiarato nel progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f66fb-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="f66fb-104">È anche possibile usare le proprietà dell'oggetto `My.Application` per visualizzare la schermata iniziale e il modulo principale dell'applicazione e per ottenere un elenco dei moduli aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f66fb-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="f66fb-105">Attività</span><span class="sxs-lookup"><span data-stu-id="f66fb-105">Tasks</span></span>  
 <span data-ttu-id="f66fb-106">La tabella seguente elenca esempi che illustrano come accedere ai moduli di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f66fb-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="f66fb-107">A</span><span class="sxs-lookup"><span data-stu-id="f66fb-107">To</span></span>|<span data-ttu-id="f66fb-108">Vedere</span><span class="sxs-lookup"><span data-stu-id="f66fb-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="f66fb-109">Accedere a un modulo da un altro modulo di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f66fb-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="f66fb-110">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="f66fb-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="f66fb-111">Visualizzare i titoli di tutti i moduli aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f66fb-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="f66fb-112">Aggiornare la schermata iniziale con informazioni sullo stato all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f66fb-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="f66fb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f66fb-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="f66fb-114">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="f66fb-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
