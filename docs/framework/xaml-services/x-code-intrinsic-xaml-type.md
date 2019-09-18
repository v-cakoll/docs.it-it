---
title: Tipo XAML intrinseco x:Code
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 2b7713548b6269f079ef32b5bf1fe4fa630edcc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053790"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="d7654-102">Tipo XAML intrinseco x:Code</span><span class="sxs-lookup"><span data-stu-id="d7654-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="d7654-103">Consente di posizionare il codice in una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="d7654-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="d7654-104">Tale codice può essere compilato da qualsiasi implementazione del processore XAML che compila XAML o lasciata nell'ambiente di produzione XAML per utilizzi successivi, ad esempio l'interpretazione da parte di un Runtime.</span><span class="sxs-lookup"><span data-stu-id="d7654-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="d7654-105">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="d7654-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="d7654-106">Note</span><span class="sxs-lookup"><span data-stu-id="d7654-106">Remarks</span></span>  
 <span data-ttu-id="d7654-107">Il codice all'interno `x:Code` dell'elemento di direttiva XAML viene ancora interpretato nello spazio dei nomi XML generale e negli spazi dei nomi XAML forniti.</span><span class="sxs-lookup"><span data-stu-id="d7654-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="d7654-108">Pertanto, in genere è necessario racchiudere il codice usato per `x:Code` all'interno di un `CDATA` segmento.</span><span class="sxs-lookup"><span data-stu-id="d7654-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="d7654-109">`x:Code`non è consentito per tutti i meccanismi di distribuzione possibili di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="d7654-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="d7654-110">In Framework specifici, ad esempio WPF, è necessario compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="d7654-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="d7654-111">In altri Framework, `x:Code` l'utilizzo potrebbe essere in genere non consentito.</span><span class="sxs-lookup"><span data-stu-id="d7654-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="d7654-112">Per i Framework che consentono contenuto `x:Code` gestito, il compilatore di linguaggio corretto da utilizzare `x:Code` per il contenuto è determinato dalle impostazioni e dalle destinazioni del progetto contenitore utilizzato per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7654-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d7654-113">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="d7654-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="d7654-114">Il codice dichiarato `x:Code` in per WPF presenta diverse limitazioni rilevanti:</span><span class="sxs-lookup"><span data-stu-id="d7654-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="d7654-115">L' `x:Code` elemento Directive deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="d7654-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="d7654-116">è necessario fornire la [direttiva x:Class](x-class-directive.md) sull'elemento radice padre.</span><span class="sxs-lookup"><span data-stu-id="d7654-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="d7654-117">Il codice inserito in `x:Code` verrà gestito dalla compilazione affinché si trovi nell'ambito della classe parziale che è già stata creata per la pagina XAML.</span><span class="sxs-lookup"><span data-stu-id="d7654-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="d7654-118">Pertanto tutto il codice definito deve essere membro o variabili della classe parziale.</span><span class="sxs-lookup"><span data-stu-id="d7654-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="d7654-119">Non è possibile definire classi aggiuntive, tranne annidando una classe all'interno della classe parziale (l'annidamento è consentito, ma non è tipico perché in XAML non è possibile fare riferimento alle classi annidate).</span><span class="sxs-lookup"><span data-stu-id="d7654-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="d7654-120">Non è possibile definire o aggiungere spazi dei nomi CLR diversi dallo spazio dei nomi usato per la classe parziale esistente.</span><span class="sxs-lookup"><span data-stu-id="d7654-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="d7654-121">I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR della classe parziale devono essere tutti completi.</span><span class="sxs-lookup"><span data-stu-id="d7654-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="d7654-122">Se i membri dichiarati sono override dei membri della classe parziale sottoponibili a override, è necessario specificarli con la parola chiave di override specifica della lingua.</span><span class="sxs-lookup"><span data-stu-id="d7654-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="d7654-123">Se i membri dichiarati nell' `x:Code` ambito sono in conflitto con i membri della classe parziale creata da XAML, in modo che il compilatore segnali il conflitto, il file XAML non può essere compilato o caricato.</span><span class="sxs-lookup"><span data-stu-id="d7654-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7654-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7654-124">See also</span></span>

- [<span data-ttu-id="d7654-125">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="d7654-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="d7654-126">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="d7654-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="d7654-127">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d7654-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
