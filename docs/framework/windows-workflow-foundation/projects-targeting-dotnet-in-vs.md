---
title: Scrittura di progetti destinati a .NET Framework 3.0 e 3.5 in Visual Studio 2010
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 95348ad57bb4dce1799c1ddf741b69f0e2b969af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a><span data-ttu-id="1c982-102">Scrittura di progetti destinati a .NET Framework 3.0 e 3.5 in Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="1c982-102">Writing Projects Targeting the .NET Framework 3.0 and 3.5 in Visual Studio 2010</span></span>
<span data-ttu-id="1c982-103">È possibile usare [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] per creare progetti destinati a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] versione 3.0 o 3.5.</span><span class="sxs-lookup"><span data-stu-id="1c982-103">You can use [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] to create projects that target the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version 3.0 or 3.5.</span></span> <span data-ttu-id="1c982-104">In questo argomento viene descritto come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="1c982-104">This topic describes how to do this.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c982-105">Quando si aggiungono attività, verificare che venga impostata la versione desiderata di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c982-105">When adding activities, make sure that the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] is set.</span></span> <span data-ttu-id="1c982-106">Se si modifica la versione di destinazione del flusso di lavoro dopo l'aggiunta delle attività, non sarà possibile convalidare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1c982-106">Changing the target version of the workflow after activities are added will cause the workflow to fail validation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="1c982-107">L'apertura di flussi di lavoro esistenti in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] in cui sono presenti attività di .NET Framework 3.5 provocherà un errore in `this.SetValue()`.</span><span class="sxs-lookup"><span data-stu-id="1c982-107">Opening existing workflows in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] that have .Net Framework 3.5 activities will cause an error at `this.SetValue()`.</span></span> <span data-ttu-id="1c982-108">Per aprire progetti creati con versioni precedenti di .NET Framework, aprire prima un flusso di lavoro vuoto nella finestra di progettazione, quindi aggiungere un'attività .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="1c982-108">In order to open projects created with previous versions of the .Net Framework, first open a blank workflow in the designer and add a .Net Framework 3.5 activity.</span></span>  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a><span data-ttu-id="1c982-109">Per creare un progetto .NET Framework 3.0 o 3.5 in Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="1c982-109">To create a .NET Framework  3.0 or 3.5 project with Visual Studio 2010</span></span>  
  
1.  <span data-ttu-id="1c982-110">Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c982-110">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1c982-111">Selezionare **File**, **nuova**, **progetto**.</span><span class="sxs-lookup"><span data-stu-id="1c982-111">Select **File**, **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="1c982-112">Nell'elenco a discesa nella parte superiore della finestra di dialogo selezionare la versione desiderata di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c982-112">In the drop-down list at the top of the dialog box, select the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a><span data-ttu-id="1c982-113">Per aggiornare la versione di destinazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c982-113">To upgrade the targeted version of the .NET Framework</span></span>  
  
1.  <span data-ttu-id="1c982-114">Fare clic sul progetto in Esplora soluzioni e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1c982-114">Right-click the project in Solution Explorer, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1c982-115">Nel **Framework di destinazione** elenco a discesa, selezionare la versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="1c982-115">In the **Target Framework** drop-down list, select the desired version.</span></span>
