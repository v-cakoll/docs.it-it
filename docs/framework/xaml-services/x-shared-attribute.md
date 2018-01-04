---
title: Attributo x:Shared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: "16"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c9cc5e2bff9cc2591c7a12630da5422dbf73713a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xshared-attribute"></a><span data-ttu-id="bbbd4-102">Attributo x:Shared</span><span class="sxs-lookup"><span data-stu-id="bbbd4-102">x:Shared Attribute</span></span>
<span data-ttu-id="bbbd4-103">Se impostato su `false`, modificare il comportamento di recupero delle risorse WPF, in modo che le richieste per la risorsa con attributa creare una nuova istanza per ogni richiesta invece di condividere la stessa istanza per tutte le richieste.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="bbbd4-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="bbbd4-104">XAML Attribute Usage</span></span>  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a><span data-ttu-id="bbbd4-105">Note</span><span class="sxs-lookup"><span data-stu-id="bbbd4-105">Remarks</span></span>  
 <span data-ttu-id="bbbd4-106">`x:Shared`viene eseguito il mapping dello spazio dei nomi XAML del linguaggio XAML e viene riconosciuto come un elemento di linguaggio XAML valido dai servizi XAML di .NET Framework e i reader XAML.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET Framework XAML Services and its XAML readers.</span></span> <span data-ttu-id="bbbd4-107">Tuttavia, le funzionalità dichiarate di `x:Shared` rilevanti solo per le applicazioni WPF e per il parser XAML di WPF.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="bbbd4-108">In WPF, `x:Shared` è utile come un attributo solo quando viene applicato a un oggetto che esiste all'interno di un controllo WPF <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="bbbd4-109">Altri utilizzi generano eccezioni di analisi o altri errori, ma non hanno alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>  
  
 <span data-ttu-id="bbbd4-110">Il significato di `x:Shared` non è specificato nella specifica del linguaggio XAML.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="bbbd4-111">Altre implementazioni di XAML, ad esempio quelli basati sui servizi XAML di .NET Framework, non necessariamente supportano la condivisione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-111">Other XAML implementations, such as those that build on .NET Framework XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="bbbd4-112">Tali implementazioni XAML può fornire un comportamento simile nel framework di supporto usato anche `x:Shared` valori.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>  
  
 <span data-ttu-id="bbbd4-113">In WPF, il valore predefinito `x:Shared` condizione per le risorse è `true`.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="bbbd4-114">Questa condizione indica che qualsiasi richiesta di risorsa specificata restituisce sempre la stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-114">This condition means that any given resource request always returns the same instance.</span></span>  
  
 <span data-ttu-id="bbbd4-115">Modifica di un oggetto che viene restituito tramite una risorsa API, ad esempio <xref:System.Windows.FrameworkElement.FindResource%2A>, o la modifica di un oggetto direttamente all'interno di un <xref:System.Windows.ResourceDictionary>, modifica la risorsa originale.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="bbbd4-116">Se i riferimenti a tale risorsa erano riferimenti a risorse dinamiche, gli utenti di tale risorsa otterranno la risorsa modificata.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>  
  
 <span data-ttu-id="bbbd4-117">Se i riferimenti alla risorsa erano riferimenti alle risorse statiche, modifiche alla risorsa dopo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tempo di elaborazione sono irrilevanti.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="bbbd4-118">Per ulteriori informazioni statiche e i riferimenti alle risorse dinamiche, vedere [risorse XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="bbbd4-118">For more information about static versus dynamic resource references, see [XAML Resources](../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="bbbd4-119">Specificare in modo esplicito `x:Shared="true"` viene utilizzata raramente, perché è già il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="bbbd4-120">Non è presente codice diretto equivalente per `x:Shared` modello a oggetti in WPF, ma può essere specificato solo in un utilizzo di XAML e deve essere elaborato da quello predefinito WPF o in un flusso del nodo XAML intermedio nel percorso di caricamento, se viene elaborato utilizzando Se XAML di .NET Framework servizi e i reader XAML.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET Framework XAML Services and its XAML readers.</span></span>  
  
 <span data-ttu-id="bbbd4-121">Uno scenario per `x:Shared="false"` è se si definisce un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> derivata come una risorsa, quindi si introduce la risorsa dell'elemento in un modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="bbbd4-122">`x:Shared="false"`Consente di introdurre più volte nella stessa raccolta di una risorsa elemento (ad esempio un <xref:System.Windows.Controls.UIElementCollection>).</span><span class="sxs-lookup"><span data-stu-id="bbbd4-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="bbbd4-123">Senza `x:Shared="false"` non è valido perché la raccolta impone l'univocità del relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="bbbd4-124">Tuttavia, il `x:Shared="false"` comportamento crea un'altra istanza identica della risorsa anziché restituire la stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>  
  
 <span data-ttu-id="bbbd4-125">Un altro scenario `x:Shared="false"` è se si utilizza un <xref:System.Windows.Freezable> risorse per i valori di animazione ma si vuole modificare la risorsa in una singola animazione.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>  
  
 <span data-ttu-id="bbbd4-126">La gestione delle stringhe di `false` non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-126">The string handling of `false` is not case sensitive.</span></span>  
  
 <span data-ttu-id="bbbd4-127">In WPF, `x:Shared` valido solo nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbbd4-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>  
  
-   <span data-ttu-id="bbbd4-128">Il <xref:System.Windows.ResourceDictionary> che contiene gli elementi con `x:Shared` deve essere compilato.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="bbbd4-129">Il <xref:System.Windows.ResourceDictionary> non può essere all'interno di XAML separato o utilizzato per i temi.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>  
  
-   <span data-ttu-id="bbbd4-130">Il <xref:System.Windows.ResourceDictionary> che contiene gli elementi non può essere annidato all'interno di altra <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="bbbd4-131">Ad esempio, è possibile usare `x:Shared` per gli elementi in un <xref:System.Windows.ResourceDictionary> che rientra un <xref:System.Windows.Style> che è già un <xref:System.Windows.ResourceDictionary> elemento.</span><span class="sxs-lookup"><span data-stu-id="bbbd4-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbd4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbbd4-132">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 [<span data-ttu-id="bbbd4-133">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="bbbd4-133">XAML Resources</span></span>](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="bbbd4-134">Elementi di base</span><span class="sxs-lookup"><span data-stu-id="bbbd4-134">Base Elements</span></span>](../../../docs/framework/wpf/advanced/base-elements.md)
