---
title: Direttiva x:Subclass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5c6e91fcecb60dee2577ea62c2313f8b2c7eecbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xsubclass-directive"></a><span data-ttu-id="0778e-102">Direttiva x:Subclass</span><span class="sxs-lookup"><span data-stu-id="0778e-102">x:Subclass Directive</span></span>
<span data-ttu-id="0778e-103">Modifica il comportamento di compilazione markup XAML quando `x:Class` viene inoltre fornita.</span><span class="sxs-lookup"><span data-stu-id="0778e-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="0778e-104">Anziché creare una classe parziale che si basa sul `x:Class`, forniti `x:Class` viene creata come una classe intermedia, e quindi la classe derivata è previsto che sia basata su `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="0778e-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="0778e-105">Utilizzo della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="0778e-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="0778e-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="0778e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`namespace`|<span data-ttu-id="0778e-107">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0778e-107">Optional.</span></span> <span data-ttu-id="0778e-108">Specifica uno spazio dei nomi CLR che contiene `classname`.</span><span class="sxs-lookup"><span data-stu-id="0778e-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="0778e-109">Se `namespace` è specificato, un punto (.) separa `namespace` e `classname`.</span><span class="sxs-lookup"><span data-stu-id="0778e-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|  
|`classname`|<span data-ttu-id="0778e-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0778e-110">Required.</span></span> <span data-ttu-id="0778e-111">Specifica il nome CLR della classe parziale che connette il codice XAML caricato e il code-behind per tale codice XAML.</span><span class="sxs-lookup"><span data-stu-id="0778e-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="0778e-112">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="0778e-112">See Remarks.</span></span>|  
|`subclassNamespace`|<span data-ttu-id="0778e-113">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0778e-113">Optional.</span></span> <span data-ttu-id="0778e-114">Può essere diverso da `namespace` se ogni spazio dei nomi è possibile risolvere l'altro.</span><span class="sxs-lookup"><span data-stu-id="0778e-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="0778e-115">Specifica uno spazio dei nomi CLR che contiene `subclassName`.</span><span class="sxs-lookup"><span data-stu-id="0778e-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="0778e-116">Se `subclassName` è specificato, un punto (.) separa `subclassNamespace` e `subclassName`.</span><span class="sxs-lookup"><span data-stu-id="0778e-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|  
|`subclassName`|<span data-ttu-id="0778e-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0778e-117">Required.</span></span> <span data-ttu-id="0778e-118">Specifica il nome CLR della sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="0778e-118">Specifies the CLR name of the subclass.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="0778e-119">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="0778e-119">Dependencies</span></span>  
 <span data-ttu-id="0778e-120">[Direttiva X:Class](../../../docs/framework/xaml-services/x-class-directive.md) deve inoltre essere disponibile per lo stesso oggetto, che deve essere l'elemento radice della produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="0778e-120">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0778e-121">Note</span><span class="sxs-lookup"><span data-stu-id="0778e-121">Remarks</span></span>  
 <span data-ttu-id="0778e-122">`x:Subclass`utilizzo viene usata principalmente per le lingue che non supportano le dichiarazioni di classe parziale.</span><span class="sxs-lookup"><span data-stu-id="0778e-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>  
  
 <span data-ttu-id="0778e-123">La classe utilizzata come il `x:Subclass` non può essere una classe annidata, e `x:Subclass` deve fare riferimento all'oggetto radice, come illustrato nella sezione "Dipendenze".</span><span class="sxs-lookup"><span data-stu-id="0778e-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>  
  
 <span data-ttu-id="0778e-124">In caso contrario, il significato concettuale di `x:Subclass` non è definita da un'implementazione di servizi XAML di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0778e-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET Framework XAML Services implementation.</span></span> <span data-ttu-id="0778e-125">In questo modo il comportamento di servizi XAML di .NET Framework non specifica il modello di programmazione generale mediante XAML markup e il codice di supporto sono connessi.</span><span class="sxs-lookup"><span data-stu-id="0778e-125">This is because .NET Framework XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="0778e-126">Le implementazioni di ulteriormente i concetti relativi a `x:Class` e `x:Subclass` vengono eseguite da framework specifici che utilizzano modelli di programmazione o applicazione per definire come connettere markup XAML, markup compilato e codice basato su CLR.</span><span class="sxs-lookup"><span data-stu-id="0778e-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="0778e-127">Ogni framework potrebbe disporre di operazioni di compilazione che abilitano alcuni comportamenti o componenti specifici che devono essere inclusi nell'ambiente di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0778e-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="0778e-128">All'interno di un framework di azioni di compilazione possono inoltre variare in base al linguaggio CLR specifico utilizzato per il code-behind.</span><span class="sxs-lookup"><span data-stu-id="0778e-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="0778e-129">Note sull'utilizzo WPF</span><span class="sxs-lookup"><span data-stu-id="0778e-129">WPF Usage Notes</span></span>  
 <span data-ttu-id="0778e-130">`x:Subclass`può essere in una radice della pagina o nel database di <xref:System.Windows.Application> radice nella definizione dell'applicazione, cui è già `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="0778e-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="0778e-131">Dichiarazione di `x:Subclass` su qualsiasi elemento diverso da una radice di un'applicazione o pagina o specificarla in cui non `x:Class` esiste, genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0778e-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>  
  
 <span data-ttu-id="0778e-132">Creazione di derivata classi che funzionano correttamente per il `x:Subclass` scenario è abbastanza complesso.</span><span class="sxs-lookup"><span data-stu-id="0778e-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="0778e-133">Potrebbe essere necessario esaminare i file intermedi (vale a dire i file g prodotti nella cartella obj del progetto dalla compilazione del markup, con nomi che includono i nomi dei file con estensione XAML).</span><span class="sxs-lookup"><span data-stu-id="0778e-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="0778e-134">Questi file intermedi consentono di determinare l'origine di determinati costrutti di programmazione in classi parziali associate nell'applicazione compilata.</span><span class="sxs-lookup"><span data-stu-id="0778e-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>  
  
 <span data-ttu-id="0778e-135">Gestori di eventi nella classe derivata devono essere `internal override` (`Friend Overrides` in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]) per eseguire l'override degli stub per i gestori creati nella classe intermedia durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="0778e-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="0778e-136">In caso contrario, le implementazioni della classe derivata nascondono l'implementazione della classe intermedi e non vengono richiamati i gestori di classe intermedia.</span><span class="sxs-lookup"><span data-stu-id="0778e-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>  
  
 <span data-ttu-id="0778e-137">Quando si definiscono gli oggetti `x:Class` e `x:Subclass`, non è necessario fornire alcuna implementazione per la classe a cui fa riferimento `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="0778e-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="0778e-138">È necessario assegnargli un nome tramite il `x:Class` attributo in modo che il compilatore dispone di alcune indicazioni per la classe che viene creato il file intermedio (il compilatore non seleziona un nome predefinito in questo caso).</span><span class="sxs-lookup"><span data-stu-id="0778e-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="0778e-139">È possibile assegnare il `x:Class` un'implementazione della classe; tuttavia, non si tratta di uno scenario tipico per l'utilizzo di entrambi `x:Class` e `x:Subclass`.</span><span class="sxs-lookup"><span data-stu-id="0778e-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0778e-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0778e-140">See Also</span></span>  
 [<span data-ttu-id="0778e-141">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="0778e-141">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="0778e-142">Classi XAML e personalizzate per WPF</span><span class="sxs-lookup"><span data-stu-id="0778e-142">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
