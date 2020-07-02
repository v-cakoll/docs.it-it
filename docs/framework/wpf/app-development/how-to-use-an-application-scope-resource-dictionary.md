---
title: "Procedura: utilizzare un dizionario risorse relativo all'ambito dell'applicazione"
description: Informazioni su come definire e usare un dizionario risorse personalizzato con ambito applicazione in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 9d117dea6c554339b4b462b9bf37b80da2dc477f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613709"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="b8f01-103">Procedura: utilizzare un dizionario risorse relativo all'ambito dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b8f01-103">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="b8f01-104">Questo esempio illustra come definire e usare un dizionario risorse personalizzato dell'ambito di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8f01-104">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8f01-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8f01-105">Example</span></span>  
 <span data-ttu-id="b8f01-106"><xref:System.Windows.Application>espone un archivio dell'ambito dell'applicazione per le risorse condivise: <xref:System.Windows.Application.Resources%2A> .</span><span class="sxs-lookup"><span data-stu-id="b8f01-106"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="b8f01-107">Per impostazione predefinita, la <xref:System.Windows.Application.Resources%2A> proprietà viene inizializzata con un'istanza del <xref:System.Windows.ResourceDictionary> tipo.</span><span class="sxs-lookup"><span data-stu-id="b8f01-107">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="b8f01-108">Usare questa istanza quando si ottengono e si impostano le proprietà dell'ambito dell'applicazione usando <xref:System.Windows.Application.Resources%2A> .</span><span class="sxs-lookup"><span data-stu-id="b8f01-108">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="b8f01-109">Per altre informazioni, vedere [procedura: ottenere e impostare una risorsa dell'ambito dell'applicazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b8f01-109">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="b8f01-110">Se si dispone di più risorse impostate utilizzando <xref:System.Windows.Application.Resources%2A> , è invece possibile utilizzare un dizionario risorse personalizzato per archiviare tali risorse e impostarle <xref:System.Windows.Application.Resources%2A> in alternativa.</span><span class="sxs-lookup"><span data-stu-id="b8f01-110">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="b8f01-111">Di seguito viene illustrato come dichiarare un dizionario risorse personalizzato con XAML.</span><span class="sxs-lookup"><span data-stu-id="b8f01-111">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="b8f01-112">Lo scambio di interi dizionari risorse tramite <xref:System.Windows.Application.Resources%2A> consente di supportare i temi dell'ambito dell'applicazione, in cui ogni tema è incapsulato da un singolo dizionario risorse.</span><span class="sxs-lookup"><span data-stu-id="b8f01-112">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="b8f01-113">Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="b8f01-113">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="b8f01-114">Di seguito viene illustrato come ottenere le risorse dell'ambito dell'applicazione dal dizionario risorse esposto da <xref:System.Windows.Application.Resources%2A> in XAML.</span><span class="sxs-lookup"><span data-stu-id="b8f01-114">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="b8f01-115">L'esempio seguente illustra come è possibile ottenere anche le risorse nel codice.</span><span class="sxs-lookup"><span data-stu-id="b8f01-115">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="b8f01-116">Quando si usa, è necessario tenere presenti due considerazioni <xref:System.Windows.Application.Resources%2A> .</span><span class="sxs-lookup"><span data-stu-id="b8f01-116">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="b8f01-117">In primo luogo, la *chiave* del dizionario è un oggetto, pertanto è necessario usare esattamente la stessa istanza dell'oggetto quando si imposta e si recupera un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8f01-117">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="b8f01-118">Si noti che la chiave fa distinzione tra maiuscole e minuscole quando si usa una stringa. In secondo luogo, il *valore* del dizionario è un oggetto, pertanto è necessario convertire il valore nel tipo desiderato quando si recupera un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b8f01-118">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f01-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8f01-119">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="b8f01-120">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="b8f01-120">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="b8f01-121">Dizionari risorse uniti</span><span class="sxs-lookup"><span data-stu-id="b8f01-121">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
