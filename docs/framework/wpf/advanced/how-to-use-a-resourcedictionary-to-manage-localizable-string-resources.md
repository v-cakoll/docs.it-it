---
title: 'Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38cfd687eadf31cc94dfdd2cbbf082bf80424cba
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="7becc-102">Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="7becc-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="7becc-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.ResourceDictionary> alle risorse stringa localizzabile pacchetto [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7becc-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="7becc-104">Per usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="7becc-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="7becc-105">Creare un <xref:System.Windows.ResourceDictionary> che contiene le stringhe che si desidera localizzare.</span><span class="sxs-lookup"><span data-stu-id="7becc-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="7becc-106">Il codice seguente illustra un esempio.</span><span class="sxs-lookup"><span data-stu-id="7becc-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="7becc-107">Questo codice definisce una risorsa di stringa, `localizedMessage`, di tipo <xref:System.String>, dal <xref:System> dello spazio dei nomi in mscorlib. dll.</span><span class="sxs-lookup"><span data-stu-id="7becc-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="7becc-108">Aggiungere il <xref:System.Windows.ResourceDictionary> per l'applicazione, tramite il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7becc-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="7becc-109">Utilizzare la risorsa stringa dal markup, utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="7becc-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="7becc-110">Usare la risorsa di tipo stringa dal code-behind, usando un codice analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="7becc-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="7becc-111">Localizzare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7becc-111">Localize the application.</span></span> <span data-ttu-id="7becc-112">Per ulteriori informazioni, vedere [localizzazione di un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="7becc-112">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>
