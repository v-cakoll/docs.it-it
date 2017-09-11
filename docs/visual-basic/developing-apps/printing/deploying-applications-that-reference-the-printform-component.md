---
title: Distribuzione di applicazioni che fanno riferimento al componente PrintForm (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b625e0c58653f1ee9a2d263d7d2d29ad3b2e3c1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="15378-102">Distribuzione di applicazioni che fanno riferimento al componente PrintForm (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15378-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="15378-103">Se si desidera distribuire un'applicazione che fa riferimento il <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente, il componente deve essere installato nel computer di destinazione.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="15378-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="15378-104">I controlli PowerPacks non sono più inclusi in Visual Studio, ma è possibile scaricarli dall' [Area download](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="15378-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="15378-105">Installazione di PrintForm come prerequisito</span><span class="sxs-lookup"><span data-stu-id="15378-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="15378-106">Per distribuire correttamente un'applicazione, è necessario distribuire anche tutti i componenti a cui viene fatto riferimento dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="15378-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="15378-107">Il processo di installazione dei componenti prerequisiti è noto come *bootstrap*.</span><span class="sxs-lookup"><span data-stu-id="15378-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="15378-108">Quando il <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente è installato nel computer di sviluppo, viene aggiunto un pacchetto di programma di avvio automatico di Microsoft Visual Basic Power Pack per il [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] directory bootstrapper.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="15378-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="15378-109">Questo pacchetto sarà disponibile quando si seguono le procedure per l'aggiunta di prerequisiti per la [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] o distribuzione di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="15378-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="15378-110">Per impostazione predefinita, i componenti con bootstrap vengono distribuiti dallo stesso percorso del pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="15378-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="15378-111">In alternativa, è possibile scegliere di distribuire i componenti da un URL o un percorso di condivisione file, da cui gli utenti possono scaricarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="15378-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15378-112">Per installare i componenti con bootstrap, l'utente può richiedere autorizzazioni amministrative o di tipo simile per il computer.</span><span class="sxs-lookup"><span data-stu-id="15378-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="15378-113">Per [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applicazioni, ciò significa che l'utente dovrà disporre di autorizzazioni amministrative per installare l'applicazione, indipendentemente dal livello di sicurezza specificato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="15378-113">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="15378-114">Dopo l'installazione dell'applicazione, l'utente può eseguire l'applicazione senza autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="15378-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="15378-115">Durante l'installazione, verranno richiesto agli utenti di installare il <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente se non è presente nel computer di destinazione.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="15378-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="15378-116">In alternativa al bootstrap, è possibile distribuire il <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>componente tramite un sistema electronic software distribution come Microsoft Systems Management Server.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="15378-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15378-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15378-117">See also</span></span>  
 <span data-ttu-id="15378-118">[Procedura: installare i prerequisiti con un'applicazione ClickOnce](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="15378-118">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="15378-119"> [Componente PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)</span><span class="sxs-lookup"><span data-stu-id="15378-119"> [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)</span></span>
