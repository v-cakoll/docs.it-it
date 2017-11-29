---
title: Personalizzazione di progetti ed estensione di oggetti My in Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 397b345239f8707f0129ac14ab426f93372b4010
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="7ef20-102">Personalizzazione di progetti ed estensione di oggetti My in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef20-102">Customizing Projects and Extending My with Visual Basic</span></span>
<span data-ttu-id="7ef20-103">È possibile personalizzare i modelli di progetto per fornire ulteriori `My` oggetti.</span><span class="sxs-lookup"><span data-stu-id="7ef20-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="7ef20-104">Questo semplifica per gli altri sviluppatori trovare e utilizzare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7ef20-104">This makes it easy for other developers to find and use your objects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ef20-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7ef20-105">In This Section</span></span>  
 [<span data-ttu-id="7ef20-106">Estensione di My Namespace in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef20-106">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)  
 <span data-ttu-id="7ef20-107">Viene descritto come aggiungere membri personalizzati e i valori per il `My` spazio dei nomi in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7ef20-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>  
  
 [<span data-ttu-id="7ef20-108">Assemblaggio e distribuzione delle estensioni My personalizzate</span><span class="sxs-lookup"><span data-stu-id="7ef20-108">Packaging and Deploying Custom My Extensions</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="7ef20-109">Viene descritto come pubblicare personalizzato `My` estensioni spazio dei nomi utilizzando modelli di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7ef20-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>  
  
 [<span data-ttu-id="7ef20-110">Estensione del modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef20-110">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="7ef20-111">Viene descritto come specificare le estensioni personalizzate per il modello di applicazione eseguendo l'override di membri del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe.</span><span class="sxs-lookup"><span data-stu-id="7ef20-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>  
  
 [<span data-ttu-id="7ef20-112">Personalizzazione degli oggetti disponibili in My</span><span class="sxs-lookup"><span data-stu-id="7ef20-112">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="7ef20-113">Viene descritto come controllare quali `My` gli oggetti sono abilitati impostando la costante di compilazione condizionale MyType del progetto.</span><span class="sxs-lookup"><span data-stu-id="7ef20-113">Describes how to control which `My` objects are enabled by setting your project's _MYTYPE conditional-compilation constant.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7ef20-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7ef20-114">Related Sections</span></span>  
 [<span data-ttu-id="7ef20-115">Sviluppo con My</span><span class="sxs-lookup"><span data-stu-id="7ef20-115">Development with My</span></span>](../../../visual-basic/developing-apps/development-with-my/index.md)  
 <span data-ttu-id="7ef20-116">Descrive quale `My` gli oggetti sono disponibili in diversi tipi di progetto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7ef20-116">Describes which `My` objects are available in different project types by default.</span></span>  
  
 [<span data-ttu-id="7ef20-117">Cenni preliminari sul modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef20-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="7ef20-118">Viene descritto il modello di Visual Basic per controllare il comportamento delle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7ef20-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="7ef20-119">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="7ef20-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="7ef20-120">Descrive quale `My` gli oggetti sono disponibili in diversi tipi di progetto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7ef20-120">Describes which `My` objects are available in different project types by default.</span></span>  
  
 [<span data-ttu-id="7ef20-121">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="7ef20-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="7ef20-122">Viene descritto come il compilatore utilizza la compilazione condizionale per selezionare particolari sezioni di codice per compilare ed escludere altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="7ef20-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>  
  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="7ef20-123">Viene descritto il `My` oggetto che fornisce le proprietà, metodi ed eventi correlati all'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="7ef20-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef20-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef20-124">See Also</span></span>  
 [<span data-ttu-id="7ef20-125">Sviluppo di applicazioni con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef20-125">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
