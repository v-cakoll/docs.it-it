---
title: 'Procedura: Usare le risorse in applicazioni localizzabili'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e025b42a72def81420de7d82dcf027405669ce78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="cc189-102">Procedura: Usare le risorse in applicazioni localizzabili</span><span class="sxs-lookup"><span data-stu-id="cc189-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="cc189-103">Localizzazione si intende l'adattamento un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a impostazioni cultura diverse.</span><span class="sxs-lookup"><span data-stu-id="cc189-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="cc189-104">A questo scopo, testo quale titoli, didascalie, elementi di caselle di riepilogo e così via deve essere tradotto.</span><span class="sxs-lookup"><span data-stu-id="cc189-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="cc189-105">Per facilitare la traduzione, gli elementi localizzabili vengono raccolti in file di risorse.</span><span class="sxs-lookup"><span data-stu-id="cc189-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="cc189-106">Vedere [localizzazione di un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) per informazioni su come creare un file di risorse per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc189-106">See [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="cc189-107">Per rendere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizzabili, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc189-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="cc189-108">Assembly di risorse è localizzato in diverse lingue e il code-behind utilizza la gestione delle risorse [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] da caricare.</span><span class="sxs-lookup"><span data-stu-id="cc189-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="cc189-109">Uno dei file necessari per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione è un file di progetto (proj).</span><span class="sxs-lookup"><span data-stu-id="cc189-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="cc189-110">Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cc189-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="cc189-111">Nell'esempio di codice seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="cc189-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc189-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc189-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="cc189-113">Per utilizzare una risorsa dell'applicazione, si crea un'istanza <xref:System.Resources.ResourceManager> e caricare la risorsa a cui si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="cc189-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="cc189-114">L'esempio di codice seguente illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="cc189-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
