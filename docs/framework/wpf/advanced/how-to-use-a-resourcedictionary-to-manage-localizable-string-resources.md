---
title: 'Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili'
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
ms.openlocfilehash: b56a307ed31fc8f7573215eac70350ac5e4b9de1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311318"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.ResourceDictionary> per assemblare risorse stringa localizzabili per applicazioni Windows Presentation Foundation (WPF).  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Per usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili  
  
1. Creare un <xref:System.Windows.ResourceDictionary> che contiene le stringhe da localizzare. Il codice seguente illustra un esempio.  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     Questo codice definisce una risorsa, stringa `localizedMessage`, di tipo <xref:System.String>, dal <xref:System> dello spazio dei nomi in mscorlib. dll.  
  
2. Aggiungere il <xref:System.Windows.ResourceDictionary> all'applicazione, usando il codice seguente.  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. Usare la risorsa stringa dal markup, usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] analogo al seguente.  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. Usare la risorsa di tipo stringa dal code-behind, usando un codice analogo al seguente.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. Localizzare l'applicazione. Per altre informazioni, vedere [localizzare un'applicazione](how-to-localize-an-application.md).
