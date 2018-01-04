---
title: "Funzionalità del linguaggio XAML 2009"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML 2009 [XAML Services]
- XAML [XAML Services], XAML 2009
ms.assetid: f6bb18d8-c86a-4549-8862-323e6b32a8dd
caps.latest.revision: "11"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 447ba37330e8027d86fd24239a8aca2461dce8d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-2009-language-features"></a><span data-ttu-id="831d3-102">Funzionalità del linguaggio XAML 2009</span><span class="sxs-lookup"><span data-stu-id="831d3-102">XAML 2009 Language Features</span></span>
<span data-ttu-id="831d3-103">XAML 2009 è il termine abbreviato per le nuove funzionalità del linguaggio XAML che estendono la specifica del linguaggio XAML esistente.</span><span class="sxs-lookup"><span data-stu-id="831d3-103">XAML 2009 is the shorthand term for new XAML language features that extend the existing XAML language specification.</span></span> <span data-ttu-id="831d3-104">XAML 2009 introduce varie nuove direttive e costrutti.</span><span class="sxs-lookup"><span data-stu-id="831d3-104">XAML 2009 introduces several new directives and constructs.</span></span> <span data-ttu-id="831d3-105">Sono incluse[x:Arguments Directive](../../../docs/framework/xaml-services/x-arguments-directive.md), [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md), [x:Reference Markup Extension](../../../docs/framework/xaml-services/x-reference-markup-extension.md), [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)e i tipi nativi per primitive di linguaggio comuni, ad esempio `x:Char`.</span><span class="sxs-lookup"><span data-stu-id="831d3-105">These include the[x:Arguments Directive](../../../docs/framework/xaml-services/x-arguments-directive.md); the [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md); the [x:Reference Markup Extension](../../../docs/framework/xaml-services/x-reference-markup-extension.md); the [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md); and built-in types for common language primitives (for example `x:Char`).</span></span>  
  
<a name="xaml_2009_support_in_wpf_and_visual_studio"></a>   
## <a name="xaml-2009-support-in-wpf-and-visual-studio"></a><span data-ttu-id="831d3-106">Supporto XAML 2009 in WPF e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="831d3-106">XAML 2009 Support in WPF and Visual Studio</span></span>  
 <span data-ttu-id="831d3-107">In WPF è possibile usare le funzionalità di XAML 2009, ma solo per il codice XAML non compilato dal markup WPF.</span><span class="sxs-lookup"><span data-stu-id="831d3-107">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="831d3-108">Il codice XAML compilato dal markup e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="831d3-108">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>  
  
 <span data-ttu-id="831d3-109">Si noti che per le tecniche esistenti per il caricamento di XAML separato in WPF esistono anche possibili restrizioni ai tipi CLR e al sistema di tipi che sono più restrittive rispetto a quelle per XAML compilato dal markup.</span><span class="sxs-lookup"><span data-stu-id="831d3-109">Note that existing techniques for loading loose XAML in WPF also have possible security and access restrictions to CLR types and the type system that are more restrictive than for markup-compiled XAML.</span></span> <span data-ttu-id="831d3-110">Per altre informazioni vedere [Sicurezza (WPF)](../../../docs/framework/wpf/security-wpf.md) o [Strategia di sicurezza di WPF - Sicurezza della piattaforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).</span><span class="sxs-lookup"><span data-stu-id="831d3-110">For more information, see [Security (WPF)](../../../docs/framework/wpf/security-wpf.md) or [WPF Security Strategy - Platform Security](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).</span></span>  
  
 <span data-ttu-id="831d3-111">XAML 2009 introduce anche funzionalità aggiuntive che modificano i costrutti XAML 2006 precedenti o che modificano i moduli del markup di base.</span><span class="sxs-lookup"><span data-stu-id="831d3-111">XAML 2009 also introduces additional features that either modify the previous XAML 2006 constructs or that modify the basic markup forms.</span></span>  
  
