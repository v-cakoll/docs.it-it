---
title: Distribuzione di applicazioni che fanno riferimento a controlli Power Pack (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ad1aba4f2e725abbe560f0c71fbb543e15741200
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="3c668-102">Distribuzione di applicazioni che fanno riferimento a controlli Power Pack (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="3c668-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="3c668-103">Se si desidera distribuire un'applicazione che fa riferimento a controlli Power Pack (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), i controlli devono essere installati nel computer di destinazione.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> </xref:Microsoft.VisualBasic.PowerPacks.OvalShape> </xref:Microsoft.VisualBasic.PowerPacks.LineShape></span><span class="sxs-lookup"><span data-stu-id="3c668-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="3c668-104">Installare i controlli Power Pack come prerequisito</span><span class="sxs-lookup"><span data-stu-id="3c668-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="3c668-105">Per distribuire correttamente un'applicazione, è necessario distribuire anche tutti i componenti a cui viene fatto riferimento dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3c668-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="3c668-106">Il processo di installazione dei componenti prerequisiti è noto come *bootstrap*.</span><span class="sxs-lookup"><span data-stu-id="3c668-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="3c668-107">Quando [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] è installato nel computer di sviluppo, un Power Pack di avvio automatico viene aggiunto per il [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] directory di avvio automatico.</span><span class="sxs-lookup"><span data-stu-id="3c668-107">When [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="3c668-108">Questo pacchetto sarà disponibile quando si seguono le procedure per l'aggiunta di prerequisiti per la [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] o distribuzione di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="3c668-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="3c668-109">Per impostazione predefinita, i componenti con bootstrap vengono distribuiti dallo stesso percorso del pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="3c668-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="3c668-110">In alternativa, è possibile scegliere di distribuire i componenti da un URL o un percorso di condivisione file, da cui gli utenti possono scaricarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3c668-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c668-111">Per installare i componenti con bootstrap, l'utente può richiedere autorizzazioni amministrative o di tipo simile per il computer.</span><span class="sxs-lookup"><span data-stu-id="3c668-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="3c668-112">Per [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applicazioni, ciò significa che l'utente dovrà disporre di autorizzazioni amministrative per installare l'applicazione, indipendentemente dal livello di sicurezza specificato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3c668-112">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="3c668-113">Dopo l'installazione dell'applicazione, l'utente può eseguire l'applicazione senza autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="3c668-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="3c668-114">Durante l'installazione, agli utenti verranno richiesto di installare i controlli Power Pack se non sono presenti nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3c668-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="3c668-115">In alternativa al bootstrap, è possibile distribuire preventivamente i controlli Power Pack utilizzando un sistema di distribuzione software elettronico, ad esempio Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="3c668-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c668-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c668-116">See also</span></span>  
 <span data-ttu-id="3c668-117">[Procedura: installare i prerequisiti con un'applicazione ClickOnce](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="3c668-117">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="3c668-118"> [Controlli Visual Basic Power Pack](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span><span class="sxs-lookup"><span data-stu-id="3c668-118"> [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span></span>
