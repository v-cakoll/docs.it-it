---
title: Direttiva x:Members
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e76f539e713f3d21751de18c86cc2dcebf99f570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xmembers-directive"></a><span data-ttu-id="cb1ce-102">Direttiva x:Members</span><span class="sxs-lookup"><span data-stu-id="cb1ce-102">x:Members Directive</span></span>
<span data-ttu-id="cb1ce-103">Contiene un set di membri che sono definiti nel markup, che si applicano alle X:Class dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-103">Holds a set of members that are defined in markup, which apply to the x:Class of the parent element.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="cb1ce-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="cb1ce-104">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="cb1ce-105">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="cb1ce-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="cb1ce-106">Nome della classe sottostante o della classe parziale per la produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-106">Name of the backing class or partial class for the XAML production.</span></span> <span data-ttu-id="cb1ce-107">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-107">See Remarks.</span></span>|  
|`oneOrMoreMembers`|<span data-ttu-id="cb1ce-108">Uno o più elementi di oggetti che rappresentano le definizioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-108">One or more object elements that represent member definitions.</span></span> <span data-ttu-id="cb1ce-109">In genere, questi sono `x:Property` elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-109">Typically, these are `x:Property` object elements.</span></span> <span data-ttu-id="cb1ce-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-110">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb1ce-111">Note</span><span class="sxs-lookup"><span data-stu-id="cb1ce-111">Remarks</span></span>  
 <span data-ttu-id="cb1ce-112">Nell'implementazione dei servizi XAML di .NET Framework, non è presente alcuna classe sottostante o l'implementazione sottostante di un membro per `x:Members`.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-112">In the .NET Framework XAML Services implementation, there is no backing class or underlying member implementation for `x:Members`.</span></span> <span data-ttu-id="cb1ce-113">`x:Members`è un membro XAML speciale che può esistere come membro di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-113">`x:Members` is a special XAML member that can exist as a member on any type.</span></span> <span data-ttu-id="cb1ce-114">In un flusso del nodo XAML, `x:Members` è rappresentato come un membro denominato `Members`, spazio dei nomi XAML del linguaggio XAML.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-114">In a XAML node stream, `x:Members` is represented as a member named `Members`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="cb1ce-115">Il membro `Members` contiene un elenco generico di sola lettura di `Member` oggetti.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-115">The member `Members` contains a read-only generic list of `Member` objects.</span></span> <span data-ttu-id="cb1ce-116">Nel markup tipico i singoli membri vengono specificati come `x:Property` elementi proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-116">In typical markup the individual members are specified as `x:Property` property elements.</span></span> <span data-ttu-id="cb1ce-117">`x:Property`è un tipo in modo specifico per le proprietà dei tipi più preciso e può essere assegnato a `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-117">`x:Property` is a more precise type specifically for properties of types and is assignable to `x:Member`.</span></span> <span data-ttu-id="cb1ce-118">Per ulteriori informazioni, vedere [direttiva X:Property](../../../docs/framework/xaml-services/x-property-directive.md).</span><span class="sxs-lookup"><span data-stu-id="cb1ce-118">For more information, see [x:Property Directive](../../../docs/framework/xaml-services/x-property-directive.md).</span></span>  
  
 <span data-ttu-id="cb1ce-119">Per supportare un utilizzo pratico di `x:Members` come mezzo per specificare le definizioni dei membri nel markup, i membri devono essere associati a una classe che può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-119">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="cb1ce-120">Il modello designato prevede che `x:Members` esista come membro di un tipo che specifica un oggetto `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-120">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="cb1ce-121">Tuttavia, il meccanismo per l'associazione di tipi e membri o per la creazione di definizioni dei membri dinamici non è supportato a livello di servizi XAML di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-121">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="cb1ce-122">Questo viene lasciato ai singoli framework che dispongono di modelli di applicazione che supportano le definizioni dei membri da XAML.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-122">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="cb1ce-123">In genere, le azioni di compilazione MSBUILD, che compilano XAML con il markup e lo integrano con il code-behind o creano veri e propri assembly da XAML, sono necessarie per supportare tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-123">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xmembers-for-windows-workflow-foundation"></a><span data-ttu-id="cb1ce-124">x: i membri per Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="cb1ce-124">x:Members for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="cb1ce-125">Per Windows Workflow Foundation, `x:Members` contiene i membri di un'attività personalizzata costituita interamente in XAML o XAML: definiti membri dinamici di un ActivityDesigner con code-behind.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-125">For Windows Workflow Foundation, `x:Members` contains the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="cb1ce-126">`x:Class` deve essere specificato anche nell'elemento radice della produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-126">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="cb1ce-127">Non è un requisito a livello di servizi XAML di .NET Framework, ma diventa un requisito quando la produzione XAML viene caricata dalle azioni di compilazione MSBUILD che supportano attività personalizzate e il codice XAML di Windows Workflow Foundation in generale.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-127">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="cb1ce-128">`x:Members`deve essere il primo elemento figlio nel markup dell'elemento che dichiara il `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="cb1ce-128">`x:Members` must be the first child element in markup of the object element that declares the `x:Class`.</span></span>
