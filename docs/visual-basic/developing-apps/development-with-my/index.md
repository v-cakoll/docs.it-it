---
title: Sviluppo con My (Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWpfExtension.Windows
dev_langs:
- VB
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3dae5e12baeb82c238381fb9e144c434816dcfb4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="development-with-my-visual-basic"></a><span data-ttu-id="01eb3-102">Sviluppo con My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01eb3-102">Development with My (Visual Basic)</span></span>
<span data-ttu-id="01eb3-103">Visual Basic fornisce nuove funzionalità per lo sviluppo rapido di applicazioni che migliorano la produttività e aumentano la facilità d'uso, garantendo al tempo stesso maggiore potenza.</span><span class="sxs-lookup"><span data-stu-id="01eb3-103">Visual Basic provides new features for rapid application development that improve productivity and ease of use while delivering power.</span></span> <span data-ttu-id="01eb3-104">Una di queste funzionalità, denominata `My`, consente di accedere a informazioni e istanze di oggetti predefinite correlate all'applicazione e al relativo ambiente di run-time.</span><span class="sxs-lookup"><span data-stu-id="01eb3-104">One of these features, called `My`, provides access to information and default object instances that are related to the application and its run-time environment.</span></span> <span data-ttu-id="01eb3-105">Queste informazioni sono organizzate in un formato riconoscibile tramite IntelliSense e delineato in modo logico in base all'uso.</span><span class="sxs-lookup"><span data-stu-id="01eb3-105">This information is organized in a format that is discoverable through IntelliSense and logically delineated according to use.</span></span>  
  
 <span data-ttu-id="01eb3-106">I membri di `My` di primo livello sono esposti come oggetti.</span><span class="sxs-lookup"><span data-stu-id="01eb3-106">Top-level members of `My` are exposed as objects.</span></span> <span data-ttu-id="01eb3-107">Ogni oggetto si comporta in modo analogo a uno spazio dei nomi o a una classe con membri `Shared` ed espone un set di membri correlati.</span><span class="sxs-lookup"><span data-stu-id="01eb3-107">Each object behaves similarly to a namespace or a class with `Shared` members, and it exposes a set of related members.</span></span>  
  
 <span data-ttu-id="01eb3-108">Questa tabella mostra gli oggetti `My` di primo livello e le relazioni tra tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="01eb3-108">This table shows the top-level `My` objects and their relationship to each other.</span></span>  
  
 <span data-ttu-id="01eb3-109">![Modello a oggetti per My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span><span class="sxs-lookup"><span data-stu-id="01eb3-109">![Object Model for My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01eb3-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="01eb3-110">In This Section</span></span>  
 [<span data-ttu-id="01eb3-111">Esecuzione di attività mediante My.Application, My.Computer e My.User</span><span class="sxs-lookup"><span data-stu-id="01eb3-111">Performing Tasks with My.Application, My.Computer, and My.User</span></span>](../../../visual-basic/developing-apps/development-with-my/performing-tasks-with-my-application-my-computer-and-my-user.md)  
 <span data-ttu-id="01eb3-112">Vengono descritti i tre principali oggetti `My`, `My.Application`, `My.Computer` e `My.User`, che consentono di accedere a informazioni e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="01eb3-112">Describes the three central `My` objects, `My.Application`, `My.Computer`, and `My.User`, which provide access to information and functionality</span></span>  
  
 [<span data-ttu-id="01eb3-113">Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices</span><span class="sxs-lookup"><span data-stu-id="01eb3-113">Default Object Instances Provided by My.Forms and My.WebServices</span></span>](../../../visual-basic/developing-apps/development-with-my/default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 <span data-ttu-id="01eb3-114">Vengono descritti gli oggetti `My.Forms` e `My.WebServices`, che consentono di accedere a form, origini dati e servizi Web XML usati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="01eb3-114">Describes the `My.Forms` and `My.WebServices` objects, which provide access to forms, data sources, and XML Web services used by your application.</span></span>  
  
 [<span data-ttu-id="01eb3-115">Sviluppo rapido di applicazioni con My.Resources e My.Settings</span><span class="sxs-lookup"><span data-stu-id="01eb3-115">Rapid Application Development with My.Resources and My.Settings</span></span>](../../../visual-basic/developing-apps/development-with-my/rapid-application-development-with-my-resources-and-my-settings.md)  
 <span data-ttu-id="01eb3-116">Vengono descritti gli oggetti `My.Resources` e `My.Settings`, che consentono di accedere alle risorse e alle impostazioni di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="01eb3-116">Describes the `My.Resources` and `My.Settings` objects, which provide access to an application's resources and settings.</span></span>  
  
 [<span data-ttu-id="01eb3-117">Cenni preliminari sul modello di applicazione Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01eb3-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="01eb3-118">Viene descritto il modello di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per l'avvio e l'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="01eb3-118">Describes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Application Startup/Shutdown model.</span></span>  
  
 [<span data-ttu-id="01eb3-119">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="01eb3-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="01eb3-120">Vengono forniti dettagli sulle caratteristiche di `My` disponibili per i diversi tipi di progetto.</span><span class="sxs-lookup"><span data-stu-id="01eb3-120">Gives details on which `My` features are available in different project types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01eb3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01eb3-121">See Also</span></span>  
 <span data-ttu-id="01eb3-122"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></span><span class="sxs-lookup"><span data-stu-id="01eb3-122"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></span></span>   
 <span data-ttu-id="01eb3-123"><xref:Microsoft.VisualBasic.Devices.Computer></span><span class="sxs-lookup"><span data-stu-id="01eb3-123"><xref:Microsoft.VisualBasic.Devices.Computer></span></span>   
 <span data-ttu-id="01eb3-124"><xref:Microsoft.VisualBasic.ApplicationServices.User></span><span class="sxs-lookup"><span data-stu-id="01eb3-124"><xref:Microsoft.VisualBasic.ApplicationServices.User></span></span>   
 <span data-ttu-id="01eb3-125">[Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) </span><span class="sxs-lookup"><span data-stu-id="01eb3-125">[My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md) </span></span>  
 <span data-ttu-id="01eb3-126">[Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) </span><span class="sxs-lookup"><span data-stu-id="01eb3-126">[My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md) </span></span>  
 [<span data-ttu-id="01eb3-127">Dipendenza di My dal tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="01eb3-127">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)

