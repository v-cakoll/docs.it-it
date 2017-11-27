---
title: Direttiva x:Property
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
caps.latest.revision: "6"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a59eb23ab3ed6ee6adbbebab0859caffd293b24f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xproperty-directive"></a><span data-ttu-id="cddc4-102">Direttiva x:Property</span><span class="sxs-lookup"><span data-stu-id="cddc4-102">x:Property Directive</span></span>
<span data-ttu-id="cddc4-103">Dichiara una proprietà XAML nel markup.</span><span class="sxs-lookup"><span data-stu-id="cddc4-103">Declares a XAML property in markup.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="cddc4-104">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="cddc4-104">XAML Object Element Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Property Name="propertyName" Type="propertyType/>  
    additionalProperties  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="cddc4-105">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="cddc4-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="cddc4-106">Nome della classe sottostante o della classe parziale per la produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="cddc4-106">Name of the backing class or partial class for the XAML production.</span></span>|  
|`propertyName`|<span data-ttu-id="cddc4-107">Nome membro della proprietà da definire.</span><span class="sxs-lookup"><span data-stu-id="cddc4-107">Member name of the property being defined.</span></span>|  
|`propertyType`|<span data-ttu-id="cddc4-108">Nome del tipo (o altro formato stringa, specifico del framework) che specifica il tipo di questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="cddc4-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cddc4-109">Note</span><span class="sxs-lookup"><span data-stu-id="cddc4-109">Remarks</span></span>  
 <span data-ttu-id="cddc4-110">Nell'implementazione dei servizi XAML di .NET Framework,</span><span class="sxs-lookup"><span data-stu-id="cddc4-110">In the .NET Framework XAML Services implementation, .</span></span> <span data-ttu-id="cddc4-111">`x:Property` non dispone di un supporto del tipo diretto, ma è supportato dalla classe <xref:System.Windows.Markup.PropertyDefinition>.</span><span class="sxs-lookup"><span data-stu-id="cddc4-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="cddc4-112">In un flusso del nodo XAML, un elemento `x:Property` viene rappresentato come membro denominato `Property`, dallo spazio dei nomi XAML del linguaggio XAML.</span><span class="sxs-lookup"><span data-stu-id="cddc4-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="cddc4-113">Il membro `Property` contiene gli attributi dichiarati dal markup.</span><span class="sxs-lookup"><span data-stu-id="cddc4-113">The member `Property` hold attributes as declared by markup.</span></span>  
  
 <span data-ttu-id="cddc4-114">I significati di `Name` e di `Type` non vengono assegnati a livello di servizi XAML di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cddc4-114">The meaning of `Name` and `Type` are not assigned at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="cddc4-115">Vengono archiviati nel flusso del nodo XAML iniziale come valori di stringa, da interpretare in seguito in base alle regole che potrebbero essere imposte da framework specifici.</span><span class="sxs-lookup"><span data-stu-id="cddc4-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="cddc4-116">Il significato potrebbe allinearsi al significato di un nome XAML e di un tipo XAML o potrebbe essere valido solo in un sistema di tipi di supporto, a seconda dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="cddc4-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>  
  
 <span data-ttu-id="cddc4-117">Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="cddc4-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="cddc4-118">Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="cddc4-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="cddc4-119">Tuttavia, il meccanismo per l'associazione di tipi e membri o per la creazione di definizioni dei membri dinamici non è supportato a livello di servizi XAML di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cddc4-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="cddc4-120">Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML.</span><span class="sxs-lookup"><span data-stu-id="cddc4-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="cddc4-121">In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cddc4-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="cddc4-122">x:Property per Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="cddc4-122">x:Property for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="cddc4-123">Per Windows Workflow Foundation, `x:Property` definisce i membri di un'attività personalizzata costituita interamente in XAML o i membri dinamici definiti da XAML per ActivityDesigner con code-behind.</span><span class="sxs-lookup"><span data-stu-id="cddc4-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="cddc4-124">`x:Class` deve essere specificato anche nell'elemento radice della produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="cddc4-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="cddc4-125">Non è un requisito a livello di servizi XAML di .NET Framework, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano attività personalizzate e il codice XAML di Windows Workflow Foundation in generale.</span><span class="sxs-lookup"><span data-stu-id="cddc4-125">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="cddc4-126">Windows Workflow Foundation non utilizza il nome del tipo XAML puro come valore designato per la `x:Property` `Type` attributo e si utilizza invece una convenzione non documentato qui.</span><span class="sxs-lookup"><span data-stu-id="cddc4-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="cddc4-127">Per ulteriori informazioni, vedere [DynamicActivityCreation](http://msdn.microsoft.com/library/dd807392.aspx).</span><span class="sxs-lookup"><span data-stu-id="cddc4-127">For more information, see [Dynamic Activity Creation](http://msdn.microsoft.com/library/dd807392.aspx).</span></span>
