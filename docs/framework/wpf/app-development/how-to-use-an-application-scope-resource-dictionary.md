---
title: 'Procedura: utilizzare un dizionario risorse relativo all''ambito dell''applicazione'
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
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 417fea4dcbb5a8d0a27f9605be19de5921aaf0ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="e702e-102">Procedura: utilizzare un dizionario risorse relativo all'ambito dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="e702e-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="e702e-103">Questo esempio illustra come definire e usare un dizionario risorse personalizzato dell'ambito di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e702e-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e702e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e702e-104">Example</span></span>  
 <span data-ttu-id="e702e-105"><xref:System.Windows.Application>espone un archivio di applicazione per le risorse condivise: <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="e702e-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="e702e-106">Per impostazione predefinita, il <xref:System.Windows.Application.Resources%2A> proprietà viene inizializzata con un'istanza di <xref:System.Windows.ResourceDictionary> tipo.</span><span class="sxs-lookup"><span data-stu-id="e702e-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="e702e-107">Utilizzare questa istanza quando si ottengono e impostare le proprietà dell'ambito dell'applicazione utilizzando <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="e702e-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="e702e-108">Per ulteriori informazioni, vedere [procedura: ottenere e impostare una risorsa applicazione](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).</span><span class="sxs-lookup"><span data-stu-id="e702e-108">For more information, see [How to: Get and Set an Application-Scope Resource](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).</span></span>
  
 <span data-ttu-id="e702e-109">Se si dispongono di più risorse impostate tramite la <xref:System.Windows.Application.Resources%2A>, è invece possibile utilizzare un dizionario risorse personalizzato per archiviare le risorse e impostare <xref:System.Windows.Application.Resources%2A> con esso invece.</span><span class="sxs-lookup"><span data-stu-id="e702e-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="e702e-110">Di seguito viene illustrato come dichiarare un dizionario risorse personalizzato tramite XAML.</span><span class="sxs-lookup"><span data-stu-id="e702e-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="e702e-111">Lo scambio di interi dizionari risorse tramite <xref:System.Windows.Application.Resources%2A> consente di supportare l'applicazione di temi, dove ogni tema è incapsulato da un singolo dizionario risorse.</span><span class="sxs-lookup"><span data-stu-id="e702e-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="e702e-112">Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="e702e-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="e702e-113">Nell'esempio seguente viene illustrato come ottenere le risorse dell'ambito di applicazione dal dizionario risorse esposto da <xref:System.Windows.Application.Resources%2A> in XAML.</span><span class="sxs-lookup"><span data-stu-id="e702e-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="e702e-114">L'esempio seguente illustra come è possibile ottenere anche le risorse nel codice.</span><span class="sxs-lookup"><span data-stu-id="e702e-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="e702e-115">Esistono due considerazioni quando si utilizza <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="e702e-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="e702e-116">Innanzitutto, il dizionario *chiave* è un oggetto, pertanto è necessario usare esattamente la stessa istanza dell'oggetto sia quando l'impostazione e recupero di un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e702e-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="e702e-117">(si noti che la chiave fa distinzione tra maiuscole e minuscole quando si usa una stringa). In secondo luogo, il dizionario *valore* è un oggetto, pertanto è necessario convertire il valore per il tipo desiderato quando si recupera un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e702e-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e702e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e702e-118">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [<span data-ttu-id="e702e-119">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="e702e-119">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="e702e-120">Dizionari risorse uniti</span><span class="sxs-lookup"><span data-stu-id="e702e-120">Merged Resource Dictionaries</span></span>](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