### <a name="xkey-as-an-object-element"></a><span data-ttu-id="831d3-112">x:Key come un elemento oggetto</span><span class="sxs-lookup"><span data-stu-id="831d3-112">x:Key as an Object Element</span></span>  
 <span data-ttu-id="831d3-113">XAML 2009 può supportare `x:Key` come un oggetto (un elemento proprietà con valore dell'elemento oggetto). Tuttavia, XAML 2006 supportava solo `x:Key` come attributo.</span><span class="sxs-lookup"><span data-stu-id="831d3-113">XAML 2009 can support `x:Key` as an object (a property element that has object element value); however, XAML 2006 only supported `x:Key` as an attribute.</span></span> <span data-ttu-id="831d3-114">Vedere la sezione "XAML 2009" di [x:Key Directive](../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="831d3-114">See the "XAML 2009" section of [x:Key Directive](../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
### <a name="xmlns-on-property-elements"></a><span data-ttu-id="831d3-115">xmlns su elementi proprietà</span><span class="sxs-lookup"><span data-stu-id="831d3-115">xmlns on Property Elements</span></span>  
 <span data-ttu-id="831d3-116">XAML 2009 può supportare definizioni (xmlns) dello spazio dei nomi XAML su elementi proprietà. Tuttavia, XAML 2006 supporta solo definizioni xmlns su elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="831d3-116">XAML 2009 can support XAML namespace (xmlns) definitions on property elements; however, XAML 2006 only supports xmlns definitions on object elements.</span></span>  
  
### <a name="event-attributes"></a><span data-ttu-id="831d3-117">Attributi dell'evento</span><span class="sxs-lookup"><span data-stu-id="831d3-117">Event Attributes</span></span>  
 <span data-ttu-id="831d3-118">Per gli attributi supportati dagli eventi, XAML 2006 presuppone che sia coinvolta la compilazione del markup e invia gli eventi alla compilazione del markup.</span><span class="sxs-lookup"><span data-stu-id="831d3-118">For attributes that are backed by events, XAML 2006 presumes that markup compilation is involved and submits the events to markup compilation.</span></span> <span data-ttu-id="831d3-119">XAML 2009 supporta un modulo di markup che assomiglia a un'estensione di markup, che rinvia il collegamento di eventi fino all'analisi e al caricamento in fase di esecuzione di XAML.</span><span class="sxs-lookup"><span data-stu-id="831d3-119">XAML 2009 supports a markup form that resembles a markup extension, which defers the event wiring until run-time parsing and loading of the XAML.</span></span> <span data-ttu-id="831d3-120">Le applicazioni WPF e gli scenari XAML per l'interfaccia utente tuttavia in genere non usano questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="831d3-120">However, WPF applications and XAML scenarios for WPF UI generally do not use this capability.</span></span> <span data-ttu-id="831d3-121">WPF e la relativa implementazione XAML 2006 usano la combinazione del collegamento del gestore eventi per eventi indirizzati, definiti al livello <xref:System.Windows.UIElement> , e il passaggio del compilatore di markup per la maggior parte dell'elaborazione di attributi evento.</span><span class="sxs-lookup"><span data-stu-id="831d3-121">WPF and its XAML 2006 implementation uses the combination of event handler wiring for routed events defined at the <xref:System.Windows.UIElement> level and its markup compiler step for much of its event attribute processing.</span></span> <span data-ttu-id="831d3-122">Il compilatore di markup preelabora anche gli attributi dell'evento trovati in XAML in cui le operazioni di compilazione dichiarano di usare il compilatore di markup.</span><span class="sxs-lookup"><span data-stu-id="831d3-122">The markup compiler also preprocesses any event attributes found in XAML where the build actions declare that the markup compiler is used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="831d3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="831d3-123">See Also</span></span>  
 [<span data-ttu-id="831d3-124">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="831d3-124">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
