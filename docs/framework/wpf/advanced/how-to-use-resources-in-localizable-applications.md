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
ms.openlocfilehash: d803989292e2fc6b0945c397df5ce32d318147fc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-resources-in-localizable-applications"></a>Procedura: Usare le risorse in applicazioni localizzabili
Localizzazione si intende l'adattamento un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a impostazioni cultura diverse. A questo scopo, testo quale titoli, didascalie, elementi di caselle di riepilogo e così via deve essere tradotto. Per facilitare la traduzione, gli elementi localizzabili vengono raccolti in file di risorse. Vedere [localizzazione di un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) per informazioni su come creare un file di risorse per la localizzazione. Per rendere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizzabili, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse dell'applicazione. Assembly di risorse è localizzato in diverse lingue e il code-behind utilizza la gestione delle risorse [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] da caricare. Uno dei file necessari per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione è un file di progetto (proj). Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto. Nell'esempio di codice seguente viene illustrata questa operazione.  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Per utilizzare una risorsa dell'applicazione, si crea un'istanza <xref:System.Resources.ResourceManager> e caricare la risorsa a cui si desidera utilizzare. L'esempio di codice seguente illustra come eseguire questa operazione.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
