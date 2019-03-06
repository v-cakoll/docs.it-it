---
title: 'Procedura: Utilizzare le risorse in applicazioni localizzabili'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: ad257e7703bcee8f71da78ad5928d7999365c38f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376161"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="bbb0f-102">Procedura: Utilizzare le risorse in applicazioni localizzabili</span><span class="sxs-lookup"><span data-stu-id="bbb0f-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="bbb0f-103">Localizzare significa adattare un' [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a impostazioni cultura diverse.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="bbb0f-104">A questo scopo, testo quale titoli, didascalie, elementi di caselle di riepilogo e così via deve essere tradotto.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="bbb0f-105">Per facilitare la traduzione, gli elementi localizzabili vengono raccolti in file di risorse.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="bbb0f-106">Visualizzare [localizzare un'applicazione](how-to-localize-an-application.md) per informazioni su come creare un file di risorse per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-106">See [Localize an Application](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="bbb0f-107">Per rendere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni localizzabili, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="bbb0f-108">L'assembly di risorse viene localizzato in lingue diverse e il code-behind Usa la gestione delle risorse [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] da caricare.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="bbb0f-109">Uno dei file richiesti per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione è un file di progetto (proj).</span><span class="sxs-lookup"><span data-stu-id="bbb0f-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="bbb0f-110">Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="bbb0f-111">Nell'esempio di codice seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbb0f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbb0f-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="bbb0f-113">Per usare una risorsa nell'applicazione, si crea un'istanza <xref:System.Resources.ResourceManager> e caricare la risorsa da usare.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="bbb0f-114">L'esempio di codice seguente illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="bbb0f-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
