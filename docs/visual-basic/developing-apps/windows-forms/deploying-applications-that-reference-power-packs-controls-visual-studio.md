---
title: Distribuzione di applicazioni che fanno riferimento a controlli Power Pack (Visual Studio)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2a9562acf05cd27eed7bc1ad963845af9a7ca5f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="da78a-102">Distribuzione di applicazioni che fanno riferimento a controlli Power Pack (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="da78a-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="da78a-103">Se si desidera distribuire un'applicazione che fa riferimento ai controlli Power Pack (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), i controlli devono essere installati nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da78a-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="da78a-104">Installazione dei controlli Power Pack come prerequisito</span><span class="sxs-lookup"><span data-stu-id="da78a-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="da78a-105">Per distribuire correttamente un'applicazione, è necessario distribuire anche tutti i componenti a cui viene fatto riferimento dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da78a-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="da78a-106">Il processo di installazione dei componenti prerequisiti è noto come *bootstrap*.</span><span class="sxs-lookup"><span data-stu-id="da78a-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="da78a-107">Quando [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] è installato nel computer di sviluppo, un Power Pack relativo pacchetto viene aggiunto per il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] directory del programma di avvio.</span><span class="sxs-lookup"><span data-stu-id="da78a-107">When [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] bootstrapper directory.</span></span> <span data-ttu-id="da78a-108">Questo pacchetto sarà quindi disponibile quando si eseguono le procedure per l'aggiunta dei prerequisiti per la distribuzione tramite [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] o Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="da78a-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="da78a-109">Per impostazione predefinita, i componenti con bootstrap vengono distribuiti dallo stesso percorso del pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="da78a-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="da78a-110">In alternativa, è possibile scegliere di distribuire i componenti da un URL o un percorso di condivisione file, da cui gli utenti possono scaricarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="da78a-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da78a-111">Per installare i componenti con bootstrap, l'utente può richiedere autorizzazioni amministrative o di tipo simile per il computer.</span><span class="sxs-lookup"><span data-stu-id="da78a-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="da78a-112">Per le applicazioni [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] , questo significa che l'utente dovrà disporre di autorizzazioni amministrative per installare l'applicazione, indipendentemente dal livello di sicurezza specificato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da78a-112">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="da78a-113">Dopo l'installazione dell'applicazione, l'utente può eseguire l'applicazione senza autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="da78a-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="da78a-114">Durante l'installazione, agli utenti verranno richiesto di installare i controlli Power Pack se non sono presenti nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da78a-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="da78a-115">In alternativa al bootstrap, è possibile pre-distribuire i controlli Power Pack utilizzando un sistema di distribuzione software elettronico, ad esempio Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="da78a-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da78a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da78a-116">See also</span></span>  
 [<span data-ttu-id="da78a-117">Procedura: Installare i prerequisiti con un'applicazione ClickOnce</span><span class="sxs-lookup"><span data-stu-id="da78a-117">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="da78a-118">Controlli di Visual Basic Power Pack</span><span class="sxs-lookup"><span data-stu-id="da78a-118">Visual Basic Power Packs Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
