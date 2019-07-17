---
title: 'Procedura: Usare risorse in applicazioni localizzabili'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 3634bb72cbacfb02b0a1230a47a1664cb8ce5009
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238467"
---
# <a name="how-to-use-resources-in-localizable-applications"></a>Procedura: Usare risorse in applicazioni localizzabili
Localizzare significa adattare un' [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a impostazioni cultura diverse. A questo scopo, testo quale titoli, didascalie, elementi di caselle di riepilogo e così via deve essere tradotto. Per facilitare la traduzione, gli elementi localizzabili vengono raccolti in file di risorse. Visualizzare [localizzare un'applicazione](how-to-localize-an-application.md) per informazioni su come creare un file di risorse per la localizzazione. Per rendere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni localizzabili, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse. L'assembly di risorse viene localizzato in lingue diverse e il code-behind Usa l'API Gestione risorse da caricare. Uno dei file richiesti per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione è un file di progetto (proj). Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto. Nell'esempio di codice seguente viene illustrata questa operazione.  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Per usare una risorsa nell'applicazione, si crea un'istanza <xref:System.Resources.ResourceManager> e caricare la risorsa da usare. L'esempio di codice seguente illustra come eseguire questa operazione.  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
