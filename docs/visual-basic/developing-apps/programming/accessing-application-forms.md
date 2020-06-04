---
title: Accesso ai moduli dell'applicazione
ms.date: 07/20/2015
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
ms.openlocfilehash: 44f98632fd2fd6c4c087a78b805d5b7da750df87
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410205"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="eab36-102">Accesso ai form di un'applicazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eab36-102">Accessing Application Forms (Visual Basic)</span></span>

<span data-ttu-id="eab36-103">L'oggetto `My.Forms` rappresenta un modo semplice di accedere a un'istanza di ogni Windows Form dichiarato nel progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eab36-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="eab36-104">È anche possibile usare le proprietà dell'oggetto `My.Application` per visualizzare la schermata iniziale e il modulo principale dell'applicazione e per ottenere un elenco dei moduli aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eab36-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="eab36-105">Attività</span><span class="sxs-lookup"><span data-stu-id="eab36-105">Tasks</span></span>  

 <span data-ttu-id="eab36-106">La tabella seguente elenca esempi che illustrano come accedere ai moduli di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eab36-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="eab36-107">A</span><span class="sxs-lookup"><span data-stu-id="eab36-107">To</span></span>|<span data-ttu-id="eab36-108">Vedere</span><span class="sxs-lookup"><span data-stu-id="eab36-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="eab36-109">Accedere a un modulo da un altro modulo di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eab36-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="eab36-110">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="eab36-110">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="eab36-111">Visualizzare i titoli di tutti i moduli aperti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eab36-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="eab36-112">Aggiornare la schermata iniziale con informazioni sullo stato all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eab36-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="eab36-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eab36-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="eab36-114">Oggetto My.Forms</span><span class="sxs-lookup"><span data-stu-id="eab36-114">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
