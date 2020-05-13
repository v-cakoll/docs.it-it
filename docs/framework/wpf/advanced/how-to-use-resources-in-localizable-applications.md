---
title: 'Procedura: Usare le risorse in applicazioni localizzabili'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212475"
---
# <a name="how-to-use-resources-in-localizable-apps"></a>Procedura: usare le risorse in applicazioni localizzabili

La localizzazione consente di adattare un'interfaccia utente a impostazioni cultura diverse. A tale scopo, è necessario convertire testo, ad esempio titoli, didascalie ed elementi della casella di riepilogo. Per semplificare la traduzione, gli elementi da tradurre vengono raccolti in file di risorse. Per informazioni su come creare un file di risorse per la localizzazione, vedere [localizzare un'app](how-to-localize-an-application.md) . Per rendere localizzabile un'applicazione WPF, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse. L'assembly di risorse viene localizzato in lingue diverse e il code-behind usa l'API di gestione delle risorse per il caricamento.

## <a name="example"></a>Esempio

Uno dei file necessari per un'applicazione WPF è un file di progetto (con estensione proj). Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto. Nell'esempio di codice XAML riportato di seguito viene illustrato.

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

Per usare una risorsa nell'applicazione, creare un'istanza <xref:System.Resources.ResourceManager> e caricare la risorsa che si vuole usare. Il codice C# seguente illustra come eseguire questa operazione.

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a>Vedere anche

- [Localizzare un'app](how-to-localize-an-application.md)
