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
# <a name="how-to-use-resources-in-localizable-apps"></a><span data-ttu-id="1a30b-102">Procedura: usare le risorse in applicazioni localizzabili</span><span class="sxs-lookup"><span data-stu-id="1a30b-102">How to: Use resources in localizable apps</span></span>

<span data-ttu-id="1a30b-103">La localizzazione consente di adattare un'interfaccia utente a impostazioni cultura diverse.</span><span class="sxs-lookup"><span data-stu-id="1a30b-103">Localization means to adapt a user interface to different cultures.</span></span> <span data-ttu-id="1a30b-104">A tale scopo, è necessario convertire testo, ad esempio titoli, didascalie ed elementi della casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="1a30b-104">To do this, text such as titles, captions, and list box items must be translated.</span></span> <span data-ttu-id="1a30b-105">Per semplificare la traduzione, gli elementi da tradurre vengono raccolti in file di risorse.</span><span class="sxs-lookup"><span data-stu-id="1a30b-105">To make translation easier, the items to be translated are collected into resource files.</span></span> <span data-ttu-id="1a30b-106">Per informazioni su come creare un file di risorse per la localizzazione, vedere [localizzare un'app](how-to-localize-an-application.md) .</span><span class="sxs-lookup"><span data-stu-id="1a30b-106">See [Localize an app](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="1a30b-107">Per rendere localizzabile un'applicazione WPF, gli sviluppatori devono compilare tutte le risorse localizzabili in un assembly di risorse.</span><span class="sxs-lookup"><span data-stu-id="1a30b-107">To make a WPF application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="1a30b-108">L'assembly di risorse viene localizzato in lingue diverse e il code-behind usa l'API di gestione delle risorse per il caricamento.</span><span class="sxs-lookup"><span data-stu-id="1a30b-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span>

## <a name="example"></a><span data-ttu-id="1a30b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a30b-109">Example</span></span>

<span data-ttu-id="1a30b-110">Uno dei file necessari per un'applicazione WPF è un file di progetto (con estensione proj).</span><span class="sxs-lookup"><span data-stu-id="1a30b-110">One of the files required for a WPF application is a project file (.proj).</span></span> <span data-ttu-id="1a30b-111">Tutte le risorse usate nell'applicazione devono essere incluse nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1a30b-111">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="1a30b-112">Nell'esempio di codice XAML riportato di seguito viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="1a30b-112">The following XAML example shows this.</span></span>

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

<span data-ttu-id="1a30b-113">Per usare una risorsa nell'applicazione, creare un'istanza <xref:System.Resources.ResourceManager> e caricare la risorsa che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="1a30b-113">To use a resource in your application, instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="1a30b-114">Il codice C# seguente illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="1a30b-114">The following C# code demonstrates how to do this.</span></span>

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a><span data-ttu-id="1a30b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a30b-115">See also</span></span>

- [<span data-ttu-id="1a30b-116">Localizzare un'app</span><span class="sxs-lookup"><span data-stu-id="1a30b-116">Localize an app</span></span>](how-to-localize-an-application.md)
