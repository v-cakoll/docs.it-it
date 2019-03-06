---
title: 'Procedura: Utilizzare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: e28086d8c97070b854ebdea35fe347c64c5cd7ac
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377937"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="d9f9f-102">Procedura: Utilizzare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="d9f9f-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="d9f9f-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.ResourceDictionary> per assemblare risorse stringa localizzabili per applicazioni Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d9f9f-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="d9f9f-104">Per usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="d9f9f-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="d9f9f-105">Creare un <xref:System.Windows.ResourceDictionary> che contiene le stringhe da localizzare.</span><span class="sxs-lookup"><span data-stu-id="d9f9f-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="d9f9f-106">Il codice seguente illustra un esempio.</span><span class="sxs-lookup"><span data-stu-id="d9f9f-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="d9f9f-107">Questo codice definisce una risorsa, stringa `localizedMessage`, di tipo <xref:System.String>, dal <xref:System> dello spazio dei nomi in mscorlib. dll.</span><span class="sxs-lookup"><span data-stu-id="d9f9f-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="d9f9f-108">Aggiungere il <xref:System.Windows.ResourceDictionary> all'applicazione, usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d9f9f-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="d9f9f-109">Usare la risorsa stringa dal markup, usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="d9f9f-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="d9f9f-110">Usare la risorsa di tipo stringa dal code-behind, usando un codice analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="d9f9f-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="d9f9f-111">Localizzare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d9f9f-111">Localize the application.</span></span> <span data-ttu-id="d9f9f-112">Per altre informazioni, vedere [localizzare un'applicazione](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="d9f9f-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
